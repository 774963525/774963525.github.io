# 解决Ubuntu下VSCODE空格距离极小的方案

下载字体文件https://github.com/tonsky/FiraCode#download-v1206–how-to-install–troubleshooting–news–updates
解压压缩文件并打开ttf文件夹，双击安装字体文件，安装完所有的字体文件
打开VSCODE的settings.json文件
注释掉原来的editor.fontFamily配置行，注释是为了后面恢复方便
添加字体文件配置
```
// 以下两行必须
   "editor.fontFamily": "'Fira Code'",
   "editor.fontLigatures": true,
    //下面四行分别设置不同粗细的字体，选择一种
    // "editor.fontWeight": "300",// Light
   // "editor.fontWeight": "400", // Regular
   "editor.fontWeight": "500", // Medium
   // "editor.fontWeight": "600", // Bold
```
保存重启.
转载链接：https://blog.csdn.net/kellncy/article/details/90345506