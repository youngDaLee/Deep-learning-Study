# Logistic Regression
## Classification

### Binary(Multi Class) Classification
variable is 0/1
- Exam : Pass/Fail
- Spam : Not Spam/Spam
- Face : Real/Fake
- Tumor : Not Malignant/Malignant
 python code에서
 학습을 위한 정보를 담고 있는
 x_train=[[1,2],[2,3],[3,1]]
 x의 title인 y
 y_train=[[0],[0],[1]] #One Hot
- 이 두 데이터를 바탕으로 Logistic Regression model을 만들 수 있음    

- Logistic :  두 가지의 case로 구분선으로 구분되어 있음. 셀 수 있다. 데이터가 딱딱 나뉘어 있음. 아날로그
- Linear : data가 연속적이다. 수치형. 디지털

### Hypothesis Representation
직선이 아니라 **g function**을 통해 딱 나뉘어지는 계단형으로 나눔
- g(z)=1/(1+e^-z)
- tensorflow에서는 tf.sigmoid(z)로 우리가 원하는 1과 0의 값을 표현해 낼 수 있음.

### Deicision Boundary
- 0과 1의 두 가지 값으로 구분해 낼 수 있음.


### cost function
- cost는 비용.
- 만들어진 weight를 최적의 비용으로 만드는 것이 cost fucntion.
- 우리가 원하는 이상적인 model값과 실제 값의 차이가 cost

```
def los_fn(hypothesis, labels):
    cost=tf.reduce_mean(labels *tf.log(hypothesis)+(1-labels)*tf.log(1-hypothesis))
    return cost
```
- 우리가 원하는 값은 **가설을 통해 나오는 값**과 **실제 값**의 차이가 최소가 되게 해야함.
- convex : 볼록하다. 볼록해야 최적의 값을 찾을 수 있음
- *우리가 수학시간에 배운 log함수는 x절편이 1이고 0에 가까워지므로 이를 이용해서 최적의 cost fucntion을 구할 수 있음*
    - 왜..?
    - log함수를 cost fucntion으로 변환하는 것 이해가 안됨

### Optimization
- cost function을 최소화 하는 것.
- 경사값을 0에 다다르게 하는 값을 구함으로서 cost function을 optimization

```
def grad(hypothesism labels):
    with th.GradientTape() as tape:
        loss_value=loss fn(hypothesis, labels)
    return tape.gradient(loss_value, [W,b])
optimizer=tf.train.GradientDescentOptimizer(learning_rate=0.01)
optimizer.apply_gradients(grads_and_vars=zip(grads,[W,b]))
```

