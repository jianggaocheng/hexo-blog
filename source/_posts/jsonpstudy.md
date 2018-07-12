---
title: JSONP的一点个人理解
tags: []
categories: []
date: 2015-02-16 16:14:57
---

JSON很多人都听说过，JSONP可能知道的人就不如JSON那么多了。在这里记录下自己在学习JSONP时候的一点个人理解。

网上经常说JSONP是类似于在页面Document中插入``` <script> ```标签的方式来实现跨域数据访问，可能对于很多只对JSON有了解的人来说理解起来有点困难。百度百科上面对于JSONP有这样一句解释：

<!-- more -->

> “用 JSONP 抓到的资料并不是 JSON，而是任意的JavaScript，用 JavaScript 直译器执行而不是用 JSON 解析器解析。”

对于只了解JSON不了解JSONP的人，看到Response里面的内容，可能会觉得JSONP不过是在普通JSON请求的Response中拼上了”_Callback(“和”);”虽然看起来的确”_Callback({});”这样的Response内容很像JavaScript代码，但是还是很难理解为什说JSONP相当于在页面中插入```<script>```标签。

我们可以看下第一张图红框标记的请求类型是application/x-javascript， 和其他普通的引用JS文件的请求类型是一样的。从请求-响应的角度来说，这样一个JSONP的请求，和通过```<script>```标签引用一个普通的JS文件效果是一样的，只不过JSONP相当于服务器端动态的生成这个JavaScript文件。而且众所周知的是，当JavaScript文件被HTML引入的时候，会立即执行文件里面的代码。

现在应该大家可以理解为什么当图中的JSONP请求返回的时候，会执行事先定义好的_Callback方法了吧。


（完）