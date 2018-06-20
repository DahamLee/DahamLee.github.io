## Linear Regression

### Terms
Yi = Observed data
Y hat i = Predicted data
Y bar = Centered point (mean)


### Errors

* Total variability (SSTotal): Total variability where they are centered
`Sigma(Yi- Ybar)^2`
* Explained Variability (Regression variability) 
`Sigma(Y hat i- Ybar)^2`
* Unexplained Variability (SSResidual): difference between the observed(Yi) and Predicted (Y hat i) values of the response variable
`Sigma(Y i- Y hat i)^2`

### Residual (Unexplained Variability)

모분산
`sigma^2 (population) = Sigma (error i)^2 / n`
표본분산 (k = beta 개수, 예: intercept를 제외한 beta 1개면 총 beta 1개)
`(sigma hat)^2 = Sigma (error i)^2 / (n-k-1)`

### R square
R^2는 Total variability중에 Regression variability가 얼마나 차지하고 있는지 확인하는 지표이다.

즉, 우리가 생각한 모델이 얼마나 잘 맞는지 보여주는 지표이다.

* Adujsted R square

n은 전체 표본 개수, 일단 표본이기 떄문에 **n-1**에서 시작하며
모델의 베타개수인 k만큼 빠진 **n-k-1**이 Residual Error에 들어간다.
```
1- {SSResidual/(n-k-1)} / {SSTotal/(n-1)}
```
따라서, 베타 개수(k) 즉, 모델에 변수가 추가 될 수록 k가 커지며, Adjusted R square는 penalty를 받게 된다.


