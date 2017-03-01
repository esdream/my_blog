## 创建my_blog

**创建my_blog之前，请确认当前环境下已成功配置`npm`, `node.js`和`git`。**

### 拷贝Repository

*`material`主题仓库由于未知原因`clone`速度极慢，可先`clone`主模块，再下载`material`主题zip压缩包，解压至`./themes`目录中，并将解压后主题目录名改成`material`。*
```shell
# 递归拷贝，将主模块和themes中的子模块(submodule)一并拷贝
$ git clone https://github.com/esdream/my_blog.git --recursive  
```

### 安装hexo
```shell
$ npm install hexo-cli -g
```

### 安装依赖包
进入`./my_blog`目录，执行
```shell
$ npm install
```

### 使用hexo生成静态文件，测试和部署
```shell
# 生成静态文件
hexo g

# 在本地创建服务
hexo s

# 部署
hexo d
```
