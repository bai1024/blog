---
title: 如何用flexbox制作一个会动的调色盘
date: 2016-09-10 22:20:13
tags:
---


### 介绍
本次的主题就是用实例介绍flexbox的使用——用flex做一个手风琴样式的调色板。这次使用的是在[codepen](https://codepen.io)发现的好的作品，觉得很适合用来讲解flex的使用，而且这个效果也很实用。

### 构建框架
第一步，构建html框架，其中最重要的是要有一个父元素，这样就有了一个“Flex容器”，在它之中所有的子元素自动就成了容器的成员。在本例中我们将容器设置成这样
```html
<div class="color-list">
</div>
```
构建好容器后，接下来就是编写子元素。
<!-- more -->

```html
  <section class="color" style="background: hsl(4,99%,66%);">
    <h2 class="name">Persimmon</h2>
    <ul class="details">
      <li>hsl(4,99%,66%)</li>
      <li>#FE5E52</li>
      <li>178 C</li>
      <li>485 U</li>
      <li>Primary</li>
    </ul>
  </section>
```
以这种形式，复制粘贴就行啦。内容相应的更改。


### 设置CSS样式
首先要定义父元素`.color－list`的display属性。
```css
.color-list {
    display: flex;
}
```
这个时候初步的框架也就可以看出来了。可以根 据需要自定义高度。  
![](http://ww3.sinaimg.cn/large/9bd18299gw1f7qzlwdsl8j20ku01vq2s.jpg)

第二步，设置`.color`的display属性。在上文中我们说到使用flex技术需要有一个容器包裹，相对于`.color`来说，`.color-list`是他的父元素，对于`.color`里面的元素来说它也是父元素，想要对`.color`里面的元素进行操作，就需要将`.color`的display属性设置成flex.  
一般情况下，在flex容器内，默认横轴为`main axis`，所以我们会看到下图的效果。
![example](http://ww2.sinaimg.cn/large/9bd18299gw1f7qzdccjmdj20b606odfv.jpg)这与我们想要达成的垂直效果不一样，这与此时只需要方向更改就可以了，如下图。
```css
.color-list {
  display: flex;
  flex-direction: column;
}
```
![](http://ww2.sinaimg.cn/large/9bd18299gw1f7r0vldwewj20ak061aa3.jpg)修改后的样式。

第三步，下图是这个项目想要达到的动态效果，即当鼠标移到某个色卡上的时候，该色卡会变宽并且显示信息。这个动态效果用flex就可以做出来～
![](http://ww1.sinaimg.cn/large/9bd18299gw1f7r1lb3szag20dc02ldou.gif)
那么怎么在flex中如何给元素加宽呢，这里可以使用`flex-basis`属性。
>flex-basis属性定义了在分配多余空间之前，项目占据的主轴空间（main size）。浏览器根据这个属性，计算主轴是否有多余空间。它的默认值为auto，即项目的本来大小.

```css
 .color:hover{ 
  flex-basis: 20em;
}
```
写到这里已经可以看到动态效果了，但是感觉过渡生硬不流畅，因此相应的增加过度效果就更好了。本文主要讲flex的用法，所在在这里其他的就不多做解释了。

本篇主要是帮助加深巩固flex技术的使用，因此涉及的不是太全面。推荐阮一峰的教程，忘记了，或者不懂的时候可以参考一下。
[Flex布局教程：语法篇](http://www.ruanyifeng.com/blog/2015/07/flex-grammar.html)
[Flex布局教程：实例篇](http://www.ruanyifeng.com/blog/2015/07/flex-examples.html)
