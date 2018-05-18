---
title: Machine Learning[머신러닝] Neural Network
description: Neural Network(인공신경망)에 대한 간략한 정리
categories:
 - Machine Learning
tags: ML
---

# Artificial Neural Network[인공신경망] 줄여서 Neural Network 
인간의 신경세포(뉴런)을 모방하여 수학식으로 만든 것이다. 컴퓨터는 숫자 계산과 같은 부분에서는 분명 사람보다 뛰어나지만, 사람은 당연하게(?) 사진을 보고 사물을 구별한다. 하지만 컴퓨터가 하기는 어렵다. 컴퓨터에겐 사진은 단순하게 0과 1로 이루어진 픽셀 데이터에 지나지 않기 때문.
사실 사람도 자연스럽게 될 뿐 과정은 간단하진 않다. 뇌에는 1천억 개의 뉴런과 100조 개의 연결이 존재한다.
따라서 인간의 뇌를 모방해보자 하는 아이디어가 나오게 되었다.
![](https://postfiles.pstatic.net/MjAxODA1MTZfMTE0/MDAxNTI2NDY4NDk2NjY2.9NzmYQWo_yCzcQJtyjvOoldXhAtI1evNeN8avHm8NYcg.033XwyvV-8MJgZ5S8kbEGCMxc6mZSiZxDhJY5GQQ34cg.PNG.goddam0205/2018-05-16_%281%29.png?type=w773 "Neural Network")
인간의 뇌는 전기 신호를 입력받고 Synapses(시냅스)에 의해 다른 신경세포와 연결(input) 한다. 신경전달물질에 의해 신경 세포가 신호 처리(가중치) 되며 결과는 어느 일정 수준 이상이 되면 출력(output)으로 전환한다.
![](https://postfiles.pstatic.net/MjAxODA1MTZfMiAg/MDAxNTI2NDY4NTUyNjI0.JAcWo6wxaQCGaS79jhLNT9oKeqAIyiyS4x8U4-hTF5kg.gCYDBK_t9G_5Pd8MwzV6P_ln-hb7nxczzxf_w47Z-6cg.PNG.goddam0205/2018-05-16_%282%29.png?type=w773)
입력 신호 (x1,x2,x3 ...)를 가중치 (weight)와 Bias에 의해 계산하며 activation function에 의해 최종 활성화 여부를 결정(output) 한다

보통 neural network는 directed graph이다. 정보의 전달이 한 방향으로만 진행되는 것. Undirected edge 혹은 동일한 directed edge가 양뱡향으로 주어지면 정보의 전달이 반복적(recursive)으로 일어나게 되는데 이런 경우를 RNN (Recurrent Neural Network)라고 한다. 
뇌에서는 각기 다른 뉴런들이 활성화되고, 그 결과를 다음 뉴런에게 전달하고 그 과정을 반복하여 최종 결정을 내리는 뉴런이 activate 되는 방식에 따라서 정보를 처리하게 된다. 
다만 단층 Neural Network로는 XOR 문제가 불가능하다.

![](https://postfiles.pstatic.net/MjAxODA1MTZfMjk4/MDAxNTI2NDY5NjI5OTg2.stp2INMBxZkGLaAkQYkp63UPifhlwuBwJeJHA2yir08g.rZ6bqAiZu-x10eU3OzsiK2EPk6a9_GVUm-YAl-GMPtYg.PNG.goddam0205/2018-05-16.png?type=w773)
(Simple) XOR problem : linearly separable ?
단층 neural network의 선형성 때문에 XOR 문제가 해결이 불가능하다. XOR은 곡속으로만 해결이 가능. 복잡한 문제 해결을 위해 Multilayer(복층) Neural Network가 필요하다.
하지만 엄청난 계산량에 한계를 발견하게 된다. 
> No one on earth had found a viable way to train - Marvin Minsky, 1969

복층 neural network에서는 학습이 불가능한 문제가 발생하게 되는데, (hidden layer를 무슨 수로 학습하는가 ?)
![](https://postfiles.pstatic.net/MjAxODA1MTZfNSAg/MDAxNTI2NDcwMjM0MjYx.U2H-XXdwDZ4yvlDUVhrPwlMhqDgIEQ1HxyyMEbyRUqog.QQudEG8VeRNboFbFVxzWSe1d16UMtQLZutcgNbtdLK0g.PNG.goddam0205/main-qimg-7532a36a1e14a3f7a135a5f7301a5752.png?type=w773)
문제가 복잡해줄수록 여러 층으로 뉴런을 구성해야 한다. 다만 이렇게 하면 엄청난 양의 연산을 해야 하는데, 그 당시 컴퓨터로는 절대 불가능했다.

다만 엄청난 계산량은 시대가 흐르면서 컴퓨터가 발전하다 보니 덜 신경 써도 되게 되었다. 
>알파고는 13개의 층으로 수백 ~ 수천만의 연결 고리를 가지고 있다고 한다. 

그리고 재 조명 받은 것이 Deep Learning 혹은 Deep Neural Network이다. 개념 자체는 수십 년도 전에 있었지만... 그리고 정보의 진행이 앞으로만 일어나는 네트워크를 'feed-forward network'라고 하는데, 그 가운데 위의 이미지처럼 hidden layer가 하나보다 많으면 'deep'하다고 한다. 요즘은 layer를 대부분 하나보다는 많이 쌓기 때문에 요즘 나오는 neural network 연구들은 다 deep learning이라고 생각해도 된다. 
