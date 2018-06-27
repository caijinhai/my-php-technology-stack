## RegExp 匹配模式
- g：表示全局模式
- i：表示不区分大小写模式
- m：表示多行模式

## RegExp 创建方式
- 对象字面量方式

 `var expression = / pattern / flags`

- 构造函数方式

 `var expression = new RegExp('pattern', 'flags')`

## RegExp 实例属性
- global：是否设置 g 标志
- ignoreCase：是否设置 i 标志
- multiline：是否设置 m 标志
- source：正则表达式的字符串表示
- lastIndex：整数，表示开始搜索下一个匹配项的字符位置，从 0 算起

## RegExp 实例方法
方法一：**exec()**

返回包含第一个匹配信息的数组，没有匹配项返回 null。

即使设置了 g，每次也只返回一个匹配信息，当再次执行 exec() 时，才返回下一个匹配信息。

`pattern.exec(string)`

方法二：**test()**

模式与参数匹配情况下返回 true，否则返回 false。

`pattern.test(string)`
