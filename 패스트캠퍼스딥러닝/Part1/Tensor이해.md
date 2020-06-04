# Tensor
![tensor](https://github.com/youngDaLee/Deep-learning-Study/blob/master/%ED%8C%A8%EC%8A%A4%ED%8A%B8%EC%BA%A0%ED%8D%BC%EC%8A%A4%EB%94%A5%EB%9F%AC%EB%8B%9D/Part1/img/TensorImg1.png?raw=true)
- scalar: 일반적으로 그냥 존재하는 값(1개) 0차원
- vector: 스칼라가 여러 개 모인 것 1차원
- matrix: 벡터가 여러 개 모인 것 2차원
- 3-tensor:matrix가 모인 것 3차원
- n-tensor   
- [출처](https://rekt77.tistory.com/102)

이와같이 tensor는 차원과 관련이 있음. tensor와 같은 고차원적인 데이터를 다루기 쉽게 만들어진 것이 Numpy.

# Numpy

## 0차원
```
import numpy as np
arr=np.array(5) 
arr.shape #결과 : () -아무것도 없음
arr.ndim #차원 -> 0
arr #array(5)
```

## 1차원
```
#[]리스트를 한번 씌우면 차원이 생김
arr=np.array([5]) #1차원
arr.shape #(1,) ->n개 숫자 : n차원, 값이 a:n차원에 a개의 값이 들어감
arr=np.array([1,2,3])
arr.shape #(3,)
arr.ndim #1
arr #array([1,2,3])
```

## 2차원
```
arr=np.array([[1,2,3]]) #2차원
arr.shape #(1,3) ->2차원 원소 1개, 1차원 원소 3개
arr.ndim #2
arr #array([[1,2,3]])
```
## 다차원
```
arr=np.array([[[[1,2,3],[1,2,3],[1,2,3],[1,2,3]]]])
arr.shape #(1,1,4,3)
```
