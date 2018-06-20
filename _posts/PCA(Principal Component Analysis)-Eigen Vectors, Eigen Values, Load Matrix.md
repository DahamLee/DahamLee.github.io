## PCA(Principal Component Analysis)-Eigen Vectors, Eigen Values, Loading Matrix


### Principal Component Analysis:
* PCA 의 목적은 모델의 구조를 분석하여 기존의 변수들을 더 설명력이 강한(has desirable properties) 새로운 변수로 대체하는 것.
* 새로운 변수들은 기존 변수의 linear combination이다.

### Desirable Properties
* Dimensionality reduction (Parsimony)
* Explanatory Power
* Uncorrelated - The new variables are uncorrelated with each other
* Insight - The new variables may reveal hidden structure and unsuspected interpretations.

### Correlation Matrix
* 각 Variable 간의 Correlation (Data에서는 Column)
* Variable인 X1(x11,x12,x13..), X2(x21,x22,x23,..), ..간의 correlation
* 여기는 각 Variable들의 **Variance**들도 포함을 하고 있다. 이것을 Maximize 하는 것이 중요

### 계산법
계산 법은 Correlation Matrix에서 Lamda와 I를 이용하여 Eigen Vector를 구한다.
R: Correlation Matrix
Lamda: Eigen Value
v: Eigen Vector

R * v = Lamda * v

### 계산 후
PCA => PRIN1 = v1(Eigen Vector) * X1 + v2(Eigen Vector) * X2 + ...

### Eigen Value
* Maximized Variance (가장 큰 분산 값)

### Eigne Vector
* Coefficient of PRIN

### Loading Matrix
* Correlation between PRIN and X

### 중요한 관계
Eigen Vector / Loading Matrix = sqrt(Eigen Value)

### Orthogonal between Eigen Vectors
**Ex) Orthogonal 보이는 방법 2x2 Matrix, Eigen Value**

Eigen Value 와 corresponding 하는 Eigen Vector를 아래와 같이 찾았다고 하자

```
A * v1 = Lamda1 * v1 ...'식 1'
A * v2 = Lamda1 * v2 ...'식 2'
```
```
v2^T * A * v1 = Lamda1 * v2^T * v1 (식 1의 양쪽 v2^T 행렬 곱) ...'식 3'  
v1^T * A * v2 = Lamda1 * v1^T * v2 (양쪽 전치행렬) ...'식 4'  
v1^T * A * v2 = Lamda2 * v1^T * v2 (식 2의 양쪽 v1^T 행렬 곱) ...'식 5'
```
```
'식 4' 와 '식 5'를 동시에 만족시키려면 v1^T * v2 = 0 
(조건: Lamda1 =\= Lamda2)
즉, dot(v1, v2) = 0  ===> orthogonal
```