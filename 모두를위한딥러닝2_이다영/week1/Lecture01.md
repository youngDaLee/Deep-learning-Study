Doker Instruction
===
## Doker란?
#### Container-based virtualization System
컨테이너 기반의 가상화 시스템
- Virtualizetion(가상화) : 현실에 존재하지 않은 것을 마치 있는 것 처럼 보이게 해 주는 기술.
    - 내 컴퓨터에 실제로는 하드디스크 1개인데 partition을 나눠 C드라이브와 D드라이브 2 개가 있는 것 처럼 보이게
    - 컴퓨터 안에 가상의 컴퓨터(virtual box 이용해 윈도우 안에 윈도우, 윈도우 안에 리눅스)
    - 클라우드 시작의 핵심기술. 서버를 쪼개서 가격을 저렴하게.
        - 컴퓨터 하나에 운영체제 여러 개 한꺼번에 돌리니 서로 치여서 느려짐.
        - 서버 많이 쓰는 애들 모두 리눅스인데.. 하나로 퉁치는 방법이 바로 **DOKER** 

- pythorch와 tensorflow 설치할 필요 없이 doker 설치하면 ok. 나는 tensorflow 설치했으니 doker 설치 할 필요 없음.    



Lecture 01
====
What is ML(Machine Learning)?
---
머신러닝이란?
- explicit programming : 이런 환경에는 이렇게 반응해라 하고 이미 프로그램을 만들어 놓은 것.    
어떤 경우에서는 explicit 하게 반응 할 수 없음
 - Spam filter : 경우의 수가 너무 ㅁ낳음
 - Automatic driving : 마찬가지로 경우의 수가 너무 많음

이를 개선하기 위해 개발자가 일일히 어떻게 할 지를 정하지 말고 **프로그램이 학습하게** 능력을 갖는 프로그램을 머신러닝이라 한다. -by. Arthur Samuel

What is learning?
---
학습을 하기 위해 어떤 데이터를 미리 주어져야 함.
> ### SuperVised learning
정해져 있는 데이터(레이블들이 지정되어 있는 데이타)-training set-을 갖고 학습을 하는 것
- 얘가 고양이일까 개일까? 맞추는 프로그램.
 - 사람들이 고양이 이미지를 준다.
 - 그 고양이 사진을 보고 학습을 한다.(이미 고양이 label이 있는 사진)    

#### 일반적인 문제의 ML
- Imane labeling
- Email spam filter : 얘가 스팸메일인가?
- Predicting exam score : 시험 성적 예측

#### Training data set
![Alt text](C:\Users\ldy09\Documents\Deep-learning-Study\모두를위한딥러닝2/lec01공부.png)
- ML을 학습시켜주는 데이터셋.    

- 알파고의 바둑판 학습시 사용된 데이터


> ### Unsupervised learning
supervised와 반대로 미리 label을 나누기 힘든 경우. 데이터를 보고 스스로 학습함
- Google news grouping
- Word clustering

what is regression?
---
공부 한 시간에 따라 시험의 성적을 예측하는 시스템을 만들 때.   
0~100처럼 굉장히 넓은 범위에서 예측하는 것을 regression이라 함


What is classification?
---
regression은 범위가 넓은데, 이를 추상화(classification)해서 예측함.
> #### Binary classification
p/np처럼 두 가지 경우로 나눔. 둘 중에 하나를 고르는 문제.

> #### multi-label classification
성적(A,B,C,D,F) 중 하나를 고르는 문제 처럼 label이 많은 경우.
