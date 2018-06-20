# Hadoop

### Hadoop 실행 방법: 
1. docker image에 sandbox 설치
	* 설치는 아래의 링크 참조
	* [how to install](https://community.hortonworks.com/articles/58458/installing-docker-version-of-sandbox-on-mac.html)

2. terminal 켜고 `docker start sandbox`
3. terminal 에서 `ssh -p 2222 root@localhost` (Hadoop root 권한으로 가상 컴퓨터에 접속? 이게 맞나..)
4. 가상 컴퓨터 접속 후 Hadoop 실행 `/etc/init.d/startup_script start`
	* 이걸 켜야 웹 브라우져에서 접속 가능함
5. 웹브라우져 켜고 localhost:8888 port 접속

### Cli 환경으로 maria_dev 권한으로 접속
1. 위의 2번까지는 동일, 그 후 terminal 켜고 `ssh -p 2222 maria_dev@localhost`. 비밀 번호: maria_dev 동일
2. 접속 후 command 는 모두 `hadoop fs OOOOO` 의 형태로
	* `hadoop fs -ls`
	* `hadoop fs -mkdir ml-100k`
	* `wget http://media.sundog-soft.com/hadoop/ml-100k/u.data` u.data가 설치 됨
	* `hadoop fs -copyFromLocal u.data ml-100k/u.data` 설치된 u.data를 위에서 만든 ml-100k 폴더에 복사.
3. 여기서 root로 가는 법은 `su root`

### Hadoop MapReducer 작동 원리
* Data example:

User_ID | Movie_ID | Rating | TimeStamp
|:---:|:---:|:---:|:---:|
196 | 242 | 3 | 8812
186 | 302 | 3 | 8917
196 | 377 | 1 | 8788

	 
* Mapper
 
```python
def mapper_get_ratings(self, _, line):
	(userID, movieID, rating, timestamp) = line.split('\t')
	yield rating, 1
```

* Reducer

```python
def reducer_count_ratings(self, key, values):
	yield key, sum(values)
```

* All code

```python
from mrjob.job import MRJob
from mrjob.step import MRStep

class RatingsBreakdown(MRJob):
	def steps(self):
		return[
			MRStep(mapper=self.mapper_get_ratings,
					reducer=self.reducer_count_ratings
			]
	def mapper_get_ratings(self, _, line):
	(userID, movieID, rating, timestamp) = line.split('\t')
	yield rating, 1
	
	def reducer_count_ratings(self, key, values):
	yield key, sum(values)

if __name__ == '__main__':
	RatingBreakdown.run()
```
	
### Pip 설치 in 가상컴퓨터
* sandbox docker 접속 후 아래와 같이 코드를 사용하여 Python을 사용할 수 있도록 한다.

```
# PIP
yum install python-pip

# MRJob
pip install mrjob==0.5.11

# Nano
yum install nano

# Data files and the script
wget http://media.sundog-soft.com/hadoop/ml-100k/u.data
wget http://media.sundog-soft.com/hadoop/RatingsBreakdown.py
```
	
### Hadoop MapReducer 실행
* RatingsBreakdown.py => 위의 'All code'
* 따라서 가상 컴퓨터에서 `python RatingsBreakdown.py u.data` 실행하면
* u.data를 위의 파이썬 코드로(MapReduce 기능) 결과 출력한다.
* .
* 위의 기능을 hadoop을 이용해서 진행하면 아래와 같다.
* `python RatingsBreakdown.py -r hadoop --hadoop-streaming-jar /usr/hdp/current/hadoop-mapreduce-client/hadoop-streaming.jar u.data`
* 강의자 말로는 원래 위의 코드(바로 위만 해당)의 u.data 대신 HDFS 주소를 써야한다고 한다.
* u.data는 가상 컴퓨터의 로컬파일로 저장하였기 때문에 위와 같이 사용했지만 보통은 HDFS.

### Ambari
* 일단 maria_dev에 접속
* `su root` root권한으로 접속
* `ambari-admin-password-reset` 을 통해 ambari admin 계정 생성
* localhost:8080 접속 후 admin 계정으로 접속 가능

### Pig
* Ambari 접속 (maria_dev 로 접속)
* 우측 상단의 table 모양의 아이콘을 클릭
* File View 클릭 (가상 컴퓨터 내의 폴더들을 보여줌 - 우리가 원하는 데이터 파일을 업로드 시킬 수 있음)
* user/maria_dev의 디렉토리에 ml-100k 폴더 생성 후 거기에 data file 업로드
* 우측 상단의 table 모양의 아이콘을 클릭
* Pig View 클릭
* New Script 작성

```pig_code
ratings = LOAD '/user/maria_dev/ml-100k/u.data' AS (userID:int, movieID:int, rating:int, ratingTime:int);

metadata = LOAD '/user/maria_dev/ml-100k/u.item' USING PigStorage('|') AS (movieID:int, movieTitle:chararray, releaseDate:chararray, videoRelease:chararray, imbdLink:chararray);
    
nameLookup = FOREACH metadata GENERATE movieID, movieTitle, ToUnixTime(ToDate(releaseDate, 'dd-MMM-yyyy')) AS releaseTime;

ratingsByMovie = GROUP ratings BY movieID;

avgRatings = FOREACH ratingsByMovie GENERATE group AS movieID, AVG(ratings.rating) AS avgRating;

fiveStarMovies = FILTER avgRatings BY avgRating > 4.0;

fiveStarsWithData = JOIN fiveStarMovies BY movieID, nameLookup BY movieID;

oldestFiveStarMovies = ORDER fiveStarsWithData BY nameLookup::releaseTime;

DUMP oldestFiveStarMovies;
```

* Execute 버튼을 눌러서 MapReduce 기능 실행 (Execute on Tez를 누르면 Tez를 사용해서 빠르게 된다.)















	
	
	