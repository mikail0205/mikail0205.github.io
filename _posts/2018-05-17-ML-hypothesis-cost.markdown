---
title: Machine Learning[머신러닝] Hypothesis, cost
description:
categories:
 - Machine Learning
tags: ML
---

#### Linear Regression

Linear Regression 학습을 한다는 것은 Hypothesis(가정)이 필요하다. 
세상의 많은 현상들이 linear 한 것으로 설명되는 경우가 많음. 
공부를 많이 하면 성적이 오른다거나, 운동을 열심히 하면 달리기가 빨라진다거나. 물론 단순한 문제에 대해서만 동작한다. 실제로 일들이 그렇게 단순하지는 않기 때문. 다양한 경우에 따른 시도들를 하나로 묶는 것을 Neural Network(신경망)라고 한다.

#### Hypothesis (가설)
 Machine Learning의 문제 Regression & Classification을 풀기 위해 만들어 본 공식. 예측(Regression) 하거나 분류(Classification)를 하기 위해 선을 그어 보는 것. 선을 1차원, 2차원 또는 다차원 함수로 정의 함. 최적의 Hypothesis 함수를 찾는 것이 Machine Learning의 해답.
H(x) = Wx + b가 될 것이라고 가설을 세우는 것이 1단계가 되겠다. 그리고 어떤 선이 가장 적합한가를 찾는 것.

![](https://postfiles.pstatic.net/MjAxODA1MTRfMjA1/MDAxNTI2Mjk3OTI4MTU2.5411Q9Ar2IaqOqw_LuCbJcTOov1kYH7eC7upa8b9Zgcg.AnfX6HT0EpzXOnTTC3sEU9ofOTKBSxmvY0GYOQtqQI4g.PNG.goddam0205/2018-05-14.png?type=w773)
간단한 그림에서 사람은 쉽게 판단하지만, 컴퓨터는 계산이 필요하다. 복잡한(다차원) 그림에서 사람은 눈으로 판단하지 못하지만 컴퓨터는 계산을 통해 판단할 수 있다.

#### Cost(= Loss) : 가설의 오차.
학습 과정에서 Hypothesis와 실제 결과(training data)와의 차이들의 합. 우리가 세운 가설과 실제 데이터가 얼마나 다른가? Cost가 작을수록 즉, 오차가 작을수록 정답에 가까워진다. 가장 Cost가 작은 것이 머신러닝의 해답. but overfitting(과적합)문제를 조심해야 한다.
#### Overfitting (과적합)
Overfitting(과적합)은 training data를 과하게 잘 학습하는 것을 말한다. 학습 데이터에 대해 과하게 학습하여 실제 데이터에 대한 오차가 증가하는 현상. 
**examples:** 
1. 특정한 색의 고양이로 학습을 했더니, 다른 색의 고양이는 고양이로 인식하지 못하는 경우. 
2. 연습경기는 잘 하는데 실전은 못하는 경우. 
3. 사람으로 생각하면 편견을 가지거나 너무 섬세한 경우.