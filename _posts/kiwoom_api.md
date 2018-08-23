# Python - Kiwoom API

## Step1
* 아나콘다 무조건 32bit 짜리로 설치
* 그냥 모든걸 다 32 bit 로 설치하자

## Step2
* Pycharm 실행할 때 무조건 오른쪽 버튼 클릭하고 관리자 모드로 실행

## Step3
* Zipline 설치하기
* Zipline 설치 조건 : Python 3.4이상 3.6미만 (Zipline 공홈 가서 해당 Python 버전 확인 가능)
* Zipline 을 설치하기 위해서는 Visual C++ 2010 있어야 함 (아마 C++ 을 사용해야 하기 때문인 것으로 보임)
* Conda 에 설치하기 위해서 해당되는 가상환경의 Conda prompt 를 켜고 거기에 `pip install zipline` 할 것
* Zipline이 설치 된 후 한번 import 를 해보고 잘 설치 되었는지 확인한다.
* Zipline 설치 후 다시 Terminal을 켜고 Zipline이 존재하는 Path로 가서 다음 코드를 실행 시킨다. (Quandl 을 다운받기 위함) `./zipline ingest -b quantopian-qandl` 
* Path 는 아래와 같다. (비슷하게 접근하면 될 듯) `cd C:/Anaconda3/envs/for_zipline/Scripts`
