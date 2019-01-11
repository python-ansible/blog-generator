---
title: HTML初探
date: 2019-01-10 16:55:28
tags: 'html'
---

这里记录一下初次学习HTML的一些知识和体验,总的来讲感觉HTML并不是太容易，虽然css是玄学，js是大山。但HTML也不是个省油的小妖精。
<!-- more -->
## HTML版本
常见的HTML版本有:
- HTML4.01
- XHTML
- HTML5

现在开发一般用的HTML5,当然外包的老项目可能会用HTML4.01,但HTML5是向前兼容的,所以不用担心太多。另外一个原因可能是HTML的文档类型定义可能是最方便好记录的一种了`<!DOCTYPE html>`就可以了。感兴趣可以自行看看HTML4.01的文档类型定义,反正我是不会去背的。

还有一点很有趣的东西,以前我一直认为H5就是HTML5,现在才知道它俩根本不是一个东西，H5是指能够在微信上运行的网页，用什么技术做都可以。想想以前。。。。应该没有吹破牛皮吧。

当然学习html还是要经常靠自己吸收一些知识的，毕竟自驱学习能力还是很重要的。自学html的方法就是要多google一下规范文档(搜html spec),和MDN啦。

## 常用HTML标签
- `<kbd></kbd>`代表键盘的按键
- `<div>`与`<span>`标签无实际意义,且无默认样式的,它们经常配一个class来代表它们的意义,而其他的标签都有默认样式。
- `<svg>`代表不规则图形,它是xml格式的
- html标签是没有块元素和内联元素之分的，它完全靠css控制
- `<img>`标签一般都要写alt防止下载失败用户不知道这是代表什么的图片
- `<nav>`代表导航条
- `<hr>`代表水平分割线
- `<main>`代表主要内容
- `<footer>`代表页脚
- `<dl>`代表描述列表，它包裹的`<dt>`代表要描述的单词,`<dd>`代表它的定义。
- `<table>`代表表格，在`<table>`中,`<col>`代表表格中的列,`<colgroup>`代表表格列组(听说这个好多人都不知道?)。
- `<meta>`代表元数据，暂时只见过用它来设置字符集。
- `<strong>`代表意义上很重要的内容。
- `<em>`代表语气上很重要的内容。
- `<div contentediable="true">Hello</div>`是个能够编辑内容的div。
- `<canvas>`用来画图。
- `<input type="range">`是一个滑动条。
- `<meter>`用来度量指定范围内的数据。
- `<aside>`定义和文章不相关的内容。
- `<section>`代表章节。
- 在需要打出`&`这个符号的时候需要用`&amp`作为转义

## `<iframe>`和`<a>`
`<iframe>`标签用于在一个页面中嵌入另一个页面。
它的形式时常是这样`<iframe name="xxx" src="xxx">`。

`<a>`标签表示一个超链接。它的表现形式经常是这样`<a href="xxx" target="yyy">`
其中target属性有四种取值
1. _self 代表在自身所在窗口打开。
2. _blank 代表在新开的窗口打开.
3. _parent 代表在父元素中打开。
4. _top 代表在顶层窗口打开。
`<a href="xxx" download>`这样的写法用于下载文件，若在http响应中Content-Type为 application/octet-stream则代表以流的形式下载文件，这时不需要download，但如果是text/html就需要加download了。

href中写的路径有以下几点需要注意。
- 加上http: https: （//代表使用当前协议）,也可以使用相对路径的形式。
- 若写成href="?name='xxx'"的形式则可以在请求中把name作为查询条件。只有锚点是不发起请求的。
- 也可以使用伪协议`<a href="javascript:;">`可以执行js代码。前面这种写法使得a不跳转到别处，也不页内跳转。
- `<a href="">`用来刷新当前页面
- `<a href="#">`使得页面锚点变成#

## `<form>`
`<form>`和`<a>`都用来发起请求,`<a>`只能用来发起get请求，而`<form>`可以发起get请求和post请求
他的一般形式是这样的
`<form action="index2.html" method="post">`
&nbsp;&nbsp;&nbsp;&nbsp;`<input type="submit" value="提交">`
`</form>`

- form发起的请求在不借助js的情况下必须有一个`<input type="submit">`作为提交标签，且发起的POST请求的Content-Type为application/x-www-form-urlencoded，它会把中文变成UTF-8(file协议是不支持POST的)
- form的method属性可以使get或者post，默认get，get会把参数放在查询参数中，而post会把参数放在第四部分的FormData中，在post的情况下也可以在action中写入"?name='xxx'"的形式把参数放在查询参数中

## `<input>`

### `<input type="button">`和`<button>`的区别
1. button不写type自动升级为提交按钮，而写了type="button"则不会有提交的功能。
2. `<input type="button">`不能提交，但type="submit"则可以提交
### `<input type="checkbox">`
`<input type="checkbox" id="xx"><label for="xx">YYY</label>`这样写就可以在点击label的时候也勾选checkbox了。
也可以写成`<label><input type="checkbox">YYY</label>`
### `<input type="radio">`
在同一时间只能选择一个radio需要把他们的name属性设置成一样的

## `<textarea>`
这个标签经常会用css来限制它的宽高，因为它是可以拖拽的。

## `<select>`
这个标签有这样三个属性
- multiple支持多选
- disabled禁止勾选
- selected代表默认勾选

## `<table>`
table中有四部分`<thead>`,`<tbody>`,`<tfoot>`,`<colgroup>`它们的顺序是没有关系的，浏览器会自动纠正。另外一个需要注意的点事<td>中一般都是数据，而<th>是表头。

## 几个重要的概念
- CSS的优先级是比标签属性高德
- CSS用横向/纵向布局的方式（不过貌似grid布局已经出来了。。。。）
- Dribble.com是设计师们的交友平台，平时可以在上面做css联系
- 在HTML中,通常在一个空元素上使用一个闭标签是无效的。例如`<input type="text"></input>`
- CSS里，可替换元素的展现不是由CSS来控制的。这些元素是一类 外观渲染独立于CSS的 外部对象。 典型的可替换元素有`<img>`,`<object>`,`<video>`和表单元素，如`<textarea>`,`<input>`。
