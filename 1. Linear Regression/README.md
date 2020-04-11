# Regression

#### Cost(Loss) function
- 우리가 세운 가설과 실제 데이터가 얼마나 차이나는지 ```H(x)-y```
- ```H(x) = Wx + b```
- 간단한 가설 : ```cost(W,b) = 1/m * ∑_i=1 ^m ( H(x^i)-y^i )^2```
  - (Convex function 모양인지 확인이 되면 cost function의 설계가 제대로 된 것)
- Goal : minimize cost(W,b) 

##### Gradient descent algorithm (경사하강법)
- cost function 최소화
- 머신러닝에 minimization problems에 사용
- U 형태의 그래프에서 경사도가 0인 지점에 도착하는 것
  - 아무지점에서 시작해서 W를 reduce cost(W,b) U자형 그래프
 - Formal definition ```W:= W - a* å/åW * cost(W), a: learning rate```
  - ``` W: W -a* 1/m * ∑_i=1 ^ m (Wx^i-y^i)x^i```

#### Multi-variable
- ```H(x1,x2,x3, ... , xn) = w1x1 + w2x2 + w3x3 + ... + wnxn+  b``` 



## ref
- [ML lec 02 - Linear Regression의 Hypothesis 와 cost 설명](https://www.youtube.com/watch?v=Hax03rCn3UI)
- [ML lec 03 - Linear Regression의 cost 최소화 알고리즘의 원리 설명](https://www.youtube.com/watch?v=TxIVr-nk1so)
- [ML lab 03 - Linear Regression 의 cost 최소화의 TensorFlow 구현 (new)](https://youtube.com/watch?v=Y0EF9VqRuEA)
- [ML lec 04 - multi-variable linear regression (*new)](https://www.youtube.com/watch?v=kPxpJY6fRkY&t=15s)
