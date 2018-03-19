---
title: 使用Anaconda实现Python环境配置与管理
date: 2018-03-19 20:20:34
categories: Python
tags: 
- Python
- environment
- 环境配置
- Anaconda
toc: true
---

## 前言

**[Anaconda](https://anaconda.org/)** 提供了Python环境配置与管理的终极解决方案，使用Anaconda能够方便地对Python packages安装、管理、导入等。

## 使用方法

### 列出环境

在终端中输入以下命令。
```shell
conda env list
```
列表中当前所在环境旁边有一个星号。默认的环境名为root。

### 创建环境

在终端中输入
```shell
conda create -n env_name package_names
```

其中package_names可以省略，如果省略则会配置为当前默认的Python版本。
在创建环境时，可以指定要安装在环境中的Python版本。例如这里创建环境名为py3，并安装最新版本的Python 3.6。
```shell
conda create -n py3 python=3.6
```

需要安装Python 2时同理。

### 激活环境

在Windows上：
```shell
activate env_name
```

在Linux/OSX上：
```shell
source activate env_name
```

### 退出环境

在Windows上：
```shell
deactivate
```

在Linux/OSX上：
```shell
source deactivate
```

### 共享环境

#### 环境导出

在终端中输入：
```shell
conda env export > environment.yml
```
将环境导出为`environment.yml`文件。

对于不使用conda的用户，使用以下命令将环境导出：
```shell
pip free > environment.txt
```

#### 环境导入

##### conda用户

在终端输入：
```shell
conda env update -f=/path/to/envirionment.yml
```
则可以让环境直接导入至conda中。

##### 非conda用户使用pip导入环境

在终端输入：
```shell
pip install -r /path/requirements.txt
```

### 删除环境

```shell
conda env remove -n env_name
```