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