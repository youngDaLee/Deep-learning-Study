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
![train_x0]()

### Channel 관련


### Label Dataset


### OneHot Encoding

