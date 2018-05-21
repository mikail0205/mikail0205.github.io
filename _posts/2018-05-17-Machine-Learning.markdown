---
title: Machine Learning[머신러닝] 개념
description:
categories:
 - Machine Learning
tags: ML
---

![](https://community-cdn-digitalocean-com.global.ssl.fastly.net/assets/tutorials/images/large/introduction-to-machine-learning_social.png "Machine Learning")

### AI(인공지능) ≒  Machine Learning(머신러닝)이라고 생각해도 된다. 
인공지능의 한 분야로 컴퓨터가 학습하는 알고리즘과 기술이기 때문이며 거기서 더 발전한 것이 Deep Learning(딥러닝) 혹은 DNN(Deep Neural Network)이다.
Deep Learning의 개념자체는 이미 수십년 전에 있었지만 DL에 대한 이론적인 결과가 전무했다는 점도 있고 그 당시 컴퓨터로는 처리할 엄두조차 낼 수 없었기 때문.

### Artificial intelligence / Machine Learning / Deep Learning
1956년 처음으로 A.I(인공지능)이라는 개념이 등장했다. 영화 등에서 보는 사람과 같은 AI는 general AI/strong AI라고 한다. 하지만 현재 기술 수준에서 만들 수 있는 AI는 narrow AI/weak AI(특정한 일을 사람보다 뛰어난 능력으로 수행하는 AI) 의 개념에 포함된다. 
기본적으로 Machine Learning은 알고리즘을 이용해 데이터를 분석하고 분석을 통해 학습하며, 학습한 내용을 기반으로 판단이나 예측을 한다. 대량의 데이터와 알고리즘을 통해 컴퓨터 그 자체를 학습시켜 작업 수행 방법을 익히는 것을 목표로 한다. 
Deep Learning은 Neural Network(인공신경망)에서 발전한 형태의 인공 지능으로, 뇌의 뉴런과 유사한 정보를 입출력 계층을 활용해 데이터를 학습한다. 그리고 hidden layer가 1개 보다 많으면 'deep'하다라고 한다. 

> Machine Learning : "Field of study that gives computers the ability to learn without being explicitly programmed" Auther Samuel (1959)

### Why Machine Learning? 
Explicit programming(명시적 프로그래밍)의 한계.  : SPAM filter, Automatic driving 등 너무 많은 규칙을 필요로 한다. 그렇다면 프로그램 자체가 어떤 데이터를 보고 학습하는 능력을 갖추면 어떨까?
문제를 해결하기 위한 맞춤 코드(custom code)를 작성하지 않고도 일련의 데이터에 대해 무언가 흥미로운 것을 알려줄 수 있는 일반 알고리즘(Generic algorithms)이 있다는 아이디어.

### Machine Learning은 근본적으로 두 가지 문제를 해결하기 위한 것이다. 
**Regression(회귀)** : 현재의 샘플링 데이터를 바탕으로 미래에 올 데이터를 예측하는 것. 주식 가격 변동을 보고 가격 예측, 시간대별 IT 시스템의 부하 예측 등

**Classification(분류)** : 데이터를 몇 가지 특성을 가진 그룹으로 분류하는 것. 사진을 보고 사물 식별, 사람 얼굴 인식.
공부한 시간을 바탕으로 시험 성적을 예측할 때 
1. 점수(0 ~ 100)으로 하면 : regression
2. 통과 or not으로 하면 : binary classification
3. 문자 (A, B, C, D, E and F)로 하면 : multi-label classification이라 한다.

### 세가지 학습 방법 Supervised / Unsupervised / Reinforcement Learning

![](http://solarisailab.com/wp-content/uploads/2017/06/supervsied_unsupervised_reinforcement.jpg)

**Supervised learning (지도 학습)** : Learning with labeled examples. Label이 붙은 학습을 위한 데이터(training data)가 존재하고 그 데이터로 학습을 하는 것이다. 즉 답이 구성된 데이터(문제)로 알고리즘을 훈련시킨다는 것이며 패턴을 찾아내서 새롭운 데이터(문제)의 답을 찾아내는 것.
알파고도 기존의 바둑 기보를 보고 학습을 하고, 그것을 바탕으로 이세돌 선수가 바둑을 두었을 때 대처를 한 것. 따라서 알파고도 Supervised learning이라고 할 수 있다.

**Unsupervised learning (비지도 학습)** : Label을 정해주기 어려울 때, data를 보고 스스로 학습한다. 특성이 비슷한 데이터를 합쳐서 group으로 분류하는 학습 방법이다. 비지도 학습은 label이 없는 데이터를 사용하며 데이터 안에서 관계를 찾아내는 것을 목적으로 한다. 따라서 사람의 개입이 없어 컴퓨터 스스로 데이터를 훈련하는 것이다. 그래서 비지도라고 한다. 하지만 대부분의 데이터가 label이 없는 형태이기 때문에 앞으로 machine learning이 나아가야 할 방향이라고 한다.

**Reinforcement learning (강화 학습)** : 앞선 두 가지 학습과는 다른 종류의 학습 알고리즘이다. 앞선 두 가지 학습은 데이터가 주어진 상태로 시작을 하지만 강화 학습은 데이터를 수집하는 과정까지 포함을 한다. 
주어진 환경에서 행동을 취하고 그로부터 보상을 얻으면서 학습을 진행하게 된다. 

### Reference
**main image**: https://www.digitalocean.com/community/tutorials/an-introduction-to-machine-learning

