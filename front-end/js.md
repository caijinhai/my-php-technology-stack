当我们说起前端 Javascript 的时候，其实是包含三个部分的
- BOM
- DOM
- ECMAScript

其中 BOM 主要指浏览器对象，DOM 指文档对象，而 ECMAScript 才真正是一门图灵完备的语言。

BOM 和 DOM 都是 Javascript 在浏览器中操作文档对象和浏览器对象的接口，在后端 Javascript，如 nodejs 中是只有 ECMAScript 的。

## BOM
- Window 对象
- Navigator 对象
- Screen 对象
- History 对象
- Location 对象
- 存储对象

## DOM
- Document 对象
- 元素对象
- 属性对象
- 事件对象：[点击查看](./js/event.md)

## ECMAScript
在 Javascript 中，关于数据处理主要是依赖 ECMAScript，也只有它能称为是编程语言。

现在浏览器普遍支持 ECMAScript，但是在 nodejs 中 ES6 都到了很大的支持，所以新开发的应用一般采用的是 ES6，其提供的新语法给了很大的便利，值得一提的是 Promise 的出现，给了 Javascript 异步编程提供了很好的方式，解决了回调地狱的风险。

### 引用类型
> 引用类型的值（对象）是引用类型的一个实例。在 ECMAScript 中，引用类型是一种数据结构，用于将数据和功能组织在一起。它也常被称为类，但是这种称呼并不妥当。

#### Object 类型
访问对象属性：
- 点表示法：person.name
- 方括号表示法：person['name']

方括号表示法可以支持变量和特殊字符串，如 person[propertyName] 和 person['first-name']，而点表示法不支持这些情况。

#### Array 类型
[查看更多](./js/array.md)

#### RegExp 类型
[查看更多](./js/regexp.md)

### 函数表达式

#### 闭包
闭包是 js 中的难点，但是其作用很大，需要用心琢磨。

参考资料：
- [web 分享](https://blog.csdn.net/zhoulei1995/article/details/80672960)

#### 块级作用域

### 面向对象
js 是一门面向对象语言，但是和 java 之类的静态语言中的面向对象有所不同，很多人容易在这一块糊涂，当然包括我自己。

**主要需要弄清楚三个问题**
1. 理解对象
2. [创建对象](https://blog.csdn.net/zhoulei1995/article/details/79858505)
3. [实现继承](https://blog.csdn.net/zhoulei1995/article/details/80632822)

## ECMAScript 6
> ECMAScript 6.0（以下简称 ES6）是 JavaScript 语言的下一代标准，已经在 2015 年 6 月正式发布了。它的目标，是使得 JavaScript 语言可以用来编写复杂的大型应用程序，成为企业级开发语言。

- let 和 const 命令
- 变量的解构赋值
- Promise 对象
- Module

参考资料：
- [ECMAScript 6 入门](http://es6.ruanyifeng.com/#README)
