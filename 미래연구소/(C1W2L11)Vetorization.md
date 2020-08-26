# Vectorization

코드에서 for문을 없애는 것. 딥러닝 알고리즘이 발전하게 해 준 것.  
$z=w^Tx+b$  
$w=\begin{bmatrix}\vdots \end{bmatrix}$  
$x=\begin{bmatrix}\vdots \end{bmatrix}$

### Non-vectorized

```
z=0
for i in range (n_x):
    z+=w[i]*x[i]
z+=b
```

### Vectorized

vectorized된 구현은 위의 $w^Tx$를 직접 계산한다. python에서 이 식을 다음과 같이 구현한다.

```
z=np.dot(w,x)+b
```

아무튼 핵심은 vectorizeation에서 for loop를 대체하며 딥러닝 알고리즘 적용 시 시간이 아주 크게 단축된다.
