본격적으로 computation graph에 들어가기 전에 logistic regresion, nn보다 쉬운 것으로 예를 들어보자.
$$J(a,b,c)=3(a+bc)$$
위 식을 계산하기 위해서는 세 단계 과정이 필요하낟.

1. $bc$를 계산해서 $u$에 넣는다.
   - $u=bc$
2. $a+u$를 계산해서 $v$에 넣는다
   - $v=a+u$
3. 출력값 $J$ - $J=3v$
   위의 세 단계를 다음과 같이 computation graph로 나타낼 수 있다.
   ![cg](./img/computationGraph.png)
   이런 Computation Graph(계산 그래프)는 특정 변수를 Optimization(최적화)할 때 유용하다.
