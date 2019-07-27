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

# JavaScript 函数

**JavaScript 函数是被设计为执行特定任务的代码块。**

**JavaScript 函数会在某代码调用它时被执行。**

```
<h2>JavaScript 函数</h2>

<p>本例调用函数把华氏度转换为摄氏度：</p>

<p id="demo"></p>

<script>
function toCelsius(f) {
    return (5/9) * (f-32);
}
document.getElementById("demo").innerHTML = toCelsius(86);
</script>

```

## () 运算符调用函数

使用上面的例子，toCelsius 引用的是函数对象，而 toCelsius() 引用的是函数结果。

```
不使用（）返回结果
function toCelsius(f) { return (5/9) * (f-32); }
```

## 局部变量

在 JavaScript 函数中声明的变量，会成为函数的*局部变量*。

局部变量只能在函数内访问。

由于局部变量只能被其函数识别，因此可以在不同函数中使用相同名称的变量。

局部变量在函数开始时创建，在函数完成时被删除。



# 十四.JavaScript 对象

## 对象概述

js中可以申明对象，我们生活中的一切都是对象，比如人对象，他有性别，年龄，id的键，以及对应的值。我们可以用如下代码进行声明：

`
var person = {sex:"男"，age:14,id:"001"};
`
其中键 sex，age...被称为属性。“男”……等被称为属性值。
可以使用`person.sex`来访问人的属性。

## 对象方法

对象的属性值可以是方法，和普通的属性值无多大区别。

```
var person = {
  firstName: "Bill",
  lastName : "Gates",
  id       : 678,
  fullName : function() {
    return this.firstName + " " + this.lastName;
  }
};
```

## this 关键词

在函数定义中，this 引用该函数的“拥有者”。

在上面的例子中，this 指的是“拥有” fullName 函数的 *person 对象*。

换言之，this.firstName 的意思是 *this 对象*的 firstName 属性。

# 十五.JavaScript 事件

## HTML 事件

HTML 事件可以是浏览器或用户做的某些事情。

下面是 HTML 事件的一些例子：

- HTML 网页完成加载
- HTML 输入字段被修改
- HTML 按钮被点击

通常，当事件发生时，用户会希望做某件事。

JavaScript 允许您在事件被侦测到时执行代码。

*通过 JavaScript 代码*，HTML 允许您向 HTML 元素添加事件处理程序。

在下面的例子中，onclick 属性（以及代码）被添加到 <button> 元素：

### 实例

```
<button onclick='document.getElementById("demo").innerHTML=Date()'>现在的时间是？</button>
```

## 常见的 HTML 事件

下面是一些常见的 HTML 事件：

| 事件        | 描述                         |
| :---------- | :--------------------------- |
| onchange    | HTML 元素已被改变            |
| onclick     | 用户点击了 HTML 元素         |
| onmouseover | 用户把鼠标移动到 HTML 元素上 |
| onmouseout  | 用户把鼠标移开 HTML 元素     |
| onkeydown   | 用户按下键盘按键             |
| onload      | 浏览器已经完成页面加载       |



# 十六.JavaScript 字符串

**JavaScript 字符串用于存储和操作文本。**

申明字符串需要使用双引号或者单引号，同一字符串符号一经使用不得再用,如：

~~"我说:"你好" "~~
应用:
"我说:'你好'"或者'我说:"你好"'或者使用转义符号.

反斜杠转义字符把特殊字符转换为字符串字符：

| 代码 | 结果 | 描述   |
| :--- | :--- | :----- |
| \'   | '    | 单引号 |
| \"   | "    | 双引号 |
| \\   | \    | 反斜杠 |

其他六个 JavaScript 中有效的转义序列：

| 代码 | 结果       |
| :--- | :--------- |
| \b   | 退格键     |
| \f   | 换页       |
| \n   | 新行       |
| \r   | 回车       |
| \t   | 水平制表符 |
| \v   | 垂直制表符 |

## 字符串长度

内建属性 length 可返回字符串的*长度*：

### 实例

