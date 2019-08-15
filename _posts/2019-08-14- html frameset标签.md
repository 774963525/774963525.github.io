# html frameset标签

<frameset> 标签定义一个框架集。

<frameset> 元素被用来组织一个或者多个 <frame> 元素。每个 <frame> 有各自独立的文档。
注意:<frameset>不能和<body>共存
下例:
		rows分上下两部分 上部分读取top.html
        下部分读取bottom.html
        左右切 cols
```
<frameset rows = "50%,50%">
            <frame src = "./top.html">
            <frame src = "./bottom.html"> 
</frameset>
```
