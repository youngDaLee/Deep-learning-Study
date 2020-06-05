# Logistic Regression
## Classification

### Binary(Multi Class) Classification
variable is 0/1
- Exam : Pass/Fail
- Spam : Not Spam/Spam
- Face : Real/Fake
- Tumor : Not Malignant/Malignant
 python code����
 �н��� ���� ������ ��� �ִ�
 x_train=[[1,2],[2,3],[3,1]]
 x�� title�� y
 y_train=[[0],[0],[1]] #One Hot
- �� �� �����͸� �������� Logistic Regression model�� ���� �� ����    

- Logistic :  �� ������ case�� ���м����� ���еǾ� ����. �� �� �ִ�. �����Ͱ� ���� ������ ����. �Ƴ��α�
- Linear : data�� �������̴�. ��ġ��. ������

### Hypothesis Representation
������ �ƴ϶� **g function**�� ���� �� ���������� ��������� ����
- g(z)=1/(1+e^-z)
- tensorflow������ tf.sigmoid(z)�� �츮�� ���ϴ� 1�� 0�� ���� ǥ���� �� �� ����.

### Deicision Boundary
- 0�� 1�� �� ���� ������ ������ �� �� ����.


### cost function
- cost�� ���.
- ������� weight�� ������ ������� ����� ���� cost fucntion.
- �츮�� ���ϴ� �̻����� model���� ���� ���� ���̰� cost

```
def los_fn(hypothesis, labels):
    cost=tf.reduce_mean(labels *tf.log(hypothesis)+(1-labels)*tf.log(1-hypothesis))
    return cost
```
- �츮�� ���ϴ� ���� **������ ���� ������ ��**�� **���� ��**�� ���̰� �ּҰ� �ǰ� �ؾ���.
- convex : �����ϴ�. �����ؾ� ������ ���� ã�� �� ����
- *�츮�� ���нð��� ��� log�Լ��� x������ 1�̰� 0�� ��������Ƿ� �̸� �̿��ؼ� ������ cost fucntion�� ���� �� ����*
    - ��..?
    - log�Լ��� cost fucntion���� ��ȯ�ϴ� �� ���ذ� �ȵ�

### Optimization
- cost function�� �ּ�ȭ �ϴ� ��.
- ��簪�� 0�� �ٴٸ��� �ϴ� ���� �������μ� cost function�� optimization

```
def grad(hypothesism labels):
    with th.GradientTape() as tape:
        loss_value=loss fn(hypothesis, labels)
    return tape.gradient(loss_value, [W,b])
optimizer=tf.train.GradientDescentOptimizer(learning_rate=0.01)
optimizer.apply_gradients(grads_and_vars=zip(grads,[W,b]))
```