```
var txt = "ABCDEFGHIJKLMNOPQRSTUVWXYZ";
var sln = txt.length;
```

## 字符串可以是对象

但不建议把字符串创建为对象,因为会拖慢执行速度,造成错误等.

当使用 == 相等运算符时，相等字符串是相等的：

### 实例

```
var x = "Bill";             
var y = new String("Bill");
```

当使用 === 运算符时，相等字符串是不相等的，因为 === 运算符需要类型和值同时相等。

### 实例

```
var x = "Bill";             
var y = new String("Bill");

// (x === y) 为 false，因为 x 和 y 的类型不同（字符串与对象）
```

甚至更糟。对象无法比较：

### 实例

```
var x = new String("Bill");             
var y = new String("Bill");

// (x == y) 为 false，因为 x 和 y 是不同的对象
```

# 十七.JavaScript 字符串方法

## 查找字符串中的字符串

indexOf() 方法返回字符串中指定文本*首次*出现的索引（位置）：

### 实例

```
var str = "The full name of China is the People's Republic of China.";
var pos = str.indexOf("China");
```

avaScript 从零计算位置。

0 是字符串中的第一个位置，1 是第二个，2 是第三个 ...

lastIndexOf() 方法返回指定文本在字符串中*最后*一次出现的索引：

### 实例

```
var str = "The full name of China is the People's Republic of China.";
var pos = str.lastIndexOf("China");
```

未找到文本,indexOf()和lastIndexOf()均返回-1.



两种方法都接受作为检索起始位置的第二个参数。

### 实例

```
var str = "The full name of China is the People's Republic of China.";
var pos = str.indexOf("China", 18);
```

## 检索字符串中的字符串

search() 方法搜索特定值的字符串，并返回匹配的位置：

### 实例

```
var str = "The full name of China is the People's Republic of China.";
var pos = str.search("locate");
```

两种方法，indexOf() 与 search()，返回的值是*相等的*。

但这两种方法是不同的。区别在于：

- search() 方法无法设置第二个开始位置参数。
- indexOf() 方法无法设置更强大的搜索值（正则表达式）。

## 提取部分字符串

有三种提取部分字符串的方法：

- slice(*start*, *end*)
- substring(*start*, *end*)
- substr(*start*, *length*)

`slice(start,end)`,`subString(start,end)`前后的参数都可以为负,`substr(start,length)`后面的参数不能为负,因为是长度.

## 替换字符串内容

replace() 方法用另一个值替换在字符串中指定的值：

### 实例

```
str = "Please visit Microsoft!";
var n = str.replace("Microsoft", "W3School");
```

replace() 方法不会改变调用它的字符串。它返回的是新字符串。

默认地，replace() *只替换首个匹配*：

### 实例

```
str = "Please visit Microsoft and Microsoft!";
var n = str.replace("Microsoft", "W3School");
```

默认地，replace() 对大小写敏感。因此不对匹配 MICROSOFT：

### 实例

```
str = "Please visit Microsoft!";
var n = str.replace("MICROSOFT", "W3School");
```

如需执行大小写不敏感的替换，请使用正则表达式 /i（大小写不敏感）：

### 实例

```
str = "Please visit Microsoft!";
var n = str.replace(/MICROSOFT/i, "W3School");
```

请注意正则表达式不带引号。

如需替换所有匹配，请使用正则表达式的 g 标志（用于全局搜索）：

### 实例

```
str = "Please visit Microsoft and Microsoft!";
var n = str.replace(/Microsoft/g, "W3School");
```

## 转换为大写和小写

通过 toUpperCase() 把字符串转换为大写：

通过 toLowerCase() 把字符串转换为小写：

## concat() 方法

concat() 连接两个或多个字符串：

### 实例

```
var text1 = "Hello";
var text2 = "World";
text3 = text1.concat(" ",text2);
```

## String.trim()

trim() 方法删除字符串两端的空白符：

### 实例

```
var str = "       Hello World!        ";
alert(str.trim());
```

## 提取字符串字符

这是两个提取字符串字符的*安全*方法：

