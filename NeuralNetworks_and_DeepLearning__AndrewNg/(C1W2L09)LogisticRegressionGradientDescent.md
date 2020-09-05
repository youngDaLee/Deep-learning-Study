이 강의에서는 logistic regresion의 Gradient Descent를 위해 Computation graph를 사용한다.

Logistic Regression을 다시 한 번 복기해보자.
$$z=w^Tx+b$$
$$\hat{y}=a=\sigma(z)$$
$$L(a,y)=-(y\log(a)+(1-y)=\log(1-a))$$

- 여기서 a는 logistic regression의 출력값, y는 참값 레이블이다.

이를 computation graph로 나타내보자.
![lrcg](./img/lr_cg.png)
logistic regression에서는 매개변수 w,b를 조절하여 Loss function인 $L(a,y)$를 줄이는 것이 목적이다.  
그래프에서 역방향으로 가서 a에 대한 손실함수의 도함수($\frac{dL(a,y)}{da}$)를 계산해보자. 코드에서는 이 변수를 $da$라 할 수 있다. 미적분에 대한 지식을 이용해 이를 계산해보면 다음과 같은 결과가 나온다.
$$ da=\frac{dL(a,y)}{da} = -\frac{y}{a}+\frac{1-y}{1-a}$$
다시 역방향으로 가서 $dz$는 z에 대한 손실함수의 도함수이고($\frac{dL}{dz}=\frac{dL(a,y)}{dz}$) 이를 미적분의 chain rule(연쇄법칙)을 이용해 계산하면 아래와 같이 나타낼 수 있다.
$$\frac{dL}{dz}=\frac{dL(a,y)}{dz}=a-y$$
역전파의 마지막 알고리즘은 w,b를 얼마나 바꿔야하는지 계산하는 것이다.

$w_1$의 변화량을 나타내는 $dw_1$은 아래와 같다.
$$\frac{dL}{dw_1}=dw_1=x_1\cdot dz$$
마찬가지로 $w_2$의 변화량을 나타내는 $dw_2$은 아래와 같다.
$$\frac{dL}{dw_2}=dw_1=x_2\cdot dz$$
그리고
$$db=dz$$
이다.  
이 식들로 $dw$, $db$를 계산한 뒤에 w,b를 계산할 수 있다.

$$w_1:=w_1-\alpha dw_1$$
$$w_2:=w_2-\alpha dw_2$$
$$b:=b-\alpha db$$

- $\alpha$는 learning rate
