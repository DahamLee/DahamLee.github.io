## Fama French 3 factors

* 5 factor: (over market, firm size, book to market equity), common factor(만기-TERM, default risk-DEF)
* 주식 시장의 횡단면 평균수익률에 영향을 주는 팩터 만을 검증한 것을 채권까지 포함하여 검증
* 3개의 주식시장 팩터 RMO SMB HML 가 주식수익률의 커먼 배리에이션을 생성하며 low-grade 회사채를 제외하고는 정부채와 회사채의 수익률에 영향을 주지 못한 반면 주식과 채권 시장은 2개의 기간구조 factor(TERM, DEF)에 의해 연결됨을 밝힘
* R^2가 높아져야 되는데 5개를 다 넣었더니 R^2가 낮아진다. (개별적으로 볼때는 R^2가 올라갔는데)

* Term: 장기 정부채와 1개월 t-bill간의 월별 금리차
* DEF: 장기 회사채의 시장포트폴리오 수익률과 장기 정부채 수익률 간의 차이

### stock market common factors
#### SMB
* 1963-1991년 기간 중 모든 NYSE주식을 사이즈(주가*주식수) 별로 서열화 하고 Median NYSE size로 NYSE, AMEX, NASDAQ 주식을 small, big으로 분리 (12월을 쓰지 않고 **6월말 기준**으로 잡는다, 12월은 조작이 가능하기 때문에?)
* 7월의 평균 수익률 (7월의 smb return의 시리즈는
#### Booked Market ratio
* BE/ME 를 low(30%), medium(40%), high(30%)로 구분

#### 6개 포트폴리오(S/L, S/M, S/H, B/L, B/M, B/H) - table1

* r_smb = SL+SM+SH - (BL+BM+BH)
* r_hml = BH+SH - (BL+SL)

##### TERM과 DEF - table3
* factor자체는 alpha값이(통계검정에서) 유의미 하지만 5.0이상? 3.5이상? table 3에서 우측상단 부분 데이터들
* 하지만 R^2값이 너무 적게 나와서 모형은 무의미 하다는 것을 알 수 있다.

##### table4
* 초과수익률에 관해서만 확인을 해보니, 주식에 있어서는 R^2가 높게 나오지만 채권에 있어서는 R^2가 낮게 나온다

##### table5
* SMB와 HML을 factor로 놓은것도 어느정도 R^2가 높게 나와서 유의미 하다. 하지만 table4보다는 낮게 나온다.
* 채권에서는 역시 R^2가 0에 수렴해서 별 의미가 없다.

##### table6
* 이것이 파마프랜치 모델
* 베타값은 거의 1에 수렴하고 있고
* s값은 시그니피컨트 하고 (SMB의 코에피션트)
* 작은놈의 s값이 큰놈의 s값보다 모두 작게 나오고 (본 논문을 증명하는 셈)
* h값(HML의 코에피션트) 방향이 잘 맞는다. 큰놈과 장부가치 큰놈이 크고 반대는 작은게 명확하다.
* R^2도 명확하다

##### table 8a
* RM-RF 마켓 초과수익률이 너무 dominate하지 않을까 해서 그거 대신 RMO를 쓴다(대용치로, 잔차와 인터셉트를 더한값) 
* RMO를 쓴다면 RM-RF를 쓰면 t검정량이 더 커져서 더 설명력이 높아진다.

##### table 9a
* 가정했던 모든 리그레션들을 비교하여 알파가 가장 0에 가깝게 나온 모델을 찾는다. 그것이 바로 4번 또는 5번인데, 4번이 더 검정력이 좋다.