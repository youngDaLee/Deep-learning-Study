# Tensorflow
## 개요
- 1버전보다 정말 쉬워졌음(우리가 하는건 2버전)
- Numpy Array와 호환이 쉬움
- TensorBoard : Tensorflow를 사용하는 주된 이유. 중간에 얼마나 학습이 되고 있는지, 시각화를 사용하기 위해서는 TensorBoard 이용
- TFLite : 안드로이드 사용하는 사람들이 많이 사용한다 함
- TPU : 구글클랩?을 사용할 때 TPU를 사용하면 학습속도가 빨라진다 함.
- 여전히 많은 사용자들이 사용

## Tensorflow 기초 사용법
- 앞서 했던 numpy와 호환이 쉽다
### Tensor 생성
### tf.constant()
- list로 생성하기
```
tf.constant([1,2,3])
 >> 결과 : <tf.Tensor: id=1, shape=(3,), dtype=int32, numpy=array([1, 2, 3])>

```
- tuple로 생성하기
```
tf.constant(((1,2,3),(1,2,3)))
 >> <tf.Tensor: id=3, shape=(2, 3), dtype=int32, numpy=
array([[1, 2, 3],
       [1, 2, 3]])>

```
- numpy array로 생성
```
arr=np.array([1,2,3])
tensor=tf.constant(arr)
tensor
 >> <tf.Tensor: id=4, shape=(3,), dtype=int32, numpy=array([1, 2, 3])>
 ```

### Tensor에 담긴 정보 확인
- shape 확인
```
tensor.shape
 >> TensorShape([3])
```

- data type 확인
```
tensor.dtype
 >> tf.int32
```

- data type 정의
```
tensor=tf.constant([1,2,3],dtype=tf.float32)
```
위와 같이 tensor 생성할 때 data type 정의할 수 있음

- data type 변환
    - numpy의 astype()과 같이 TensorFlow에서는 tf.cast
numpy의 astype()
```
arr=np.array([1,2,3],dtype=tf.float32)
arr.astype(np.uint8)
```
tensor의 tf.cast
```
tf.cast(tensor, dtype=tf.uint8)
```

- Tensor에서 Numpy 불러오기
```
tensor.numpy()
 >> array([1., 2., 3.], dtype=float32) 와 같이 tensor를 numpy로 불러옴
```

```
np.array(tensor)
 >> array([1., 2., 3.], dtype=float32) 위와 마찬가지
```
type()를 사용해 numpy array로 변환된 것 확인
```
type(tensor)
 >> tensorflow.python.framework.ops.EagerTensor
type(tensor.numpy())
 >> numpy.ndarray
```


