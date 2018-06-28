## CSS

### 布局
- 浮动（float）
- 绝对定位（position:absolute）
- 弹性盒子布局（display:flex）
- 表格布局（display:table）
- 网格布局（display:grid）
- 相对定位与负边距

### 盒模型
> 所有 HTML 元素可以看作盒子，在 CSS 中，"box model"这一术语是用来设计和布局时使用。CSS 盒模型本质上是一个盒子，封装周围的 HTML 元素，它包括：边距，边框和实际内容。盒模型允许我们在其它元素和周围元素边框之间的空间放置元素。

![Alt text](../images/box-model.gif)

**主要构成**
- Margin(外边距): 清除边框外的区域，外边距是透明的
- Border(边框): 围绕在内边距和内容外的边框
- Padding(内边距): 清除内容周围的区域，内边距是透明的。
- Content(内容): 盒子的内容，显示文本和图像。

#### 标准模型
> 最终元素的总宽度计算公式是这样的：

总元素的宽度 = 宽度 + 左填充 + 右填充 + 左边框 + 右边框 + 左边距 + 右边距

> 元素的总高度最终计算公式是这样的：

总元素的高度 = 高度 + 顶部填充 + 底部填充 + 上边框 + 下边框 + 上边距 + 下边距

#### IE 模型
> 根据 W3C 的规范，元素内容占据的空间是由 width 属性设置的，而内容周围的 padding 和 border 值是另外计算的。不幸的是，IE 5.X 和 6 在怪异模式中使用自己的非标准模型。这些浏览器的 width 属性不是内容的宽度，而是内容、内边距和边框的宽度的总和（不包过外边距）。

#### 设置两种模型
标准
```css
box-sizing: content-box;
```
IE
```css
box-sizing: border-box;
```

#### 设置和获取盒模型对应的宽和高
- `dom.style.width/height(只能获取内联样式)`
- `dom.offsetWidth/offsetHeight`

## CSS3

### 弹性盒子模型
> Flex 布局极大简化了开发人员的开发工作，以前需要使用复杂组合实现的效果，现在使用 Flex 布局可以轻松实现。虽然由于兼容性问题（主要对 IE 8 的兼容）导致其在许多 PC 端的项目中不被考虑，但是在移动端，它热的发紫。同时，如果没有其它特殊的需求，请在移动端优先使用 Flex 布局。

参考资料：
- [语法篇](http://www.ruanyifeng.com/blog/2015/07/flex-grammar.html)
- [实战篇](http://www.ruanyifeng.com/blog/2015/07/flex-examples.html)

### 2D 转换
> CSS3 转换可以可以对元素进行移动、缩放、转动、拉长或拉伸。

- translate() 方法

  根据左(X轴)和顶部(Y轴)位置给定的参数，从当前元素位置移动。

- rotate() 方法

  在一个给定度数顺时针旋转的元素。负值是允许的，这样是元素逆时针旋转。

- scale() 方法

  该元素增加或减少的大小，取决于宽度（X轴）和高度（Y轴）的参数。

- skew() 方法

  包含两个参数值，分别表示X轴和Y轴倾斜的角度，如果第二个参数为空，则默认为0，参数为负表示向相反方向倾斜。

- matrix() 方法

  2D 所有变换方法的合并，有六个参数，包含旋转，缩放，移动（平移）和倾斜功能。

> 所有这些方法都需要在 transform 属性上使用。

**实例：**某个宽度已知，高度未知的盒子垂直居中

```css
position: relative;
top: 50%;
left: 50%;
width: 300px;
margin-left: -150px;
transform: translateY(-50%);
border: 1px solid #0f0;
```

### 过渡
> 不管是 2D 转换也好，还是 3D 转换也好，它们都是静态的，要想实现炫酷的动效那边必须用到 transition（过度）。

CSS3 过渡是元素从一种样式逐渐改变为另一种的效果：
- 指定要添加效果的 CSS 属性
- 指定效果的持续时间

```
语法：
transition: property duration timing-function delay;

实例：
transition: width 2s, height 2s, transform 2s;
```

### 动画
> 尽管过度能够帮助我们实现简单动画，但是对于复杂的动画来说，过度就难于应付了。这个时候我们可以使用 CSS3 的动画，来帮助我们实现复杂多变的动画效果。

动画是使元素从一种样式逐渐变化为另一种样式的效果：
1. 创建动画
2. 执行动画

```
语法：
@keyframes animationname {keyframes-selector {css-styles;}}

实例：
@keyframes mymove
{
  from  {top: 0px;}
  to    {top: 200px;}
}

@keyframes myfirst
{
	0%   {background: red;}
	25%  {background: yellow;}
	50%  {background: blue;}
	100% {background: green;}
}
```

```
语法：
animation: name duration timing-function delay iteration-count direction fill-mode play-state;

实例：
animation: mymove 5s infinite;
```
