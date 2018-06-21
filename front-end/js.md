## 引用类型
> 引用类型的值（对象）是引用类型的一个实例。在 ECMAScript 中，引用类型是一种数据结构，用于将数据和功能组织在一起。它也常被称为类，但是这种称呼并不妥当。

### Object 类型
访问对象属性：
- 点表示法：person.name
- 方括号表示法：person['name']

方括号表示法可以支持变量和特殊字符串，如 person[propertyName] 和 person['first-name']，而点表示法不支持这些情况。

### Array 类型
完整 Array 对象属性和方法：[菜鸟教程](http://www.runoob.com/jsref/jsref-obj-array.html)

#### 易混淆函数
**slice(start, end)**

slice 翻译成中文为切片。函数作用：从某个已有的数组返回选定的元素。

*该方法不会改变原始数组。*

**splice(index, count, item1, item2, ...)**

splice 翻译成中文为拼接。函数作用：向/从数组中添加/删除项目，然后返回被删除的项目。

*该方法会改变原始数组。*

### RegExp 类型

#### RegExp 匹配模式
- g：表示全局模式
- i：表示不区分大小写模式
- m：表示多行模式

#### RegExp 创建方式
- 对象字面量方式

 `var expression = / pattern / flags`

- 构造函数方式

 `var expression = new RegExp('pattern', 'flags')`

#### RegExp 实例属性
- global：是否设置 g 标志
- ignoreCase：是否设置 i 标志
- multiline：是否设置 m 标志
- source：正则表达式的字符串表示
- lastIndex：整数，表示开始搜索下一个匹配项的字符位置，从 0 算起

#### RegExp 实例方法
方法一：**exec()**

返回包含第一个匹配信息的数组，没有匹配项返回 null。

即使设置了 g，每次也只返回一个匹配信息，当再次执行 exec() 时，才返回下一个匹配信息。

`pattern.exec(string)`

方法二：**test()**

模式与参数匹配情况下返回 true，否则返回 false。

`pattern.test(string)`
