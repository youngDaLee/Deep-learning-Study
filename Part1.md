# 인공지능 개념 이해

## 딥러닝 용어

- Model : cnn이 모델이다. 이 모델을 학습시키고자 하는 것. 모델 안에서 특징을 뽑아내고 예측을 한다.
- Layer : 레이어를 여러 층을 쌓았다고 해서 딥러닝이라고 함. inputlayer-hidden layer-ouput layter 연결이 어떻게 되어있느냐가 핵심.
- Convolution : CNN에서 C가 Convolution. 합성곱 이라는 뜻. 이미지가 어떤 필터를 받으면 하나하나 곱한다. 그러면 다른 결과가 나옴.
- Weight : 학습하려는 대상. 목적에 따라 다른 weight 학습 시켜야 함./Filter/Kernel/Variavle/Bias
- output=Weight*input+Bias
- Pooling Layer : 압축을 함. 이미지를 압축. 이미지가 가지고 있는 가장 큰 특징들을 반 사이즈의 이미지로 줄여준다. **압축한다**
- Optimization : 학습시키고 최적화로 찾아가는거. Loss 최소로 줄이고 싶어서 업데이트... 어떻게 하면 Loss를 줄일 수 있을까 도와준다.
- Activation Funtion : 앞에서 특징을 뽑았으면 불필요한 값 제거함. ReLU에 익숙해지자.
- Softmax : 최종 마지막에 컴퓨터가 예측. 앞에서 받은 값들을 확률로 나타내 줄 수 있게 하는 것
- Loss(Cost) : Lost(Cost) Funtion에서 나온 값/Loss(Cost) Funtion : 얼마나 틀렸는지 계산하는 방식
- Learning Rate
- Batch Size : 몇 장을 넣어줄거냐 정하는게 배치사이즈.
- Epoch : 인공지능은 Epoch수 만큼 데이터를 반복해서 본다./Step
- Train/Validation/Test
- Label/Ground Truth : 정답