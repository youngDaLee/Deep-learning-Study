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


### 난수 생성


## dataset(MNIST) 소개 및 물러오기