- charAt(*position*)
- charCodeAt(*position*)

## charAt() 方法

charAt() 方法返回字符串中指定下标（位置）的字符串：

### 实例

```
var str = "HELLO WORLD";
str.charAt(0);            // 返回 H
```

## charCodeAt() 方法

charCodeAt() 方法返回字符串中指定索引的字符 unicode 编码：

### 实例

```
var str = "HELLO WORLD";

str.charCodeAt(0);         // 返回 72
```

## 属性访问（Property Access）

ECMAScript 5 (2009) 允许对字符串的属性访问 [ ]：

### 实例

```
var str = "HELLO WORLD";
str[0];                   // 返回 H
```

使用属性访问有点不太靠谱：

- 不适用 Internet Explorer 7 或更早的版本

- 它让字符串看起来像是数组（其实并不是）

- 如果找不到字符，[ ] 返回 undefined，而 charAt() 返回空字符串。

- 它是只读的。str[0] = "A" 不会产生错误（但也不会工作！）

  

  ## 把字符串转换为数组

  可以通过 split() 将字符串转换为数组：

  ### 实例

  ```
  var txt = "a,b,c,d,e";   // 字符串
  txt.split(",");          // 用逗号分隔
  txt.split(" ");          // 用空格分隔
  txt.split("|");          // 用竖线分隔
  ```
    ```
function myFunction() {
  var str = "a,b,c,d,e,f";
  var arr = str.split(",");
  document.getElementById("demo").innerHTML = arr[5];
  }
    ```

 # 十八.JavaScript 数字

**JavaScript 只有一种数值类型。**

**书写数值时带不带小数点均可。**

## NaN - 非数值

NaN 属于 JavaScript 保留词，指示某个数不是合法数。

尝试用一个非数字字符串进行除法会得到 NaN（Not a Number）：

### 实例

```
var x = 100 / "Apple";  // x 将是 NaN（Not a Number）
```

不过，假如字符串包含数值，则结果将是数：

### 实例

```
var x = 100 / "10";     // x 将是 10
```

**除了"+"其他符号系统都会检测引号内是否是数值**

可使用全局 JavaScript 函数 isNaN() 来确定某个值是否是数：返回true/false.

## Infinity

Infinity （或 -Infinity）是 JavaScript 在计算数时超出最大可能数范围时返回的值。

### 实例

```
var myNumber = 2;

while (myNumber != Infinity) {          // 执行直到 Infinity
    myNumber = myNumber * myNumber;
}
```

除以 0（零）也会生成 Infinity：

## 十六进制

JavaScript 会把前缀为 0x 的数值常量解释为十六进制。

所以不要使用03,04这样的数字.

# 十九.JavaScript 数值方法

**Number 方法帮助您处理数值。**

## toString() 方法

toString() 以字符串返回数值。

所有数字方法可用于任意类型的数字（字面量、变量或表达式）：

### 实例

```
var x = 123;
x.toString();            // 从变量 x 返回 123
(123).toString();        // 从文本 123 返回 123
(100 + 23).toString();   // 从表达式 100 + 23 返回 123
```

## toFixed() 方法

toFixed() 返回字符串值，它包含了指定位数小数的数字：

### 实例

```
var x = 9.656;
x.toFixed(0);           // 返回 10
x.toFixed(2);           // 返回 9.66
x.toFixed(4);           // 返回 9.6560
x.toFixed(6);           // 返回 9.656000
```

## toPrecision() 方法

toPrecision() 返回字符串值，它包含了指定长度的数字：

### 实例

```
var x = 9.656;
x.toPrecision();        // 返回 9.656
x.toPrecision(2);       // 返回 9.7
x.toPrecision(4);       // 返回 9.656
x.toPrecision(6);       // 返回 9.65600
```

## valueOf() 方法

valueOf() 以数值返回数值：

### 实例

```
var x = 123;
x.valueOf();            // 从变量 x 返回 123
(123).valueOf();        // 从文本 123 返回 123
(100 + 23).valueOf();   // 从表达式 100 + 23 返回 123
```

