# Tensor
![tensor](https://github.com/youngDaLee/Deep-learning-Study/blob/master/%ED%8C%A8%EC%8A%A4%ED%8A%B8%EC%BA%A0%ED%8D%BC%EC%8A%A4%EB%94%A5%EB%9F%AC%EB%8B%9D/Part1/img/TensorImg1.png?raw=true)
- scalar: �Ϲ������� �׳� �����ϴ� ��(1��) 0����
- vector: ��Į�� ���� �� ���� �� 1����
- matrix: ���Ͱ� ���� �� ���� �� 2����
- 3-tensor:matrix�� ���� �� 3����
- n-tensor   
- [��ó](https://rekt77.tistory.com/102)

�̿Ͱ��� tensor�� ������ ������ ����. tensor�� ���� ���������� �����͸� �ٷ�� ���� ������� ���� Numpy.

# Numpy

## 0����
```
import numpy as np
arr=np.array(5) 
arr.shape #��� : () -�ƹ��͵� ����
arr.ndim #���� -> 0
arr #array(5)
```

## 1����
```
#[]����Ʈ�� �ѹ� ����� ������ ����
arr=np.array([5]) #1����
arr.shape #(1,) ->n�� ���� : n����, ���� a:n������ a���� ���� ��
arr=np.array([1,2,3])
arr.shape #(3,)
arr.ndim #1
arr #array([1,2,3])
```

## 2����
```
arr=np.array([[1,2,3]]) #2����
arr.shape #(1,3) ->2���� ���� 1��, 1���� ���� 3��
arr.ndim #2
arr #array([[1,2,3]])
```
## ������
```
arr=np.array([[[[1,2,3],[1,2,3],[1,2,3],[1,2,3]]]])
arr.shape #(1,1,4,3)
```
