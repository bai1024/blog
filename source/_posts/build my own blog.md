---
title: How to build your bolg On GitHub Pages
---


### 创建git仓库
在自己的GitHub上创建以“username.github.io”格式为名字的仓库
e.g.
![](http://ww1.sinaimg.cn/large/9bd18299gw1f73u79mz76j205u016744.jpg)



### 安装hexo
在本地建立一个以“Blog”为名字的文件夹（可以自行决定文件夹名字啦～）,这里用于存放建立blog的原始文件

``` bash
$ git init
```
<!-- more -->

进入刚刚建立的文件夹中安装hexo

``` bash
$ npm install -g hexo
```

安装完以后开始初始化

``` bash
$ npm install hexo
```
Hexo随后会自动在目标文件夹建立网站所需要的所有文件。


### 改变bolg的样式
可以到hexo官网寻找喜欢的主题，根据作者的提示安装

https://hexo.io/themes/

这里直接贴上网址，方便大家寻找，大家也可以去GitHub上查找主题，有很多好看的主题，安装也非常简单

下载以及安装完以后我们需要更改模板内容，将它变为展示自己的博客

在Blog文件夹的_config.yml文件里面修改相应的内容，比如：
![](http://ww2.sinaimg.cn/large/9bd18299gw1f73vm7blhgj207f04bmxd.jpg)

与此同时，我们也要修改themes文件夹里面的_config.yml文件，修改里面的内容，比如：
![](http://ww3.sinaimg.cn/large/9bd18299gw1f73vpx1hqjj20aj05sdge.jpg)


### 写博文
Blog文件夹中可以看到一个souce文件夹，点开里面有一个子文件夹_posts，里面就装着我们每次写的博文
![](http://ww2.sinaimg.cn/large/9bd18299gw1f73vya1y5tj206907daaa.jpg)

新建文章的话只要输入`hexo new "postName"`指令就可以啦


### 本地查看网页样式
如何能在本地查看自己的博客呢，我们可以运用$ hexo sever 指令，查看我们的网页效果
![](http://ww2.sinaimg.cn/large/9bd18299gw1f7bxjj14vtj20ev04tt9n.jpg)
按"Ctrl + c"结束进程

### 将本地文件部署到GitHub
博客完成后我们需要将它部署到GitHub，这样才能和大家分享自己的网页，第一步输入以下指令：

```bash
  type: git
  repository: //输入"username.github.io"仓库的shh
  branch: master
```

第二步，安装deployer插件

```bash
$ npm install hexo-deployer-git --save
```

第三步，部署到GitHub

```bash
$ hexo g
$ hexo d
```
以后每一次在本地的更新只需要输入上面的两个指令就可以啦

### 查看自己的博客
在我们完成以上所有步骤后，只需要输入在浏览器中输入`{usename}.github.io`
这样大家就可以访问你的博客啦～