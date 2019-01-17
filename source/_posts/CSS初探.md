---
title: CSS初探
date: 2019-01-17 15:29:07
tags: 'CSS'
---

CSS一直是工作中很头疼的东西，简直是噩梦。曾经也啃过《CSS权威指南》之类的书。看完之后貌似记得一些东西，不过还是啥都不会做，觉得无从下手。现在才醒悟这可能是个纯实践的学科。慢慢做出来点儿东西可能就会了。那就下面介绍一些常见的技巧吧。

## 左右布局
左右布局的制作方法非常简单，分为两步。
1. 让需要进行左右布局的所有元素浮动（使用`float:left`或者`float:right`）。
2. 在它们的父元素上使用class="clearfix"。

clearfix的写法如下。
``` css
.clearfix::after{
    content:'';
    display:block;
    clear:both;
}
```
1. 排布在左侧的内容使用`float:left`，排布在右侧的内容使用`float:right`。就可以实现一个左右布局了。
<!-- more -->
## 左中右布局
左中右布局的实现方式在于使用绝对定位，实现方法如下
1. 在表示左右的内容上分别使用`position: absolute`，并固定它们的宽度。
2. 在它们的父元素上使用`postion: relative`。使得子元素绝对定位的标准为父元素而不是浏览器。
3. 使用`top: xxx;` `left: xxx`调整左右内容的位置。
4. 中间的内容使用margin根据浏览器自动调整。

## 水平居中
这里介绍使用inline-block + text-align的实现方式。
1. 对子框设置`display:inline-block`，使其变为内联元素。
2. 对父框设置`text-align:center`。实现子框的水平居中。

## 垂直居中
将父框转化为一个表格单元格显示可以使得表格单元格内容垂直居中，代码如下
``` css
.parent {
	display:table-cell;
	vertical-align: middle;
}
```
## 其他小技巧
1. 调试CSS的时候只需要给它一个`border: 1px solid red`就可以清清楚楚显示它的边框。
2. div的高度是由它内部文档流元素的高度和决定的。内联元素从左向右流，块元素从上向下流。
3. span内的汉字换行的时候是会分离的，而英文不会，想让英文分离的话需要使用`word-break:break-all`;
4. line-height有多高，一个span就会有多高。
5. span和span在html换行写的话中间是会有一个空格的。
6. 在开发者工具中，Styles展示所有的样式，而Computed显示计算之后的属性。


