## 浏览器通讯

### 前后端通信方式

#### 浏览器主动从服务器获取数据

> AJAX 技术

- XMLHttpRequest 对象的工作流程
- 兼容性处理
- 事件的触发条件
- 事件的触发顺序

#### 服务器主动给浏览器发送数据

> Comet 技术

### 同源策略及限制
**同源策略**

同源策略限制从一个源加载的文档或脚本如何与来自另一个源的资源进行交互，这是一个用于隔离潜在恶意文件的关键的安全机制。

**限制**

- Cookie、LocalStorage 以及 IndexDB 无法读取
- DOM 无法获得
- AJAX 无法发送

### 跨域通信
- JSONP
- Hash
- postMessage
- WebSocket
- CORS

## 浏览器渲染机制

### 渲染主流程
Webkit

![Webkit](../images/webkitflow.png)

Gecko

![Gecko](../images/gecko.jpg)

**注意**
- display:none 的节点不会被加入Render Tree，而visibility: hidden 则会，所以，如果某个节点最开始是不显示的，设为display:none 是更优的。

- display:none 会触发 reflow，而 visibility:hidden 只会触发 repaint，因为没有发现位置变化。

- 有些情况下，比如修改了元素的样式，浏览器并不会立刻reflow 或 repaint 一次，而是会把这样的操作积攒一批，然后做一次 reflow，这又叫异步 reflow 或增量异步 reflow。但是在有些情况下，比如resize 窗口，改变了页面默认的字体等。对于这些操作，浏览器会马上进行 reflow。

更多参考：[https://www.cnblogs.com/slly/p/6640761.html](https://www.cnblogs.com/slly/p/6640761.html)

### 重排 Reflow

#### 定义
DOM 结构中的每个元素都有自己的盒子模型，这些都需要浏览器根据各种样式来计算并根据计算结果将元素放到它该出现的位置，这个过程称之为 Reflow。

#### 触发条件
- 增加、删除和修改 DOM 节点时，会导致 Reflow 或 Repaint
- 移动 DOM 位置，或使用动画
- 修改 CSS 样式（如 width、height等）
- Resize 浏览器窗口（移动端没有该问题），或是滚动
- 修改网页默认字体

### 重绘 Repaint

#### 定义
当各种盒子的位置、大小以及其他属性，例如颜色、字体大小等都确定下来后，浏览器会把这些元素按照各自的特性进行绘制，然后呈现页面，这个过程称之为 Repaint。

#### 触发条件
- DOM 改动
- CSS 改动

## JavaScript 运行机制

### 如何理解 JavaScript 的单线程
> 同一时刻，只能做一件事情。

如果深入来说这个问题，我们可以从单线程有什么特点入手，从优点和缺点两方面来说。

当然，但凡说道优缺点都是有一个比较对象的，所以回答这个问题中，我们可以找一个比较对象。既然说道了单线程，那么就找一个多线程的语言 Java（或者 C#、Go等）。

### 什么是任务队列

#### 异步任务
- setTimeout 和 setInterval
- DOM 事件
- AJAX
- ES6 中的 Promise

#### 同步任务
JavaScript 会先执行同步任务，当所有的同步任务执行完后，才会去执行异步任务。

### 什么是事件循环（Event Loop）

浏览器中有一个 Time 模块，专门用来处理 JavaScript 的定时器任务。

当浏览器执行 JavaScript 脚本时，如果遇到定时器的部分，Time 模块会记录这部分，等到定时器设置的时间到了，才会把这部分放到异步队列，然后才会执行。
