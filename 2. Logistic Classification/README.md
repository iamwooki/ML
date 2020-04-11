# Logistic Classficiation

### Classification
##### Binary
- 둘 중 한개의 카테고리를 고르는 것 ex) Spam Detection : Spam or Ham
- 0,1 encoding  -> H(x) = Wx + b가 간단하고 좋지만 0~1 사이에 값으로 변환시키고 싶음
  - z=Wx+b => g(z) = 0 ~1
- ```Sigmoid function(logistic function)``` : g(z)= 1 / (1+e^-z)

## ref
- [ML lec 5-1: Logistic Classification의 가설 함수 정의](https://www.youtube.com/watch?v=PIjno6paszY&feature=youtu.be)
