---
title: Dropout与过拟合
date: 2018-03-30 12:51:01
categories: Machine Learning
tags: 
    - 机器学习
    - Dropout
toc: True
---
## Dropout方法简介

Dropout方法是解决神经网络过拟合问题的一个行之有效的方法。其过程如下：
1. 在训练中，**随机删除**网络中隐藏层**一定比例**（例如50%）的units（图b中变为×的units）；
2. 在删除units后的网络中进行训练，并更新units参数；
3. 恢复被删除的units，再重新随机选择相同比例的units，重复第2步。直至训练迭代次数为止。
4. 在预测时，**将删除的units全部恢复**，不再需要Dropout。

![Droput](http://oxcq4sqz2.bkt.clouddn.com/dropout.png)

## 为什么Dropout能起到解决overfitting的作用？

1. 平均以抵消过拟合：每一次迭代由于是随机删除units，相当于k次迭代训练了k个不同的神经网络，完整的Dropout过程相当于对于不同的Neural Network取平均或者投票（类似于集成学习中的Bagging），这样可以有效防止过拟合。
2. 减少神经元之间复杂的共适应关系：由于Dropout导致神经元不一定每次都在dropout网络中出现，能够减少网络对任一feature的依赖，使权值更新不再依赖于某一隐含节点，能够从其他节点中学习到一些共同的模式，增强鲁棒性，达到类似L2正则化的效果。


**References:**
1. [Dropout in (Deep) Machine learning](https://medium.com/@amarbudhiraja/https-medium-com-amarbudhiraja-learning-less-to-learn-better-dropout-in-deep-machine-learning-74334da4bfc5)
2. [深度学习--Dropout](http://phoebepan.cn/2017/09/03/dropout/)
3. [Dropout解决过拟合问题](https://zhuanlan.zhihu.com/p/23178423)