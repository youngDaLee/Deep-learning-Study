## Neural Network Representation

![nn2](./img/NN2.png)

### input layer(입력층)

신경망의 입력이 있음.  
입력값의 다른 표기로는 $a^{[0]}=x$로 표기 할 수 있음. 여기서 $a$는 activation value(활성값)를 의미하고, 신경망의 layer들이 다음 layer로 전달해주는 값을 의미한다.  
input layer는 $x$를 hidden layer로 전달해준다. $a^{[0]}$은 input layer의 activation value라 부른다.

### hidden layer(은닉층)

hidden layer의 실제 값은 training set에 기록되어있지 않음. 즉, training set에서 무슨 값인지 볼 수 없다.  
hidden layer는 activation value $a^{[1]}$를 만든다.  
hidden layer의 첫 번째 node는 $a^{[1]}_1$을 만들고 두 번째 노드는 $a^{[1]}_2$를 만든다. 따라서 $a^{[1]}$는 아래 그림과 같은 4-dim vector가 된다.  
![nn3](./img/NN3.png)
파이썬에서는 (1,4) matrix혹은 column matrix로 표기되는데, 4-dim인 이유는 위 예시로 든 hidden layer에 node 개수가 4개이기 때문이다.

### ouput layer(출력층)

하나의 node로 이루어짐. 예측값인 $\hat{y}$를 책임짐.  
output layer는 실숫값 $a^{[2]}$를 만들게 된다. 따라서 $\hat{y}=a^{[2]}$가 된다.  
logistic regression에서 $\hat{y}=a$가 되는 것과 비슷하다. logistic regression에서는 ouput layer 하나만 있어서 대괄호 위첨자를 쓰지 않았지만, NN에서는 위첨자를 사용해 어떤 층에서 만들어진 건지 표기해준다.

---

위 예시로 든 Neural Network는 **2 layer NN**이다. 신경망의 층을 셀 때 input layer는 세지 않기 때문이다.  
따라서 hidden layer가 첫 번째 층이고, output layer가 두 번째 층이다.

- hidden layer는 매개변수 $w^{[1]}$과 $b^{[1]}$에 관련되어있고, 첫 번째 층인 hidden layer에 관련된 변수이기 때문에 위첨자$^{[1]}$를 붙였다.
  - $w$는 (4,3) matrix가 되고,
    - hidden layer가 네개이기 때문에 4, input feature가 세 개 이기 때문에 3.
  - $b$는 (4,1) vector가 된다.
- output layer도 비슷하게 $w^{[2]}$과 $b^{[2]}$에 관련되어있고,
  - 차원은 차례로 (1,4)와 (1,1)이 된다.
