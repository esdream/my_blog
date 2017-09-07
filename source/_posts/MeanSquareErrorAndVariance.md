---
title: 详细解释均方差与方差
date: 2017-05-11
categories: Math
toc: true
---
在统计学和机器学习领域中，经常会使用到均方差和方差这两个词。那么它们有什么区别呢？

## 定义

**均方差(Mean Square Error, MSE)**的公式如下：

$$MSD = {\sum_{i=0}^{n}(x_i - {\overline x})^2 \over n}$$

**方差(Variance)**的公式如下：

$$Var = {\sum_{i=0}^{n}(x_i - {\overline x})^2 \over n - 1}$$

## 两者的共同点与区别

事实上，二者都属于方差，也可以说是方差在不同情况下的两种表达方式。均方差(MSE)和均方根差(Root Mean Square Error, RMSE)在**机器学习**领域中更加常见。

唯一的不同点是，当分号下方系数为`n - 1`时，这是一个**无偏估计**的方差。


**References:**
1. [What is the difference between Mean Squared Deviation and Variance?](https://stats.stackexchange.com/questions/239379/what-is-the-difference-between-mean-squared-deviation-and-variance)
