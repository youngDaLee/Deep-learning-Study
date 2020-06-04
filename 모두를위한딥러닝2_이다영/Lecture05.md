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