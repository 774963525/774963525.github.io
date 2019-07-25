# JavaScript 教程 01)

JavaScript 能够改变 HTML 内容
JavaScript 能够改变 HTML 属性
JavaScript 能够改变 HTML 样式 (CSS)
JavaScript 能够隐藏 HTML 元素
JavaScript 能够显示 HTML 元素
```
<!DOCTYPE html>
<html>
<body>

<h2>JavaScript 能做什么</h2>

<p id="demo">JavaScript 能够改变 HTML 内容。<br>
JavaScript 能够改变 HTML 属性<br>
JavaScript 能够改变 HTML 样式 (CSS)<br>
JavaScript 能够隐藏 HTML 元素<br>
JavaScript 能够显示 HTML 元素<br>
</p>

<button type="button" onclick='document.getElementById("demo").innerHTML = "Hello JavaScript!"'>点击我！</button>
//更改属性
document.getElementById("demo").style.fontSize = "25px";
//隐藏html元素
document.getElementById("demo").style.display="none";
//显示html元素
document.getElementById("demo").style.display="block";

</body>
</html>

```
## js使用 



### <script> 标签

***

#### 内部脚本
JavaScript 函数可以被放置于 HTML 页面的 <head>和<body> 部分。

```
<!DOCTYPE html>
<html>
<body> 

<h1>A Web Page</h1>
<p id="demo">一个段落</p>
<button type="button" onclick="myFunction()">试一试</button>

<script>
function myFunction() {
   document.getElementById("demo").innerHTML = "段落被更改。";
}
</script>

</body>
</html>
```
**提示:**
把脚本置于 <body> 元素的底部，可改善显示速度，因为脚本编译会拖慢显示。

#### 外部脚本 

脚本可放置与外部文件中：

外部文件：myScript.js
```
function myFunction() {
   document.getElementById("demo").innerHTML = "段落被更改。";
}
```
外部脚本很实用，如果相同的脚本被用于许多不同的网页。

JavaScript 文件的文件扩展名是 .js。

如需使用外部脚本，请在 <script> 标签的 src (source) 属性中设置脚本的名称：

实例
`<script src="myScript.js"></script>`

您可以在 <head> 或 <body> 中放置外部脚本引用。

该脚本的表现与它被置于 <script> 标签中是一样的。

**注释：** 外部脚本不能包含 <script> 标签。



### JavaScript 显示方案

***



JavaScript 能够以不同方式“显示”数据：

使用 window.alert() 写入警告框
使用 document.write() 写入 HTML 输出
使用 innerHTML 写入 HTML 元素
使用 console.log() 写入浏览器控制台

出于测试目的，使用 document.write() 比较方便：

**提示：****document.write()** 方法仅用于测试。

**注意：**在 HTML 文档完全加载后使用 **document.write()** 将*删除所有已有的 HTML* ：



### JavaScript 关键词
***

JavaScript 语句常常通过某个关键词来标识需要执行的 JavaScript 动作。

下面的表格列出了一部分将在教程中学到的关键词：

| 关键词        | 描述                                              |
| :------------ | :------------------------------------------------ |
| break         | 终止 switch 或循环。                              |
| continue      | 跳出循环并在顶端开始。                            |
| debugger      | 停止执行 JavaScript，并调用调试函数（如果可用）。 |
| do ... while  | 执行语句块，并在条件为真时重复代码块。            |
| for           | 标记需被执行的语句块，只要条件为真。              |
| function      | 声明函数。                                        |
| if ... else   | 标记需被执行的语句块，根据某个条件。              |
| return        | 退出函数。                                        |
| switch        | 标记需被执行的语句块，根据不同的情况。            |
| try ... catch | 对语句块实现错误处理。                            |
| var           | 声明变量。                                        |

**注释：**JavaScript 关键词指的是保留的单词。保留词无法用作变量名。



# JavaScript 语法

**JavaScript 语法是一套规则，它定义了 JavaScript 的语言结构。**

```
var x, y;	// 如何声明变量
x = 7; y = 8;	// 如何赋值
z = x + y;	// 如何计算值
```

### JavaScript 值
JavaScript 语句定义两种类型的值：混合值和变量值。

混合值被称为字面量（literal）。变量值被称为变量。

#### JavaScript 字面量
书写混合值最重要的规则是：

写数值有无小数点均可：
```
15.90
10011
```
字符串是文本，由双引号或单引号包围：
```
"Bill Gates"

'Bill Gates' 
```

#### JavaScript 变量
在编程语言中，变量用于存储数据值。

JavaScript 使用 var 关键词来声明变量。

= 号用于为变量赋值。

在本例中，x 被定义为变量。然后，x 被赋的值是 7：
```
var x;

x = 7;
```
JavaScript 运算符
JavaScript 使用算数运算符（+ - * /）来计算值：
`
(7 + 8) * 10
`

# JavaScript 运算符
```
<h1>+= 运算符</h1>

<p id="demo"></p>

<script>
var x = 7;
x += 8;
document.getElementById("demo").innerHTML = x;
</script>
```
## JavaScript 比较运算符JavaScript 比较运算符

| 运算符 | 描述           |
| :----- | :------------- |
| ==     | 等于           |
| ===    | 等值等型       |
| !=     | 不相等         |
| !==    | 不等值或不等型 |
| >      | 大于           |
| <      | 小于           |
| >=     | 大于或等于     |
| <=     | 小于或等于     |
| ?      | 三元运算符     |

## JavaScript 逻辑运算符