## 把变量转换为数值

这三种 JavaScript 方法可用于将变量转换为数字：

- Number() 方法
- parseInt() 方法
- parseFloat() 方法

这些方法并非*数字*方法，而是*全局* JavaScript 方法。

## 全局方法

JavaScript 全局方法可用于所有 JavaScript 数据类型。

这些是在处理数字时最相关的方法：

| 方法         | 描述                         |
| :----------- | :--------------------------- |
| Number()     | 返回数字，由其参数转换而来。 |
| parseFloat() | 解析其参数并返回浮点数。     |
| parseInt()   | 解析其参数并返回整数。       |

## Number() 方法

Number() 可用于把 JavaScript 变量转换为数值：

### 实例

```
x = true;
Number(x);        // 返回 1
x = false;     
Number(x);        // 返回 0
x = new Date();
Number(x);        // 返回 1404568027739
x = "10"
Number(x);        // 返回 10
x = "10 20"
Number(x);        // 返回 NaN
```

## 用于日期的 Number() 方法

Number() 还可以把日期转换为数字：

### 实例

```
Number(new Date("2019-04-15"));    // 返回 1506729600000
```

上面的 Number() 方法返回 1970 年 1 月 1 日至今的毫秒数。

## parseInt() 方法

parseInt() 解析一段字符串并返回数值。允许空格。只返回首个数字：

### 实例

```
parseInt("10");         // 返回 10
parseInt("10.33");      // 返回 10
parseInt("10 20 30");   // 返回 10
parseInt("10 years");   // 返回 10
parseInt("years 10");   // 返回 NaN
```

如果无法转换为数值，则返回 NaN (Not a Number)。

## parseFloat() 方法

parseFloat() 解析一段字符串并返回数值。允许空格。只返回首个数字：

### 实例

```
parseFloat("10");        // 返回 10
parseFloat("10.33");     // 返回 10.33
parseFloat("10 20 30");  // 返回 10
parseFloat("10 years");  // 返回 10
parseFloat("years 10");  // 返回 NaN
```

如果无法转换为数值，则返回 NaN (Not a Number)。

## 数值属性

| 属性              | 描述                             |
| :---------------- | :------------------------------- |
| MAX_VALUE         | 返回 JavaScript 中可能的最大数。 |
| MIN_VALUE         | 返回 JavaScript 中可能的最小数。 |
| NEGATIVE_INFINITY | 表示负的无穷大（溢出返回）。     |
| NaN               | 表示非数字值（"Not-a-Number"）。 |
| POSITIVE_INFINITY | 表示无穷大（溢出返回）。         |

# 二十.JavaScript 数组

**JavaScript 数组用于在单一变量中存储多个值。**

**声明语法:**

`var person = ["张三","李思","枉二","麻子"];`

可以使用

`var person =new Array ("张三","李思","枉二","麻子");`

效果完全相同,但是麻烦 没必要.

**通过数字下标索引从0开始访问并改变:**

`person[0]="独秀";`

## 数组是对象

数组是一种特殊类型的对象。在 JavaScript 中对数组使用 typeof 运算符会返回 "object"。

## 数组属性和方法

JavaScript 数组的真实力量隐藏在数组的属性和方法中：

### 实例

```
var x = cars.length;   // length 属性返回元素的数量
var y = cars.sort();   // sort() 方法对数组进行排序
```

## 如何识别数组

常见的问题是：我如何知晓某个变量是否是数组？

问题在于 JavaScript 运算符 typeof 返回 "object"：

### 解决方案 3(最易)：

假如对象由给定的构造器创建，则 *instanceof* 运算符返回 true：

```
var fruits = ["Banana", "Orange", "Apple", "Mango"];
 
fruits instanceof Array     // 返回 true
```

# 二十一.JavaScript 数组方法

## 把数组转换为字符串

JavaScript 方法 toString() 把数组转换为数组值（逗号分隔）的字符串。

### 实例

```
var fruits = ["Banana", "Orange", "Apple", "Mango"];
document.getElementById("demo").innerHTML = fruits.toString(); 
```

