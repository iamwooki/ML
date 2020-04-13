# Application & Tips
## Learing late
- ```Overshooting``` : 높은 learning late로 간격이 넓어짐으로써 내 최적의 W값을 찾지 못할 수도 있음 
  - (발산) 그래프를 튀어나가 숫자가 아닌 값이 나타날 수도 있
- ```Small learning``` : 최저점이 아님에도 불구하고 시간이 다되 멈출 수도 있음
  - 작은 값의 변화만 있을 경우 learning rate를 올림
- 보통 시작을 0.01로 시작해 발산하거나 느리게 변화할 때 값을 변경해 나감

## Data (X) 선처리 for gradient descent
- ```normalize``` : 보통 사용하는 방식 데이터 중심이 0으로 가기 위한 (zero-centered data)

## Overfitting
- training data set(with memorization)에 너무 적합하게 학습이 되어서 새로운 data에 대해 학습이 제대로 되지 않을 수 있음
  - More training data!
  - features 수 줄이기 (중복되는 것이 있다면 줄여볼 것)
  - ```Regularization``` : Weight이 작아질 수록 구부러짐, 따라서 기존 Loss = 1/n∑_i D(S(Wxi+b), Li) +   λ∑w^2   (  λ : regualzation strength 이 값이 0이되면 쓰지 않고 값이 커지면 regualzarization을 중요시 여긴다라는 의미)
  ```python
  #Reularization
  l2reg = 0.001 * tf.reduce_sum(tf.square(W))
  ```
## Performance Evaluation 
- ```training set```-> ```model```->```test set```(training set의 예측값 Y와 test set의 실제 값 Y의 비교를 통해 확인)
  - <-----------Original Set------------>
  - ---------Training---------  -Testing -
  - --Training--  --Validation-  -Testing-
  - =>validation을 통해 기존에 training으로 학습된 값을 튜닝시켜, testing dataset(only one test)으로 모델이 동작하는지 확인
- ```Online learning``` : ex) 100만개의 데이터중 10만개씩 잘라서 순차적으로 학습시킴, 학습모델의 경우 기존에 학습된 모델을 기반으로 학습시켜나감
## ref
- [lec 07-1: 학습 rate, Overfitting, 그리고 일반화 (Regularization)](https://www.youtube.com/watch?v=1jPjVoDV_uo&feature=youtu.be)
