# Vectorizing Logistic Regression's Gradient Computation

> vectorization을 통해 m개의 전체 training sample에 대한 Gradient Computation을 동시에 하는 법을 배운다. 또한 효율적인 Logistic Regression의 구현 방법을 배운다.

## Vectorizing Logistic Regression

$dz_1=a_1-y_1\quad$
$dz_2=a_2-y_2\quad\cdots$  
 $dZ=\begin{bmatrix}dz_1&dz_2&\cdots&dz_m\end{bmatrix}$ (1,m)행렬 혹은 m-dimension row vector

지난 강의에서 $A$와 $Y$를 다음과 같이 정의했다.  
$A=\begin{bmatrix}a_1&a_2&\cdots&a_m\end{bmatrix}\quad$
$Y=\begin{bmatrix}y_1&y_2&\cdots&y_m\end{bmatrix}$  
제일 처음 썼던 식($dz_1=a_1-y_1$)을 통해 우리는 활성값$A$와 예측값(?)$Y$를 아래와 같이 표현할 수 있다.
$$dZ=A-Y=\begin{bmatrix}a_1-y_1 & a_2-y_2 & \cdots \end{bmatrix}$$
지난 강의에서 한 개의 for문을 제거했지만, training sample을 계산하는 두 번째 for문은 아직 남아있다.  
$dw$와 $db$를 구하는 과정에서  
$dw=0$  
$dw+=x_1dz_1$  
$dw+=x_2dz_2$  
$\qquad\vdots$  
$dw/=m$  
으로 $dw$를 구하고,  
$db=0$  
$db+=dz_1$  
$db+=dz_2$  
$\qquad\vdots$  
$db+=dz_m$  
$db/=m$  
으로 $db$를 구했다. 이미 하나의 for문을 제거했기 때문에 $dw$는 벡터이고 $dw_1$, $dw_2$를 따로 갱신하지 않았다.

이제 이 두개를 vectorization 해보자.
$$db=\frac{1}{m}\sum_{i=1}^m dz_i=\frac{1}{m}np.sum(dz)$$
$$dw=\frac{1}{m}Xdz^T=\frac{1}{m}\begin{bmatrix}|&|& &| \\x_1&x_2&\cdots&x_m \\ |&|& &|\end{bmatrix}\begin{bmatrix}dz_1\\ \vdots \\ dz_m\end{bmatrix}=\frac{1}{m}\begin{bmatrix}x_1dz_1+\cdots+x_mdz_m\end{bmatrix}$$

- 이 벡터는(m,1)벡터이고 $dw$의 값이 된다.

정리하면 vectorized된 도함수의 계산은 아래와 같은식으로 for문 없이 변수의 갱신값을 계산할 수 있다.
$$db=\frac{1}{m}np.sum(dz)$$
$$dw=\frac{1}{m}Xdz^T$$

이에 따라 Gradient Descent(경사하강법)갱신은
$$w:=w-\alpha dw$$
$$b:=b-\alpha db$$
가 된다.