结果

```
Banana,Orange,Apple,Mango
```

join() 方法也可将所有数组元素结合为一个字符串。

它的行为类似 toString()，但是您还可以规定分隔符：

### 实例

```
var fruits = ["Banana", "Orange","Apple", "Mango"];
document.getElementById("demo").innerHTML = fruits.join(" * "); 
```

结果

```
Banana * Orange * Apple * Mango
```

## Popping 和 Pushing

在处理数组时，删除元素和添加新元素是很简单的。

Popping 和 Pushing 指的是：

从数组*弹出*项目，或向数组*推入*项目。

pop()方法删除数组中最后一个元素;

### 实例

```
var fruits = ["Banana", "Orange", "Apple", "Mango"];
fruits.pop();              // 从 fruits 删除最后一个元素（"Mango"）
```

pop()方法返回被弹出的值

## Pushing

push("xxx") 方法（在数组结尾处）向数组添加一个新的元素：

### 实例

```
var fruits = ["Banana", "Orange", "Apple", "Mango"];
fruits.push("Kiwi");       //  向 fruits 添加一个新元素
```

push() 方法返回新数组的长度：

### 实例

```
var fruits = ["Banana", "Orange", "Apple", "Mango"];
var x =  fruits.push("Kiwi");   //  x 的值是 5
```

## 位移元素

位移与弹出等同，但处理首个元素而不是最后一个。

shift() 方法会删除首个数组元素，并把所有其他元素“位移”到更低的索引。

使用 `数组名.shift();` 删除数组第一个元素.

输出 `数组名.shift();` 值为被删除的元素值.

`unshift() 方法`（在开头）向数组添加新元素，原有元素以此向后位移.

输出unshift() 方法 值为添加后的数组长度.

## 删除元素

使用delete 数组名[下标数字]来删除数组里的元素

**delete方法删除元素后会留下空洞,需要使用pop()灬shift补足**.

## 拼接数组

splice() 方法可用于向数组添加新项：

### 实例

```
var fruits = ["Banana", "Orange", "Apple", "Mango"];
fruits.splice(2, 0, "Lemon", "Kiwi");
```

第一个参数（2）定义了应添加新元素的位置（拼接）。

第二个参数（0）定义应删除多少元素。

其余参数（“Lemon”，“Kiwi”）定义要添加的新元素。

splice() 方法返回一个包含已删除项的数组：

### 实例

```
var fruits = ["Banana", "Orange", "Apple", "Mango"];
fruits.splice(2, 2, "Lemon", "Kiwi");
```

## 使用 splice() 来删除元素比delete()方便

通过聪明的参数设定，您能够使用 splice() 在数组中不留“空洞”的情况下移除元素：

### 实例

```
var fruits = ["Banana", "Orange", "Apple", "Mango"];
fruits.splice(0, 1);        // 删除 fruits 中的第一个元素
```

## 合并（连接）数组

concat() 方法通过合并（连接）现有数组来创建一个新数组：

### 实例（合并两个数组）

```
var myGirls = ["Cecilie", "Lone"];
var myBoys = ["Emil", "Tobias", "Linus"];
var myChildren = myGirls.concat(myBoys);   // 连接 myGirls 和 myBoys
```

concat() 方法不会更改现有数组。它总是返回一个新数组。

concat() 方法可以使用任意数量的数组参数：

## 裁剪数组

slice() 方法用数组的某个片段切出新数组。

slice() 可接受两个参数，比如 (1, 3)。

该方法会从开始参数选取元素，直到结束参数（不包括）为止。



# 二十二.JavaScript 数组排序

**sort() 方法是最强大的数组方法之一。**

## 数组排序

sort() 方法以字母顺序对数组进行排序：

### 实例

```
var fruits = ["Banana", "Orange", "Apple", "Mango"];
fruits.sort();            // 对 fruits 中的元素进行排序
```

## 反转数组

reverse() 方法反转数组中的元素。



http://www.w3school.com.cn/js/js_array_sort.asp笔记有空补

