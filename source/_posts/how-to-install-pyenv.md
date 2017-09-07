---
title: pyenv教程完整版
date: 2017-05-25
categories: Python
toc: true
---
## 为什么要安装pyenv？

Python最令人头疼的问题之一，就是其版本问题。我们经常会遇到系统需要的运行环境是Python 2.7，但自己又想使用Python 3.x中的某些特性。

这时候需要在系统中安装多个版本的Python。但不同版本的Python会相互影响，例如Shell的Python版本决定运行环境，Python 2和Python 3的pip会冲突等等。因此我们需要一个不会影响系统运行环境，而又可以轻松切换版本的Python管理器。[pyenv](https://github.com/pyenv/pyenv)就是一款比较优秀的Python版本管理器。

## pyenv能做什么？

pyenv能够实现：
+ 可以自由切换全局Python版本
+ 对每个项目提供不同的Python版本支持
+ 重写环境变量中的Python版本
+ 更轻便地创建Python虚拟环境

## 安装与配置pyenv

### 安装pyenv

可以通过**Github**或**Pypi**两种方式安装pyenv。

#### Github方式（推荐）
```shell
$ curl -L https://raw.githubusercontent.com/pyenv/pyenv-installer/master/bin/pyenv-installer | bash
```

更新pyenv：
```shell
pyenv update
```

#### Pypi方式
使用Pypi方式安装时，一定要注意系统Python版本应为**Python 2.x**。
```shell
$ pip install --egg pyenv
```

### 定义环境变量

使用**CentOS**或**Debian**系统时，在命令行输入：
```shell
$ echo 'export PYENV_ROOT="$HOME/.pyenv"' >> ~/.bash_profile
$ echo 'export PATH="$PYENV_ROOT/bin:$PATH"' >> ~/.bash_profile
$ echo 'eval "$(pyenv init -)"' >> ~/.bash_profile
```

使用**Ubuntu**或**Fedora**：将命令行中的`.bash_profile`
改为`~/.bashrc`。
特别地，如果使用**zsh**作为Shell环境：将命令行中的`.bash_profile`改为`~/.zshenv`。

### 重启Shell
重启之后，环境变量的配置才会生效。
```shell
$ exec $SHELL
```

此时pyenv的安装已经完成，在命令行中输入
```shell
$ pyenv version
```
如果打印
```shell
system (set by /$HOME/.pyenv/version)
```
则表示安装成功。安装完pyenv还必须安装**Python依赖包**。

### 安装Python依赖包

pyenv在安装不同版本的Python时需要编译Python，会依赖一些库文件。安装Python前必须安装这些库文件。不同系统安装方法如下：
+ Ubuntu/Debian:
    ```shell
    $ sudo apt-get install -y make build-essential libssl-dev zlib1g-dev libbz2-dev libreadline-dev libsqlite3-dev wget curl llvm libncurses5-dev libncursesw5-dev xz-utils tk-dev
    ```
+ Fedora/CentOS/RHEL:
    ```shell
    $ yum install zlib-devel bzip2 bzip2-devel readline-devel sqlite sqlite-devel openssl-devel
    ```
+ Mac OS X:
    ```
    brew install readline xz
    ```

此时所有安装和配置工作已经完成。安装存在Bug请参考[https://github.com/pyenv/pyenv/wiki/Common-build-problems](https://github.com/pyenv/pyenv/wiki/Common-build-problems)。

## 使用pyenv

以下是pyenv常用的一些命令。
+ 查看当前Python版本：
    ```shell
    $ pyenv version
    ```

+ 查看pyenv中可以使用的Python版本：
    ```shell
    $ pyenv versions
    ```

+ 查看所有可以安装的版本：
    ```shell
    $ pyenv install --list
    ```

+ 安装Python版本：
    ```shell
    $ pyenv install <Python版本>
    ```
    编译Python的时间比较长，请耐心等待。

+ 卸载Python版本：
    ```shell
    $ pyenv uninstall <Python版本>
    ```

+ 切换Shell的Python版本：
    ```shell
    $ pyenv shell <Python版本>
    ```
    切换后，可以通过`which python`命令查看当前Shell的Python环境。

+ 设置局部python版本:
    ```shell
    $ pyenv local <python版本>
    ```

## 卸载pyenv
```
$ rm -fr ~/.pyenv
```
然后从`.bashrc/.zshrc/.bash_profile`中移除下面的环境变量：
```
export PATH="~/.pyenv/bin:$PATH"
eval "$(pyenv init -)"
eval "$(pyenv virtualenv-init -)"
```

**References:**
1. [https://github.com/pyenv/pyenv](https://github.com/pyenv/pyenv).
2. [https://github.com/pyenv/pyenv/wiki/Common-build-problems](https://github.com/pyenv/pyenv/wiki/Common-build-problems).
