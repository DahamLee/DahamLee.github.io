## Correct meaning of Confidence Interval in Bayesian


#### ex) Based on a 2015 PR poll on 1500 adults: "We are 95% confident that 60 % to 64% of Americans think the federal goverment does not do enough for middle class people"

* Correct meaning: **95% of random samples** of 1500 adults will produce **confidence intervals** that **contain the true proportion of** Americans who think the federal goverment does not do enough for middle class people.

* Wrong answer: There is a **95% chance** that this confidence interval includes the true population proportion
* the true population proportion is in this interval 95% of the time


* Correct meaning: **95% of similary** constructed intervals will contain the true mean"

* Wrong answer: the probability that true mean lies between L and U is 0.95

왜냐하면 Frequentist 들은 불확실성을 확률로 표현하지 않기 때문이다. true mean이 interval 안에 있냐 없냐를 나타낸다 0 또는 1의 확률로.

즉, 위의 예를 보면 샘플의 95%가 true proportion을 가지고 있고, 5%는 가지고 있지 않다. (이건 확률이 아니라 샘플을 95:5로 나눈 것이라고 생각하자)

하지만 Bayesian은 "the probability the true mean is contained within a given interval is 0.95"