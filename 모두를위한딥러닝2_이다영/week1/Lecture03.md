Review
===
## Hypothesis
H(x)=Wx=b
## cost
cost(W,b)=1/m((i=1~m까지)(H(xi)-yi)^2)
- cost가 최소인 W와 b를 찾는 것


### Simplified hypothesis 간략화
- H(x)=Wx
- cost(W)=1/m((i=1~m)(Wxi-yi)^2);

Lecture 03
===
cost(W)
---
위에 간략화 수식 이용해 계산하면
- W=0, cost(W)=4.67
- W=1, cost(W)=0
- W=2, cost(W)=4.67
- W=3, cost(W)=18.67     

 - 그래프로 그리면 이차함수 모양
 - 최저점 찾기 위해 Gradient descent algorithm

Gradient descent algorithm
---
경사하강 알고리즘
- 최저점 찾기 위한 알고리즘
- **최적화 알고리즘**(손실을 최소화-cost를 최소화 되는 W와 b 찾는 알고리즘)
- W1,W2,..이렇게 변수가 여러 개 일때도 사용 가능      


- 최초의 추정을 이용해 W, b값 정함
 - 0,0 이던, 다른 랜덤값이던 상관 없음
 - W,b를 줄어들 수 있는 방향으로 지속적으로 바꿔나감
- W,b 업데이트 할 때 **기울기**를 이용해 cost 최소화 되는 방향으로 업데이트 해 나감
 - 최소점에 도달했다 라고 판단될 때 까지 이 과정 반복

- 뒤에서 미분을 위해 cost(W,b) 식에서 나누는 값을 1/m에서 1/2m으로 변경..

- 미분한 값에 learning rate(학습율) 곱해서 W값 찾아감
 - learning rate 높으면 : W값 큰 폭으로 움직임(섬세x, 빠름)
 - learning rate 낮으면 : W값 작은 폭으로 움직임(섬세,느림)

 - Convex function
    - 주변에 비해 가장 낮은 지역 : 기울기가 0 => **local minimum**
    - local minimum과 global minimun이 일치한 함수를 convex function. 찾고자 하는 값이 하나인 함수





