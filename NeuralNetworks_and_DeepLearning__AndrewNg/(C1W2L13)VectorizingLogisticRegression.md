# Vectorizing Logistic Regression

먼저, 정방향 전파(forward propagation)를 살펴보자.  
$z^{(1)}=w^Tx^{(1)}+b$  
$a^{(1)}=\sigma(z^{(1)})$  
m개의 훈련 샘플이 있을 때 처음 샘플을 예측하기 위해서는 위의 두 공식으로 z를 계산한 뒤 활성값과 y의 예측값도 계산해야 한다.

$z^{(2)}=w^Tx^{(2)}+b$  
$a^{(2)}=\sigma(z^{(2)})$  
두 번째 샘플을 훈련 예측하기 위해서는 이 값을 계산한다.

즉 m개의 훈련샘플을 계산하기 위해서는 위 수식을 m번 계산해야 한다.

### for문을 사용하지 않고 계산하는 방법(forward propargation)

먼저, $X$는 training input을 column으로 쌓은 matrix라는 것을 기억하자.
$$ X=\begin{bmatrix}|&|& &| \\x_1&x_2&\cdots&x_m \\ |&|& &|\end{bmatrix}$$
`(nx,m)`의 행렬.

1. $z_1, z_2, z_3$ 등을 한 줄의 코드로 작성
   - 행 벡터이기도 한 (1,m) 행렬을 생성
   - 거기에서 $[z_1, ..., z_m]$ 까지 계산
   - $[z_1, ..., z_m]=w^TX_T[b,b,b, ...b]$ (1,m)행렬이다.
   - &w^T$ 에 $[x_1, x_2, ..., x_m]$ 으로 이루어진 행렬을 곱하면 $w^T\$는 행벡터가 된다.
   - $[z_1, ..., z_m]=w^TX_T[b,b,b, ...b]=[w^Tx_1+b, w^Tx_2+b, ..., w^Tx_n+b]$

훈련샘플인 x를 가로러 쌓은 결과가 X인것 처럼 소문자 z를 쌓은 결과가 Z이다.

이 값을 계산하는 numpy 명령어

```
Z=np.dot(w.T,X)+b
```

- b는 하나의 실수.
- np.dot의 벡터와 실수 b를 더하면 실수 b를 자동으로 (1,m) row벡터로 변환시켜줌 - 이 현상을 **broadcasting**이라고 함
  이 한 줄의 코드로 z를 얻을 수 있음.

### vectorization을 통해 소문자 a(예측값)로 표현되는 activaton value를 동시에 효율적으로 계산하는 방법

$x$와 $z$를 가로로 쌓아서 $X$와 $Z$를 얻은 것 처럼 $a$를 쌓아 $A$를 만든다.
$$ A=\begin{bmatrix}a_1&a_2&\cdots&a_m\end{bmatrix}=\sigma(Z)$$

- 적절한 $\sigma$의 구현으로 한 줄의 코드로 모든 $a$를 동시에 계산할 수 있음.

vectiorization을 통해 역방향 전파의 도함수도 효율적으로 구할 수 있음.
