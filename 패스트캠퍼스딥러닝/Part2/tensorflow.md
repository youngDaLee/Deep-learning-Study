# Tensorflow
## ����
- 1�������� ���� ��������(�츮�� �ϴ°� 2����)
- Numpy Array�� ȣȯ�� ����
- TensorBoard : Tensorflow�� ����ϴ� �ֵ� ����. �߰��� �󸶳� �н��� �ǰ� �ִ���, �ð�ȭ�� ����ϱ� ���ؼ��� TensorBoard �̿�
- TFLite : �ȵ���̵� ����ϴ� ������� ���� ����Ѵ� ��
- TPU : ����Ŭ��?�� ����� �� TPU�� ����ϸ� �н��ӵ��� �������� ��.
- ������ ���� ����ڵ��� ���

## Tensorflow ���� ����
- �ռ� �ߴ� numpy�� ȣȯ�� ����
### Tensor ����
### tf.constant()
- list�� �����ϱ�
```
tf.constant([1,2,3])
 >> ��� : <tf.Tensor: id=1, shape=(3,), dtype=int32, numpy=array([1, 2, 3])>

```
- tuple�� �����ϱ�
```
tf.constant(((1,2,3),(1,2,3)))
 >> <tf.Tensor: id=3, shape=(2, 3), dtype=int32, numpy=
array([[1, 2, 3],
       [1, 2, 3]])>

```
- numpy array�� ����
```
arr=np.array([1,2,3])
tensor=tf.constant(arr)
tensor
 >> <tf.Tensor: id=4, shape=(3,), dtype=int32, numpy=array([1, 2, 3])>
 ```

### Tensor�� ��� ���� Ȯ��
- shape Ȯ��
```
tensor.shape
 >> TensorShape([3])
```

- data type Ȯ��
```
tensor.dtype
 >> tf.int32
```

- data type ����
```
tensor=tf.constant([1,2,3],dtype=tf.float32)
```
���� ���� tensor ������ �� data type ������ �� ����

- data type ��ȯ
    - numpy�� astype()�� ���� TensorFlow������ tf.cast
numpy�� astype()
```
arr=np.array([1,2,3],dtype=tf.float32)
arr.astype(np.uint8)
```
tensor�� tf.cast
```
tf.cast(tensor, dtype=tf.uint8)
```

- Tensor���� Numpy �ҷ�����
```
tensor.numpy()
 >> array([1., 2., 3.], dtype=float32) �� ���� tensor�� numpy�� �ҷ���
```

```
np.array(tensor)
 >> array([1., 2., 3.], dtype=float32) ���� ��������
```
type()�� ����� numpy array�� ��ȯ�� �� Ȯ��
```
type(tensor)
 >> tensorflow.python.framework.ops.EagerTensor
type(tensor.numpy())
 >> numpy.ndarray
```


### ���� ����
![rand](https://github.com/youngDaLee/Deep-learning-Study/blob/master/%ED%8C%A8%EC%8A%A4%ED%8A%B8%EC%BA%A0%ED%8D%BC%EC%8A%A4%EB%94%A5%EB%9F%AC%EB%8B%9D/Part2/img/rand.png?raw=true)
- Nomal Distribution�� �߽����� ��. �߽ɱ��� �̷п� ���� �������� ���
- Uniform Distribution�� �ҿ������̰� �����ϰ� �����Ǿ� ����. Uniform Distribution���� ������ �����ϸ� �ұ�Ģ�� �������� ���´�.

numpy������ nomal distribution�� �⺻������ ����
```
np.random.randn(9)
 >> array([ 0.55353788,  1.01172373, -0.06899285, -0.82164259, -1.24852798, -2.60180328,  0.78479722,  0.81358391, -1.70180237])
```

- tf.random.normal
    - TensorFlow���� Normal Distribution
```
tf.random.normal([3,3])
 >> <tf.Tensor: id=42, shape=(3, 3), dtype=float32, numpy=
array([[ 0.06156063,  0.43525046, -0.35022092],
       [-0.97931534,  1.1286514 , -0.5220305 ],
       [ 0.7653165 , -1.1510981 ,  0.55565506]], dtype=float32)>
```

- tf.random.uniform
    - TensorFlow���� Uniform Distribution
```
tf.random.uniform([4,4])
 >><tf.Tensor: id=27, shape=(4, 4), dtype=float32, numpy=
array([[0.324759  , 0.25375938, 0.33694983, 0.80128694],
       [0.08134782, 0.09706128, 0.9027542 , 0.53766966],
       [0.9203788 , 0.6004349 , 0.50720656, 0.37506068],
       [0.9644288 , 0.7827195 , 0.28966463, 0.07401979]], dtype=float32)>
```

## dataset(MNIST) �Ұ� �� ��������
TensorFlow������ �⺻������ dataset�� ��������. ���⼱ �� �߿����� MNIST �����ͼ����� ����.

### �ҷ�����
```
import numpy as np
import matplotlib.pyplot as plt

import tensorflow as tf
from tensorflow.keras import datasets #�����ͼ� �ҷ�����

%matplotlib inline
```

```
mnist=datasets.mnist
(train_x, train_y), (test_x, test_y)=mnist.load_data()
```

- data shape Ȯ��
```
train_x.shape
 >>(60000,28,28) #(28,28)�� �̹����� 60000�� �����ִٴ� ��
```

### Image Dataset
�ҷ��� �����ͼ¿��� �̹��� ������(train_x) �ϳ��� �̾Ƽ� �ð�ȭ�ϱ�
- ������ �ϳ��� �̱�
```
image=train_x[0]
image.shape
 >> (28,28)
```
- �ð�ȭ
```
plt.imshow(image, 'gray') #(28,28,3)ó�� ���� 3�� ���� �� gray�迭�̶�� ��. �׷��� �̹��� gray�� �����.
plt.show()
```
![train_x0]()

### Channel ����


### Label Dataset


### OneHot Encoding

