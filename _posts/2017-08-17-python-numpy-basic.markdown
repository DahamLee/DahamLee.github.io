---
layout: post
title: "Python (Numpy: slicing, polyval)"
img: python.png
date: 2017-08-17 13:00:00 +0900
tag: [Python, Numpy, polyval]
---
# Python (Numpy: slicing, polyval)


##### 안녕하세요, 제 블로그는 제가 공부하면서 어려웠던 부분에 대해서 정리하고 공유하는 블로그 입니다.

##### 오늘은 python의 강력한 기능인 slicing과 numpy를 이용한 급수 표현에 대해서 작성해보겠습니다.

##### 너무 어려웠기 때문에 저도 하나씩 해보면서 익혀가야 될 것 같습니다.


## 그럼 시작해보겠습니다.

##### Numpy import 
`import numpy as np`

##### 먼저 배열하나를 생성하고 이 배열을 이용해서 slicing을 해보겠습니다.

```
In [76]: z = np.arange(1,10)

In [77]: z
Out[77]: array([1, 2, 3, 4, 5, 6, 7, 8, 9])

In [78]: z.shape=(3,3)

In [79]: z
Out[79]:
array([[1, 2, 3],
       [4, 5, 6],
       [7, 8, 9]])


```

##### z 라는 3행 3열인 행렬을 만들었습니다.

```
[[1, 2, 3],
 [4, 5, 6],
 [7, 8, 9]]
```

## slice 연산

* `,`의 왼쪽은 행을, 오른쪽은 열을 나타냅니다.

* `:`는 두개를 사용할 수 있습니다.

* 시작점 `:` 끝점 `:` 간격

* 시작점 생략시 `처음부터`, 끝점 생략시` 끝까지`, 간격 생략시 `시작부터 끝까지 모든 행 또는 열`


##### 아래는 제가 연습삼아 해본 코드 입니다. 위의 내용을 바탕으로 연습해보시면 이해가 빠르실 겁니다.

```
In [93]: z[0:3,:]
Out[93]:
array([[1, 2, 3],
       [4, 5, 6],
       [7, 8, 9]])

In [94]: z[0:3,:2]
Out[94]:
array([[1, 2],
       [4, 5],
       [7, 8]])

In [95]: z[0:3,::2]
Out[95]:
array([[1, 3],
       [4, 6],
       [7, 9]])

```

## Polynomial 함수

##### 이제 급수(series)를 numpy내의 polynomial 함수를 사용해서 풀어보도록 하겠습니다.

![sereis]({{ site.url }}/assets/img/2017-08-17_1.gif)



### Polyval

##### polyval 함수에 대해서 알아보겠습니다.

`polyval(x, c, tensor=True)`

* `x` 넣으려는 값
* `c` 계수 (coefficient)
* `tensor` 는 뭔지 모르겠네요..

##### polyval 함수는 polynomial을 `2번` 타고 들어가야 나타납니다. 아래의 코드를 보시죠..


```
import numpy as np

sum_of_series = np.polynomial.polynomial.polyval(10, [1,2,3,4])

sum_of_series
Out[157]: 4321.0
```

##### 위와 같이 `x`의 자리에 10을 넣었고 `c`의 자리에 list [1,2,3,4]를 넣었습니다.
##### 결과를 보니 4321이 나왔네요 이를 거꾸로 생각해보면  `1*1 + 2*10 + 3*100 + 4*1000` 로 계산된 것을 알 수 있습니다.
##### 즉, 아래의 급수를 polyval 함수로 계산한 것이라고 할 수 있습니다.

![sereis]({{ site.url }}/assets/img/2017-08-17_2.gif)

![sereis]({{ site.url }}/assets/img/2017-08-17_3.gif)



##### 오늘은 polyval 까지만 보겠습니다. 마크다운으로 수식을 작성해서 업로드 하는 것이 어렵네요.
