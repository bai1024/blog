---
title: shell指令的总结
date: 2016-10-22 16:11:57
tags:
---
## 小记
这篇文章主要是为了帮助自己查阅以及巩固之前所学到的知识，所以有什么写的不全面，或者理解不对的地方，希望可以指出~

# SHELL
所有测试基于`bash`。shell里面，每个指令有一个返回值，0表示成功，非0表示不成功。上一个指令的返回值可以通过`$?`去看。

## shell变量

shell变量可以直接使用`name=val`这种形式来赋值（注意中间没有空格，不能有空格），查看变量的时候，在变量名前面加上`$`符。
<!-- more -->
```bash
name=dingdingbai
echo $name
```

## 文件描述符，流与重定向

每一个程序默认打开三个流，标准输入，标准输出，标准错误输出。
shell使用文件描述符来标识一个流。
标准输入： 0
标准输出： 1
标准错误输出： 2
e.g
a>b，文件描述a重新定向到b指向的地方。一般是重定向到文件或者设备，`/dev/null`。
```bash

ls -l > a.txt 2>a.txt

ls -l > a.txt 2>&1

```

 
## 管道
管道操作符`|`，可以将一个指令的标准输出连接到另一个指令的标准输入。
```bash
ls | grep A # 将当前目录下所有含有A的文件名列出来
```


## 别名
别名就是可以给一个指令创建另外一个名字，一般是用来简化指令的，少打几个字符。

```bash
alias cj=ls # 输入cj相当于输入ls
alias # 直接输入alias，可以看到当前shell中所有的别名
```


## shell通配符
`{a..z}`会自动扩展。

`*`号shell会替你自动替换。


## 子shell，环境变量

环境变量就是当前shell中能够被子shell继承的变量，普通变量不能被继承。在子shell里修改变量，是不会影响父shell的。在父shell中存在的变量，会在子shell继承。

使用指令`export name=val`将变量导出为环境变量。

用圆括号括起来的指令会在子shell中执行。`(ls)`

变量赋值可以使用这种语法,`name=$(ls)`


## 一行执行多个指令
第一种，使用分号。

使用`&&`或者`||`号。


## 常用指令

- `cd` (changedirectory)改变当前工作目录，后面一般加上你想要更换到的目录
e.g
```bash
    cd Documents
```

- `pwd` (print working directory)打印当前的工作目录，这个指令会显示当前处于哪个目录当中

- `ls` (list) 展现当前文件夹下面所有的文件

- `touch` 新建一个空的文件，比如touch a.txt，在当前目录下新建一个名叫a.txt的空文件

- `cat` + filename  可以直接查看文件里面的内容

- `rm`(remove) 删除文件或文件夹

- `mkdir` (make directory)创建一个新的文件夹

- `rmdir` （make directory)删除空文件，强制删除非空文件夹要使用`rm -f [direcoty name]`

- `open` 将文件在finder中显示

- `which` 显示指令的绝对路径
```bash
$ which ls
ls: aliased to ls -G
$ which cd
cd: shell built-in command
```

- `echo` 打印字符串到标准输出
e.g
```bash
    echo "hello world"
    hello world
```

- `mv` 移动文件

- `ping`

- `grep` ((global search regular expression(RE) and print out the line)
全面搜索正则表达式并把行打印出来


