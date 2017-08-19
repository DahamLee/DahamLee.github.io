 ---
layout: post
title: "Python (Matplotlib: font setting, plot)"
img: python.png
date: 2017-08-19 13:00:00 +0900
tag: [Python, Numpy, Pandas, matplotlib]
---
# Python (matplotlib: font setting, plot)


##### 안녕하세요, 제 블로그는 제가 공부하면서 어려웠던 부분에 대해서 정리하고 공유하는 블로그 입니다.

##### 이번에는 matplotlib 에 대해서 알아보겠습니다.

##### data science는 visualization 이 매우 중요하다고 하네요.. 그래서 그래프를 그릴 줄 알아야 한다고 합니다.

## 그럼 시작해보겠습니다.


##### matplotlib import
`import matplotlib.pyplot as plt`

<hr>

##### 저는 IDE로 Pycharm을 사용하는데 matplotlib plot에서 한글을 출력하기 위해 약간의 세팅이 필요합니다.

##### 저도 한글 출력 때문에 고생을 많이했기 때문에 여러분들도 필요한? 내용이라고 생각합니다. 저는 `안수찬 님의 블로그`를 통해서 글꼴 변경하는 방법을 배웠는데요,

##### `안수찬 님`께서는 여러가지 방법을 알려주셨지만 저는 제가 사용한 방법만 작성해 보겠습니다. (다른 방법으로 변경하시고 싶으신 분은 아래의 출처에서 확인 부탁 드립니다.)

_source: https://ansuchan.com/matplotlib-with-korean/_

##### 먼저 console을 켜고 ipython(또는 python)을 실행시킵니다.

##### matplotlib import
```
In [2]: import matplotlib
```

##### 글꼴 정보에 대한 위치 확인 코드
```
In [5]: matplotlib.matplotlib_fname()

Out[5]: '/usr/local/var/pyenv/versions/3.6.1/envs/finance/lib/python3.6/site-packages/matplotlib/mpl-data/matplotlibrc'
```

##### 저는 pyenv 가상 환경을 사용하고 있기 때문에 위와 같이 주소가 나왔지만 사용자분들께서는 각자 해당되는 주소가 출력 될 것입니다.

##### 저기 주소로 타고 들어가서 해당 파일을 열어 봅니다.

![screenshot]({{ site.url }}/assets/img/2017-08-19_2.png)

##### 위와 같이 font.family가 sans-serif 로 되어 있을 텐데 원하시는 font로 바꿔 주시면 됩니다. (font는 따로 다운 받으셔야 됩니다.)

##### 폰트를 변경해주고 나면 이제 한글이 잘 출력 되는 것을 확인 할 수 있습니다.

##### ! *중요* : 글꼴을 변경하고 나면 pycharm 에서 사용하실 때 아래의 코드를 작성해 주셔야 `-`(음수)가 출력이 됩니다.

```plt.rcParams['axes.unicode_minus'] = False```

## 그럼 다시.. 시작해보겠습니다.

##### plot의 기본 사용법 입니다.

```
import matplotlib.pyplot as plt
import numpy as np


t = np.arange(0, 5, 0.2)
plt.plot(t, t, 'r--', t, t ** 2, 'bs', t, t ** 3, 'g^')
plt.show()
```
오늘은 한글 setting에 대해서 너무 많은 이야기를 했기 때문에 plot은 여기까지만 하겠습니다.
