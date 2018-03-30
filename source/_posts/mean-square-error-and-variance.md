---
title: 详细解释均方差与方差
date: 2017-05-11
categories: Math
toc: true
---

**本文于2018年3月30日更新，从自由度上解释了MSE中N与N-1的区别。**

在统计学和机器学习领域中，经常会使用到均方差和方差这两个词。那么它们有什么区别呢？

## 定义

**均方差(Mean Square Error, MSE)**的公式如下：

$$MSE = {\sum_{i=0}^{n}(x_i - {\overline x})^2 \over n}$$

**方差(Variance)**的公式如下：

$$Var = {\sum_{i=0}^{n}(x_i - {\overline x})^2 \over n - 1}$$

## 两者的共同点与区别

事实上，二者都属于方差，也可以说是方差在不同情况下的两种表达方式。实际上二者并无区别。真正需要注意的是二者除以的样本数n与n-1。

在统计学中，存在 **“自由度”** 这一概念。自由度是指当以样本的统计量来估计总体的参数时，样本中独立或能自由变化的数据个数，称为该统计量的自由度。一般来说，自由度等于独立变量减掉其衍生量数；举例来说，对于n个随机且相互独立的样本，某一样本的样本值与其他样本的样本值没有任何关系，也就是说n个样本都会对均值$\overline x$产生影响，因此样本均值的自由度是**n**。

而在方差Var中，需要使用样本减平均值(一个由样本决定的衍伸量)。而在**均值$\overline x$固定**的情况下，n个随机样本中能够独立变化的样本值为n-1个，剩下的一个样本必然受其他n-1样本影响。因此对n个随机样本而言，其方差Var自由度为**n-1**。

在机器学习中，很多研究者不care自由度这一概念，因此MSE计算常用n。但从严格的统计学定义出发，应该使用n-1。

**References:**
1. [What is the difference between Mean Squared Deviation and Variance?](https://stats.stackexchange.com/questions/239379/what-is-the-difference-between-mean-squared-deviation-and-variance)
2. [自由度(统计学)](https://zh.wikipedia.org/wiki/%E8%87%AA%E7%94%B1%E5%BA%A6_(%E7%BB%9F%E8%AE%A1%E5%AD%A6))