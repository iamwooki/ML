# Basic
from https://hunkim.github.io/ml/
## tf_version issue
- v1.x 호환문제
```python
import tensorflow.compat.v1 as tf
tf.disable_v2_behavior()
```

## Computational Graph
1. 그래프 빌드
```python
node1 = tf.constant(3.0, tf.float32)
node2 = tf.constant(4.0)
node3 = tf.add(node1, node2)
```
2. 세션 생성
```python
sess = tf.Session()
```
3. 세션 실행
```python
print(sess.run(node3))
```

## placeholder
1. placeholder build
```python
a = tf.placeholder(tf.float32)
b = tf.placeholder(tf.float32)
adder_node = a + b # tf.add(a,b) //op
```
2. 세션 생성
```python
sess = tf.Session()
```
3. 세션 실행
#### feed_dict : placeholder의 경우 위에 생성해둔 것 외에 값을 알지 못함 따라서 feed_dict를 통해 값을 넘겨줌
```python
#sess.run(op, feed_dict={x: x_data})
print(sess.run(adder_node, feed_dict={a: 3, b:4.5}))
print(sess.run(adder_node, feed_dict={a: [1,3], b:[2,4]}))
```

## Rank, Shape, Data type
#### Math entity: rank
- Scalar    : 0
- Vector    : 1
- Matrix    : 2
- 3-Tensor  : 3
- n-Tensor  : n

#### Shape : 각 몇개의 요소가 있는지 (배열 생각) [3,3] : 3차원 텐서에 3개의 요소

#### Data type : 대부분 tf.float32, tf.int32 사용

#### Reduce mean / Reduce sum
```python
x = [[1. , 2.],  # ->axis =1
     [3. , 4.,]]
#     |
#     V
#   axis=0
tf.reduce_mean([1,2]. axis=0).eval() #축에 따른 평균
tf.reduce_mean(x).eval()  # 모든 값의 평균
```
#### Argmax : 맥시멈 값의 위치를 나타내줌
```python
x = [[0,1,2], [2,1,0] ]
tf.argmax(x, axis=0).eval() # axis=0이므로 가로기준 가장 큰 값
```
#### Reshape
```python
t = [[[ ~~~ ]]]
tf.reshape(t, shape =[-1,3]).eval()
```
##### squeeze
##### expand

#### One hot
#### Casting
```python
tf.cast([1.8, 2.2, 3.3, 4.9]. tf.int32).eval()

tf.cast([True, False, 1==1, 0==1], tf.int32).eval()
```

#### Stack

#### Ones and Zeros like
```python
x = [[0, 1, 2], [2, 1, 0]] #이라 하면 이 모양에 맞게
tf.ones_like(x).eval()# => [[1,1,1] , [1,1,1]]
tf.zeros_like(x).eval()#=> [[0,0,0] , [0,0,0]]
```

#### Zip
```python
for x, y  in zip([1,2,3],[4,5,6]):
     print(x,y)
#1 4
#2 5
#3 6
for x, y. z in zip([1,2,3], [4,5,6], [7,8,9]):
    print(x,y,z)
#1 4 7
#2 5 8
#3 6 9
```

## ref
- [ML lab 01 - TensorFlow의 설치및 기본적인 operations (new)](https://www.youtube.com/watch?v=-57Ne86Ia8w&feature=youtu.be)
