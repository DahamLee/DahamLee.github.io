---
layout: post
title: "Derivatives"
description: "(Options)"
img: derivatives.jpeg
date: 2017-08-29 13:00:00 +0900
tag: [Derivatives]
---
# Derivatives (Options)


#### 안녕하세요, 제 블로그는 제가 공부하면서 어려웠던 부분에 대해서 정리하고 공유하는 블로그 입니다.

#### 오늘은 옵션에 대해서 알아보겠습니다.


## 그럼 시작해보겠습니다.

### 옵션 용어

* expiration date(maturity date): 만기일
* exercise price(strike price): 행사가격

* Call options: 살 수 있는 권리
* Put options: 팔 수 있는 권리

* bermudan option: holder can exercise every n months(specified date) up until the expiration date.

* American option can't be cheaper than European option.
* becuase
> American option = European + (additional Exercise right. = usually '0', but cannot be '-')


* Payoff diagram:
> * payoff means only the spot of maturity time
> * so, payoff diagram shows data only at maturity time.
> * payoff is that the cashflow occurs at the maturity time



* option price = option premium


* option profit/loss = option payoff(maturity) + option price(=premium)(when you sell)
> payoff & profit 구별 확실히 하자~!!
> by convention we ignore time value of money


* in the money: when the payoff would be positive if it were exercised immediately. (지금 행사된다고 생각했을 때 양의 payoff를 가질 떄)
* out of the money: if the payoff would be zero if it were exercised immediately
* at the money: if the underlying is at the strike price


ITM: in the money
ATM: at the money
OTM: out of the money


* intrinsic value: `considering payoff`, maximum of zero and the value the option would have if it were exercised immediately
* time value: still has posibility of earning cash

* option premium(price) = Instrinsic value + time value

* in extreme case time value can be negative.
* 풋옵션을 가지고 있는데 그 회사가 부도나서 증권가격이 0이 됐다.
* 내가 만기시점에 얻을 수 있는 이익은 행사가격(K)이다. 
* 따라서 이를 현재 시점으로 바꾸면 continuous compound를 통해서 PV=K\*e^(-k*T) 라는 것을 알 수 있다.
* intrinsic value는 K이다.(정의: 지금 바로 행사했을 때 얻을 수 있는 이익)
* 따라서 옵션의 가치는 intrinsic value+time value 인데, intrinsic value(K) > option price(PV)
* 따라서, time value is negative.
* only occurs for 'put option'


* institution investor has large portion in short position.
* 기관 투자자들은 옵션뿐만 아니라 underlying asset을 갖고있기 때문에 (시장을 주도하는 힘이 있기에)
* initial margin이 개인투자자보다 많기 때문에.

