## DOM 事件级别
- DOM 0 ：onclick = function() {}
- DOM 2 : addEventListener('click',function(){},false)
- DOM 3 : addEventListener('click',function(){},false) 增加了一些事件

## DOM 事件模型
- 冒泡
- 捕获

## DOM 事件流
捕获阶段 -> 目标阶段 -> 冒泡阶段

## DOM 事件捕获的具体流程
window -> document -> html -> body -> ... -> target element

## Event 对象的常见应用
- event.preventDefault()
- event.stopPropagation()
- event.stopImmediatePropagation()
- event.currentTarget()
- event.target()

## 自定义事件
var event = new Event('custome');
event.addEventListener('custome', function(){});
event.dispatchEvent(event);

CustomEvent()