### 난수 생성
![rand](https://github.com/youngDaLee/Deep-learning-Study/blob/master/%ED%8C%A8%EC%8A%A4%ED%8A%B8%EC%BA%A0%ED%8D%BC%EC%8A%A4%EB%94%A5%EB%9F%AC%EB%8B%9D/Part2/img/rand.png?raw=true)
- Nomal Distribution은 중심적인 값. 중심극한 이론에 의해 연속적인 모양
- Uniform Distribution은 불연속적이고 일정하게 분포되어 있음. Uniform Distribution으로 난수를 생성하면 불규칙한 랜덤값이 나온다.

numpy에서는 nomal distribution을 기본적으로 생성
```
np.random.randn(9)
 >> array([ 0.55353788,  1.01172373, -0.06899285, -0.82164259, -1.24852798, -2.60180328,  0.78479722,  0.81358391, -1.70180237])
```

- tf.random.normal
    - TensorFlow에서 Normal Distribution
```
tf.random.normal([3,3])
 >> <tf.Tensor: id=42, shape=(3, 3), dtype=float32, numpy=
array([[ 0.06156063,  0.43525046, -0.35022092],
       [-0.97931534,  1.1286514 , -0.5220305 ],
       [ 0.7653165 , -1.1510981 ,  0.55565506]], dtype=float32)>
```

- tf.random.uniform
    - TensorFlow에서 Uniform Distribution
```
tf.random.uniform([4,4])
 >><tf.Tensor: id=27, shape=(4, 4), dtype=float32, numpy=
array([[0.324759  , 0.25375938, 0.33694983, 0.80128694],
       [0.08134782, 0.09706128, 0.9027542 , 0.53766966],
       [0.9203788 , 0.6004349 , 0.50720656, 0.37506068],
       [0.9644288 , 0.7827195 , 0.28966463, 0.07401979]], dtype=float32)>
```

## dataset(MNIST) 소개 및 물러오기
TensorFlow에서는 기본적으로 dataset을 제공해줌. 여기선 그 중에서도 MNIST 데이터셋으로 연습.

### 불러오기
```
import numpy as np
import matplotlib.pyplot as plt

import tensorflow as tf
from tensorflow.keras import datasets #데이터셋 불러오기

%matplotlib inline
```

```
mnist=datasets.mnist
(train_x, train_y), (test_x, test_y)=mnist.load_data()
```

- data shape 확인
```
train_x.shape
 >>(60000,28,28) #(28,28)의 이미지가 60000개 겹쳐있다는 뜻
```

### Image Dataset
불러온 데이터셋에서 이미지 데이터(train_x) 하나만 뽑아서 시각화하기
- 데이터 하나만 뽑기
```
image=train_x[0]
image.shape
 >> (28,28)
```
- 시각화
```
plt.imshow(image, 'gray') #(28,28,3)처럼 끝에 3이 없는 건 gray계열이라는 뜻. 그래서 이미지 gray로 출력함.
plt.show()
```
![train_x0](https://github.com/youngDaLee/Deep-learning-Study/blob/master/%ED%8C%A8%EC%8A%A4%ED%8A%B8%EC%BA%A0%ED%8D%BC%EC%8A%A4%EB%94%A5%EB%9F%AC%EB%8B%9D/Part2/img/5.png?raw=true)
이렇게 이미지가 출력 됨.
- train_x 에는 이미지 데이터가 들어가 있고
- train_y 에는 이미지의 결과 데이터가 들어가있음
- test_x와 test_y는 train set(학습데이터)의 평가용

### Channel 관련
이미지는 (Batch Size, Height, Width, Channel)의 정보를 담고 있음
여기에서 GrayScale이면 Channel이 1, RGB면 3
 우리가 앞서 했던 train_x의 데이터는(60000,28,28) 이었음. 따라서 BatchSize 60000, Width와 Height는 28인 이미지

- shape로 데이터 확인
```
train_x.shape
 >> (60000,28,28)
```

- 데이터 차원 수 늘리기(numpy)
```
expanded_data=np.expand_dims(train_x,-1)
expanded_data.shape
    >> (60000,28,28,1)
```
-1은 맨 뒤에 붙는다는 뜻이다.

```
expanded_data=np.expand_dims(train_x,0)
expanded_data.shape
    >> (1,60000,28,28)
```
0은 맨 앞에 붙는다는 뜻이다.

```
expanded_data=np.expand_dims(np.expand_dims(train_x,-1),0)
expanded_data.shape
    >> (1,60000,28,28,1)
```
이렇게 앞뒤로 붙일 수 도 있다.

- TensorFlow 패키지를 불러와 데이터 차원 수 늘리기(tensorFlow)
```
new_train_x=tf.expand_dims(train_x,-1)
new_train_x.shape
    >> TensorShape([60000,28,28,1])
```

- tf.newaxis로 데이터 차원 수 늘리기(주로 사용함)
```
train_x[...,tf.newaxis].shape
    >> (60000,28,28,1)
```
이를 활용해
```
new_train_x=train_x[...,tf.newaxis]
```
로 차원 늘림

- reshape로 차원 늘리기
```
reshape=train_x.reshape([60000,28,28,1])
```

+ 주의사항 
    - matplotlib로 시각화 할 때는 gray scale의 이미지는 3번째 dimension, 즉 channel 부분이 비어있다. 따라서 2 dimension으로 차원을 조절해서 넣어줘야 한다.
```
disp=new_train_x[0] #(28,28,1)짜리 이미지

plt.imshow(disp,'gray')
plt.show()
    >> error! 시각화 되지 않음
```
차원 수 줄이는 방법
```
disp=np.squeeze(new_train_x[0]) #(28,28)로 차원 수 줄임
plt.imshow(disp,'gray')
plt.show()
```
![train_x0](https://github.com/youngDaLee/Deep-learning-Study/blob/master/%ED%8C%A8%EC%8A%A4%ED%8A%B8%EC%BA%A0%ED%8D%BC%EC%8A%A4%EB%94%A5%EB%9F%AC%EB%8B%9D/Part2/img/5.png?raw=true)
이렇게 이미지 출력 됨.

### Label Dataset
train_x의 결과 데이터인 train y
```
train_y.shape
    >> (60000,)
```
0차원 숫자 데이터

```
plt.imshow(train_x[0])
plt.show()
```
![train_x0](https://github.com/youngDaLee/Deep-learning-Study/blob/master/%ED%8C%A8%EC%8A%A4%ED%8A%B8%EC%BA%A0%ED%8D%BC%EC%8A%A4%EB%94%A5%EB%9F%AC%EB%8B%9D/Part2/img/Notgray5.png?raw=true)
```
train_y[0]
    >> 5
```
image dataset(train_x[0])의 정답이 5 라는 뜻이다.

- Label 시각화
title을 붙여줌.
```
plt.title(train_y[0])
plt.imshow(train_x[0],'gray')
plt.show()
```
![train_x0](https://github.com/youngDaLee/Deep-learning-Study/blob/master/%ED%8C%A8%EC%8A%A4%ED%8A%B8%EC%BA%A0%ED%8D%BC%EC%8A%A4%EB%94%A5%EB%9F%AC%EB%8B%9D/Part2/img/label5.png?raw=true)


### OneHot Encoding
컴퓨터가 이해할 수 있는 형태로 변환해서 Label을 주는 것.

- tesorflow.keras.utils.to_categorical
```
from tensorflow. keras.utils import to_categorical
```

- 6을 예시로 one hot encording
```
to_categorical(6,10)
    >> array([0., 0., 0., 0., 0., 0., 1., 0., 0., 0.], dtype=float32)
```
10개 중에 6번째 있는 게 1로 바뀜

- train_y 에 label 확인해서 to_categorical 사용
```
label=train_y[0] # label은 5

label_onehot=to_categorical(label,num_classes=10)
label_onehot
    >> array([0., 0., 0., 0., 0., 1., 0., 0., 0., 0.], dtype=float32)
```

- onehot encodiong으로 시각화
```
plt.title(label_onehot)
plt.imshow(train_x[0], 'gray')
plt.show()
```
![train_x0](https://github.com/youngDaLee/Deep-learning-Study/blob/master/%ED%8C%A8%EC%8A%A4%ED%8A%B8%EC%BA%A0%ED%8D%BC%EC%8A%A4%EB%94%A5%EB%9F%AC%EB%8B%9D/Part2/img/onehotencoding5.png?raw=true)