| 运算符 | 描述   |
| :----- | :----- |
| &&     | 逻辑与 |
| \|\|   | 逻辑或 |
| !      | 逻辑非 |

## JavaScript 类型运算符JavaScript 类型运算符

| 运算符     | 描述                                  |
| :--------- | :------------------------------------ |
| typeof     | 返回变量的类型。                      |
| instanceof | 返回 true，如果对象是对象类型的实例。 |

JavaScript 位运算符
位运算符处理 32 位数。

该运算中的任何数值运算数都会被转换为 32 位的数。结果会被转换回 JavaScript 数。

| 运算符 | 描述         | 例子    | 等同于       | 结果 | 十进制 |
| :----- | :----------- | :------ | :----------- | :--- | :----- |
| &      | 与           | 5 & 1   | 0101 & 0001  | 0001 | 1      |
| \|     | 或           | 5 \| 1  | 0101 \| 0001 | 0101 | 5      |
| ~      | 非           | ~ 5     | ~0101        | 1010 | 10     |
| ^      | 异或         | 5 ^ 1   | 0101 ^ 0001  | 0100 | 4      |
| <<     | 零填充左位移 | 5 << 1  | 0101 << 1    | 1010 | 10     |
| >>     | 有符号右位移 | 5 >> 1  | 0101 >> 1    | 0010 | 2      |
| >>>    | 零填充右位移 | 5 >>> 1 | 0101 >>> 1   | 0010 |        |

因此，在 JavaScript 中，~ 5 不会返回 10，而是返回 -6。

~00000000000000000000000000000101 将返回 11111111111111111111111111111010。

# JavaScript 数据类型

## 字符串值，数值，布尔值，数组，对象。

## JavaScript 拥有动态类型
JavaScript 拥有动态类型。这意味着相同变量可用作不同类型：

实例
```
var x;               // 现在 x 是 undefined
var x = 7;           // 现在 x 是数值
var x = "Bill";      // 现在 x 是字符串值
```
## JavaScript 数组

JavaScript 数组用方括号书写。

数组的项目由逗号分隔。

下面的代码声明（创建）了名为 cars 的数组，包含三个项目（汽车品牌）：

### 实例

```
var cars = ["Porsche", "Volvo", "BMW"];
```

数组索引基于零，这意味着第一个项目是 [0]，第二个项目是 [1]，以此类推。

您将在本教程中学到更多有关数组的知识。

## JavaScript 对象

JavaScript 对象用花括号来书写。

对象属性是 *name*:*value* 对，由逗号分隔。

### 实例

```
var person = {firstName:"Bill", lastName:"Gates", age:62, eyeColor:"blue"};
```

上例中的对象（person）有四个属性：firstName、lastName、age 以及 eyeColor。

您将在本教程中学到更多有关对象的知识。

## typeof 运算符

您可使用 JavaScript 的 typeof 来确定 JavaScript 变量的类型：

typeof 运算符返回变量或表达式的类型：

### 实例

```
typeof ""                  // 返回 "string"
typeof "Bill"              // 返回 "string"
typeof "Bill Gates"          // 返回 "string"
```

### 实例

```
typeof 0                   // 返回 "number"
typeof 314                 // 返回 "number"
typeof 3.14                // 返回 "number"
typeof (7)                 // 返回 "number"
typeof (7 + 8)             // 返回 "number"
```

typeof 运算符对数组返回 "object"，因为在 JavaScript 中数组属于对象。

## Undefined

在 JavaScript 中，没有值的变量，其值是 undefined。typeof 也返回 undefined。

### 实例

```
var person;                  // 值是 undefined，类型是 undefined
```

任何变量均可通过设置值为 undefined 进行清空。其类型也将是 undefined。

### 实例

```
person = undefined;          // 值是 undefined，类型是 undefined
```

## 空值

空值与 undefined 不是一回事。

空的字符串变量既有值也有类型。

### 实例

```
var car = "";                // 值是 ""，类型是 "string"
```

## Null

在 JavaScript 中，null 是 "nothing"。它被看做不存在的事物。

不幸的是，在 JavaScript 中，null 的数据类型是对象。

您可以把 null 在 JavaScript 中是对象理解为一个 bug。它本应是 null。

您可以通过设置值为 null 清空对象：

### 实例

```
var person = null;           // 值是 null，但是类型仍然是对象
```



您也可以通过设置值为 undefined 清空对象：

### 实例

```
var person = undefined;     // 值是 undefined，类型是 undefined
```



## Undefined 与 Null 的区别

Undefined 与 null 的值相等，但类型不相等：

```
typeof undefined              // undefined
typeof null                   // object
null === undefined            // false
null == undefined             // true
```

## 原始数据

原始数据值是一种没有额外属性和方法的单一简单数据值。

typeof 运算符可返回以下原始类型之一：

- string
- number
- boolean
- undefined

### 实例

```
typeof "Bill"              // 返回 "string"
typeof 3.14                // 返回 "number"
typeof true                // 返回 "boolean"
typeof false               // 返回 "boolean"
typeof x                   // 返回 "undefined" (假如 x 没有值)
```

## 复杂数据

typeof 运算符可返回以下两种类型之一：

- function
- object

typeof 运算符把对象、数组或 null 返回 object。

typeof 运算符不会把函数返回 object。

### 实例

```
typeof {name:'Bill', age:62} // 返回 "object"
typeof [1,2,3,4]             // 返回 "object" (并非 "array"，参见下面的注释)
typeof null                  // 返回 "object"
typeof function myFunc(){}   // 返回 "function"
```



typeof 运算符把数组返回为 "object"，因为在 JavaScript 中数组即对象。