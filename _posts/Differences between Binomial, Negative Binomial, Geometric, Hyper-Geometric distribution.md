## Differences between Binomial, Negative Binomial, Geometric, Hyper-Geometric distribution


### Binomial: 
* 두가지 가능한 결과만 주어졌을 때 사용한다. 
	* 예) male/female, heads/tails, 0/1.
* 한번의 시행이 다음 시행에 영향을 주지 않는다.
* 매번 시행의 확률은 똑같다.
* 예시: 동전을 10번 던져서 2번의 앞면이 나올 확률은?

### Negative-Binomial:
* 두가지 가능한 결과만 주어졌을 때 사용한다.
* 한번의 시행이 다음 시행에 영향을 주지 않는다.
* 매번 시행의 확률은 똑같다.
* 다른점은 우리가 원하는 성공횟수가 될 때까지 시험한다.
* 예시: 동전을 10번 던질때 10번째에 2번째 성공이 나타날 확률은?

### Why is this negative binomial?
- 우리가 **1000명의 사람**들중 **10명의 복수학위자**들을 찾고 싶다고 하자. 이것은 **binomial**이다.
- 그러나, **10명의 복수학위자**들을 찾기 위해 우리는 **몇명의 사람들**이 필요할까? 라는 것이 **negative-binomial**로써 binomial과 반대 되는 내용이다.

### Geometric distribution 
- negative binomial의 특수케이스다. 
- 첫번째 성공이 나올 확률? 
- **1명의 복수학위자**가 나오기 위해 **몇명의 사람**들이 필요할까?

### Hypergeometric distribution
* 확률이 일정하지 않은 확률변수들의 확률분포
* 15명의 사람들중에서 7명이 복수학위를 받은 것을 알고있는 상태에서 3명의 복수학위자를 찾고 싶다고 하자.
* 매 시행마다 복수학위자를 찾을 확률이 바뀌는 것을 알 수 있다.
* '큰' 모집단에서 임의로 한명을 뽑았을 때 복수학위를 받은 사람일 확률이 60%이다. 만약 이런 '큰' 모집단 에서 15명의 사람을 뽑는다고 하면, 이것은 binomial distribution이다. 
* '큰' 모집단이기 때문에 우리가 한명을 뽑아도 다음 시행에 복수학위를 받은 사람일 확률(60%)에 영향을 미치지 않는다. 

### Summary
* binomial: 
	* 시행횟수 n 고정
	* 매 시행마다 확률 p값이 일정
	* 복원추출
* hyper-geometric: 
	* 시행횟수 n 고정
	* 매 시행마다 확률 p값이 변함
	* 비복원 추출
* negative binomial:
	* 시행횟수 n 변함
	* 매 시행마다 확률 p값이 일정
	* 성공횟수 k 필요함
* geometric:
	* 시행횟수 n 변함
	* 매 시행마다 확률 p값이 일정
	* 첫 성공까지의 확률분포