---
title: Machine Learning[머신러닝] 개념
description:
date: 2018-05-17
categories:
 - Machine Learning
tags: ML
---

![](https://community-cdn-digitalocean-com.global.ssl.fastly.net/assets/tutorials/images/large/introduction-to-machine-learning_social.png "Machine Learning")

## What is Machine Learning?
집사 로봇이라던가 터미네이터를 떠올릴 수 있겠지만, 이미 우리 주변에 많이 자리 잡아 있다. 수십 년간 사용되온 스팸 필터 역시 머신 러닝이라 할 수 있다. 이후 추천이나 음성 검색 등으로 발전 했다.

AI(인공지능) ≒  Machine Learning(머신러닝)이라고 생각해도 된다. 인공지능의 한 분야로 컴퓨터가 학습하는 알고리즘과 기술이기 때문이며 거기서 더 발전한 것이 Deep Learning(딥러닝) 혹은 DNN(Deep Neural Network)이다. Deep Learning의 개념자체는 이미 수십년 전에 있었지만 DL에 대한 이론적인 결과가 전무했다는 점도 있고 그 당시 컴퓨터로는 처리할 엄두조차 낼 수 없었기 때문.
> Machine Learning : "Field of study that gives computers the ability to learn without being explicitly programmed" Auther Samuel (1959)
> “A computer program is said to learn from experience E with respect to some of tasks T and performance measure P, if its performance at tasks in T, as measured by P, improves with experience E” Tom Mitchell (1997)

## Artificial intelligence / Machine Learning / Deep Learning
1956년 처음으로 A.I(인공지능)이라는 개념이 등장했다. 영화 등에서 보는 사람과 같은 AI는 general AI/strong AI라고 한다. 하지만 현재 기술 수준에서 만들 수 있는 AI는 narrow AI/weak AI(특정한 일을 사람보다 뛰어난 능력으로 수행하는 AI) 의 개념에 포함된다.
기본적으로 Machine Learning은 알고리즘을 이용해 데이터를 분석하고 분석을 통해 학습하며, 학습한 내용을 기반으로 판단이나 예측을 한다. 대량의 데이터와 알고리즘을 통해 컴퓨터 그 자체를 학습시켜 작업 수행 방법을 익히는 것을 목표로 한다.
Deep Learning은 Neural Network(인공신경망)에서 발전한 형태의 인공 지능으로, 뇌의 뉴런과 유사한 정보를 입출력 계층을 활용해 데이터를 학습한다. 그리고 hidden layer가 1개 보다 많으면 'deep'하다라고 한다.

## Why Machine Learning?
Explicit programming(명시적 프로그래밍)의 한계.  : SPAM filter, Automatic driving 등 너무 많은 규칙을 필요로 하며 단순하지 않아서 점점 길고 복잡해지므로 유지 보수하기도 매우 힘들어진다. 그렇다면 프로그램 자체가 어떤 데이터를 보고 학습하는 능력을 갖추면 어떨까? 문제를 해결하기 위한 맞춤 코드(custom code)를 작성하지 않고도 일련의 데이터에 대해 무언가 흥미로운 것을 알려줄 수 있는 일반 알고리즘(Generic algorithms)이 있다는 아이디어.
머신러닝은 다음과 같은 분야에서 뛰어난 모습을 보이는데
1. 많은 수동 조정과 규칙이 필요한 문제
2. 전통적인 방법으로는 해결 방법이 없는 복잡한 문제
3. 유동적인 환경
4. 복잡한 문제와 대량의 데이터

머신러닝 기술을 적용하면 겉으로는 보이지 않던 패턴을 발견할 수 있는데. 이를 데이터 마이닝(data mining)이라 한다.

## Machine Learning은 근본적으로 두 가지 문제를 해결하기 위한 것이다. 
**Regression(회귀)** : 현재의 샘플링 데이터를 바탕으로 미래에 올 데이터를 예측하는 것. 주식 가격 변동을 보고 가격 예측, 시간대별 IT 시스템의 부하 예측 등

**Classification(분류)** : 데이터를 몇 가지 특성을 가진 그룹으로 분류하는 것. 사진을 보고 사물 식별, 사람 얼굴 인식.
공부한 시간을 바탕으로 시험 성적을 예측할 때
1. 점수(0 ~ 100)으로 하면 : regression
2. 통과 or not으로 하면 : binary classification
3. 문자 (A, B, C, D, E and F)로 하면 : multi-label classification이라 한다.

## 세가지 학습 방법 Supervised / Unsupervised / Reinforcement Learning

![](http://solarisailab.com/wp-content/uploads/2017/06/supervsied_unsupervised_reinforcement.jpg)
**Supervised learning (지도 학습)** : Learning with labeled examples. Label이 붙은 학습을 위한 데이터(training data)가 존재하고 그 데이터로 학습을 하는 것이다. 즉 답이 구성된 데이터(문제)로 알고리즘을 훈련시킨다는 것이며 패턴을 찾아내서 새로운 데이터(문제)의 답을 찾아내는 것. Classification(분류)가 전형적인 지도학습 작업이 되며 스팸 필터가 좋은 예이다. 많은 메일 샘플로 학습하여(스팸인지 아닌지) 어떻게 새 메일을 분류할지 학습하는 것.

또 다른 방법은 예측 변수(predictor variable)라 부르는 특성(feature)를 사용하는 것인데. 중고차(연식, 주행거리, 브랜드 등)라든지, 부동산(방 개수, 이웃 등) 등의 거래 가격 같은 타깃 수치를 예측하는 것이다. 이런 작업을 regression(회귀)라고 부른다.

**Unsupervised learning (비지도 학습)** : Label을 정해주기 어려울 때(훈련 데이터에 label이 없다), data를 보고 스스로 학습한다. 특성이 비슷한 데이터를 합쳐서 group으로 분류하는 학습 방법이다. 비지도 학습은 label이 없는 데이터를 사용하며 데이터 안에서 관계를 찾아내는 것을 목적으로 한다. 따라서 사람의 개입이 없어 컴퓨터 스스로 데이터를 훈련하는 것이다. 그래서 비지도라고 한다. 하지만 대부분의 데이터가 label이 없는 형태이기 때문에 앞으로 machine learning이 나아가야 할 방향이라고 한다.

label이 일부만 있는 데이터를 학습하는 것을 Semisupervised learning(준지도 학습)이라 한다.

**Reinforcement learning (강화 학습)** : 앞선 두 가지 학습과는 매우 다른 종류의 학습 알고리즘이다. 앞선 두 가지 학습은 데이터가 주어진 상태로 시작을 하지만 강화 학습은 데이터를 수집하는 과정까지 포함을 한다. 여기서는 학습하는 시스템을 에이전트(agent)라고 부르며 환경(environment)을 관찰해서 행동(action)을 실행하고 그 결과로 보상(reward) 또는 벌점(penalty)를 받는다. 시간이 지나면서 가장 큰 보상을 얻기 위해 정책(policy)라고 부르는 최상의 전략을 스스로 학습 하는 것.
![](https://1.bp.blogspot.com/-TYr5fovwVp4/VvY7iT_JJ5I/AAAAAAAAxQg/xayzv5nND2sCh16MINdYjNJDY8qldZdGA/s400/aaa.png "Reinforcement learning")

위 3가지 학습법 외에도 다양한 학습방법이 있다.

## Release note
2018-05-17: First upload  
2018-05-22: Update

## References
<https://www.digitalocean.com/community/tutorials/an-introduction-to-machine-learning>

<http://solarisailab.com/archives/1785>

Hands-on Machine Learning

