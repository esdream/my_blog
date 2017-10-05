# Ryan FU Blog

这是Ryan FU的博客，使用Hexo搭建，主题为yilia。当前版本`为v1.1.1`。

## 创建前配置

**创建my_blog之前，请确认当前环境下已成功配置`npm`, `node.js`和`git`。**

## 拷贝Repository

```shell
# 递归拷贝，将主模块和themes中的子模块(submodule)一并拷贝
$ git clone https://github.com/esdream/my_blog.git --recursive  
```
拷贝完成后，将`config_in_themes`目录下对应主题的`_config.yml`拷贝到`themes`中的主题目录中覆盖源文件。

## 安装hexo

```shell
$ npm install hexo-cli -g
```

## 安装依赖包
进入`./my_blog`目录，执行
```shell
$ npm install
```

## 使用hexo生成静态文件，测试和部署
```shell
# 生成静态文件
hexo g

# 在本地创建服务
hexo s

# 部署
hexo d
```
