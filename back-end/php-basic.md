## 类型
PHP 支持 9 种原始数据类型

四种标量类型
- boolean
- integer
- float
- string

三种复合类型
- array
- object
- callable（可调用）

两种特殊类型
- resource（资源）
- null（无类型）

### callable（可调用）
自 PHP 5.4 起可用 callable 类型指定回调类型 callback。

这种类型通俗来说就是一种函数类型，比如我们创建一个函数，它接受一个参数，这个时候我们可以指定参数的类型。如果参数是一个函数，那这种类型就是 callable 类型。

当然在 PHP 中，我们创建函数的时候，它的参数是不需要给出类型的，但是像 Java 这种强类型语言就不一样了，它的函数（方法）的参数是需要给出类型的。

**call_user_func()**

这个函数第一个参数就是一个回调函数（callable）类型。

**array_map()**

这个函数第一个参数也是一个回调函数（callable）类型。

### resource（资源）
资源 resource 是一种特殊变量，保存了到外部资源的一个引用。

像数据库连接和文件资源符都属于 resource 类型。
- $c = mysql_connect();
- $fp = fopen("foo","w");

`get_resource_type ( resource $handle )`这个函数可以得到 resource 的字符串表示。

### NULL（无类型）
特殊的 NULL 值表示一个变量没有值。NULL 类型只有一个值，就是不区分大小写的常量 NULL。

在下列情况下一个变量被认为是 NULL：
- 被赋值为 NULL。
- 尚未被赋值。
- 被 unset()。

### 类型检测和判断
- gettype()：获取变量类型
- get_resource_type()：返回资源（resource）类型
- is_bool()
- is_int()
- is_float()
- is_string()
- is_array()
- is_object()
- is_callable
- is_resource()
- is_null()
- is_numeric()：检测变量是否为数字或数字字符串
