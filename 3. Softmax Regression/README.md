# Logistic Classficiation

### Classification
##### Binary
- 둘 중 한개의 카테고리를 고르는 것 ex) Spam Detection : Spam or Ham
- 0,1 encoding  -> H(x) = Wx + b가 간단하고 좋지만 0~1 사이에 값으로 변환시키고 싶음
  - z=Wx+b => g(z) = 0 ~1
- 두번째 가설,```Sigmoid function(logistic function)``` : g(z)= 1 / (1+e^-z) => H(X) = 1 / 1+ e^-(W^Transpose * X)
#### New Cost function
- ```cost(W) = 1/m∑(H(x),y)```
- ```c(H(x),y) = y=1) -log(H(x)) y=0 -log(1-H(x))``` // log를 사용하는 이유는 exp func가 반대이므로 상쇄
- 정리 ```C(H(x),y) = -ylog(H(x)) - (1-y)log(1-H(X))```
```python
#cost function
cost = tf.reduce_mean(-tf.reduce_sum(Y*tf.log(hypothesis) + (1-Y)*tf.log(1-hypothesis)))

# Minimize
a = tf.Variable(0.1) #learning rate
optimizer = tf.train.GradientDescentOptimizer(a)
train = optimizer.minimize(cost)
```
## ref
- [ML lec 5-1: Logistic Classification의 가설 함수 정의](https://www.youtube.com/watch?v=PIjno6paszY&feature=youtu.be)
- [ML lec 5-2 Logistic Regression의 cost 함수 설명](https://www.youtube.com/watch?v=6vzchGYEJBc)
