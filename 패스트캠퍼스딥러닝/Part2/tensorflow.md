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


### ���� ����


## dataset(MNIST) �Ұ� �� ��������

