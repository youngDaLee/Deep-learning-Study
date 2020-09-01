# Computing Neural Network Output

![nn4](./img/NN4.png)
logistic regression을 나타내는 이 원은 두 단계의 계산을 나타낸다. $z$를 $w^Tx+b$의 식으로 계산하고 activation $a$를 $\sigma(z)$로 계산한다.  
Neural Network에서는 위 식을 여러 번 반복한다(오른쪽 그림). 먼저 hidden layer의 노드 하나를 자세히 살펴보자.

---

앞으로의 표기
$$a^{[l]}_i$$

- $l=layer$
- $i=node-in-layer$

위 NN에서 $z^{[l]}_i=w^{[l]T}_ix+b^{[l]}_i$의 식이 여러 번 반복된다(위 그림에서는 4차례 반복). 따라서 이 $z$를 vetorization 해 주겠다.
![nnr](./img/nnr.png)
vectorizing의 결과 matrix의 각 행은 위에서 계산한 네 값과 정확히 일치한다. 따라서 이 matrix값은
$$\begin{bmatrix}z^{[1]}_1 \\ z^{[1]}_2\\z^{[1]}_3\\z^{[1]}_4\end{bmatrix}$$
와 같다. 이 column vector를 **$z^{[1]}$** 이라고 부르겠다.

이제 $a$값을 계산해야 한다.
$$a^{[1]}=\begin{bmatrix}a^{[1]}_1 \\ a^{[1]}_2\\a^{[1]}_3\\a^{[1]}_4\end{bmatrix}=\sigma(z^{[1]})$$
이 된다.

![nnr2](./img/nnr2.png)
