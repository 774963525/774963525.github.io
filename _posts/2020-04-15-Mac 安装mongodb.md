## Mac 安装mongodb

教程:https://www.runoob.com/mongodb/mongodb-osx-install.html

#### 一.安装
安装完成,添加环境变量：
`export PATH=/usr/local/mongodb/bin:$PATH`
也可以
` vi ~/.bash_profile`
将`export PATH=/usr/local/mongodb/bin:$PATH`放在尾部
`source ～/.bash_profile`

#### 二.运行
创建数据库存储路径
`sudo mkdir -p /data/db`
由于升级系统,无法创建,换一个自定义路径
`mongod --dbpath '/usr/local/mongodb/data/db'`

**每次启动都需要**:
		启用服务器
				`sudo mongod`
		启动客户端:进入bin
				`./mongo`
