---
layout: post
title:  "seajs学习之路 - AMD与CMD"
description: "学习seajs，了解前端js模块化编程，CommonJS、AMD与CMD的比较"
keywords: "seajs, CMD, AMD, CommonJS, nodejs"
date:   2015-02-01 00:06:10
categories: seajs
---

第一次听说seajs，已经是两年前的事了，但一直没有机会让我意识到模块化对于前端开发的好处，所以也没有深入去了解使用seajs或者requirejs这类的模块加载器进行模块化编程。

随着公司项目越来越大，前端近无规范的协作，不管是代码维护还是新功能模块的添加，都越显困难与无力。所以，我铁定了心来研究seajs与requirejs这类的模块加载器的实现原理以及模块化编程。这不管对于公司项目的发展与维护，还是提升自身的能力，都有很大的好处。所以，别再想了，干吧！

###1. 关于CommonJS

CommonJS是服务器端模块化的规范，我们耳熟的Node.js就是基于CommonJS Modules/1.0。

根据CommonJS规范，一个单独的文件就是一个模块。每一个模块都是一个单独的作用域，在改模块内定义的变量无法被其他模块所读取，除非定义为global对象的属性。

{% highlight javascript %}
:::under nodejs
//main.js
global.name = 'Frend';
{% endhighlight %}

以上定义的name变量可以被所有的模块所读取，但是并不推荐这种方式。输出模块的变量，最好的方式是使用exports(module.exports)对象。关于`exports与module.exports的区别`推荐看[一位全栈码农对exports与module.exports的分析](http://zihua.li/2012/03/use-module-exports-or-exports-in-node/)。

{% highlight javascript %}
:::under nodejs
//module_a.js

exports.name = 'Frend';

exports.say = function() {
	console.log(name);
}
{% endhighlight %}

使用require方法，加载module_a.js

{% highlight javascript %}
:::under nodejs
//main.js

var module_a = require('./module_a.js');

module_a.say(); //Frend
{% endhighlight %}








