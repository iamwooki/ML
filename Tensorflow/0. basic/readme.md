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
