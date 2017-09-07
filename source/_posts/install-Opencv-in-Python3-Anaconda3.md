---
title: 在Anaconda3 / Python3环境下安装Opencv
date: 2017-09-07 10:53:36
categories: Python
tags: Python3, OpenCV2, Anaconda3
toc: True
---
## 问题起源

最近在做一个深度学习项目，期间需要进行人脸检测，想使用`OpenCV2`库。可曾想这个大坑货的官方版本只支持Python 2.x版本。而我的整个程序由于是在Anaconda3编写的，使用了大量Python3的语法与特性。而Google上大部分解决方法要么是要下载`.whl`文件，要么是需要下载源码重新编译，不符合我们优雅地解决问题的初衷。经过一番折腾，终于被我找到了最优雅的解决方式。

## 安装环境

+ 操作系统: Windows 10 amd64
+ Python环境: Anaconda3 / Python3

## 解决过程

首先说一下解决的过程，以后碰到类似的找不到合适安装包的问题可以参照解决，没耐心的可以直接跳到下一节 **安装方法** 。

我首先搜索了Anoconda的安装包库。
```shell
$ conda search cv
```

返回结果
```shell
cvxcanon                     0.0.23.3                 py27_0  defaults
                             0.0.23.3                 py34_0  defaults
                             0.0.23.3                 py35_0  defaults
                             0.0.23.3                 py27_0  https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/free
                             0.0.23.3                 py34_0  https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/free
                             0.0.23.3                 py35_0  https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/free
cvxopt                       1.1.9                    py35_0  defaults
                             1.1.9                    py35_0  https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/free
r-cvtools                    0.3.2                  r3.3.1_0  defaults
                             0.3.2                  r3.3.2_0  defaults
                             0.3.2                  r3.4.1_0  defaults
r-mgcv                       1.8_12                 r3.2.4_0  defaults
                             1.8_12                 r3.3.0_0  defaults
                             1.8_12                 r3.3.1_0  defaults
                             1.8_16                 r3.3.2_0  defaults
                             1.8_17                 r3.4.1_0  defaults
vcversioner                  2.16.0.0                 py27_0  defaults
                             2.16.0.0                 py34_0  defaults
                             2.16.0.0                 py35_0  defaults
                             2.16.0.0                 py36_0  defaults
                             2.16.0.0                 py27_0  https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/free
                             2.16.0.0                 py34_0  https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/free
                             2.16.0.0                 py35_0  https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/free
                             2.16.0.0                 py36_0  https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/free
```
最左边一列是名字中包含`cv`的包，如果没有类似于`opencv`的包说明Anaconda中没有合适的库。

接下来搜索一下Python pip的安装包库。
```shell
$ pip search cv
```

找到返回结果中`opencv`相关的包。
```shell
simple-opencv-ocr (0.0)                   - A simple OCR with OpenCV
opcvm-sdk-python (1.1.7)                  - OPCVM360 RESTFul API Wrapper
opencv-utils (0.0.2)                      - OpenCV Utilities
opencv-python (3.3.0.10)                  - Wrapper package for OpenCV python
                                            bindings.
  INSTALLED: 3.3.0.10 (latest)
opencv_cffi (0.2.2)                       - A random subset of OpenCV's'
                                            functionality, wrapped via CFFI
opencv_engine (1.0.1)                     - OpenCV imaging engine for thumbor.
opencv_helpers (1.1)                      - Helper functions for opencv
opencvutils (0.9.2)                       - Simple OpenCV 3.x image processing
                                            functions
OpenRCV (0.0.1-alpha)                     - open-source software for tallying
                                            ranked-choice voting elections
openslides-topicvoting (1.1.0)            - OpenSlides Topic Voting Plugin
```

左边一列是包名，右边一列是包的说明。
我们发现好像有几个可能与`OpenCV`有关。可以一个一个尝试。我这里觉得`opencv-python`相关的可能性最大（程序员的直觉），就直接安装了。

## 安装方法

猴子都会的安装方法。
```shell
$ pip install opencv-python
```

## 检验安装

安装完成后，运行
```shell
$ python
>>> import cv2
>>> cv2.__version__
```
如果没有出现异常，说明安装成功。

最后，感谢将openCV官方包封装成Python3支持的包并推送至pip的人。节约他人的时间，也是一种伟大。
