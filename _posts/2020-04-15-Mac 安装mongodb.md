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
由于升级系统,无法创建

解决方法:

- 重启mac
- 按住`command+r`进入恢复模式
- 点击用户登录
- 在顶部导航栏选择`Utilities->Terminal.app`
- 输入`csrutil disable`关闭SIP
- 点击左上角苹果的logo重启
- 重启完成后在Terminal中输入`sudo mount -uw /`重新挂载根目录
- 在根目录正常创建文件夹
- 将其他目录的文件夹软连接到根目录文件夹`ln -s /Users/xxxx/test /test/`
- 设置777或者其他读写权限
- 重启并按`command+r`进入恢复模式
- 在恢复模式的Terminal输入`csrutil enable`重新开启SIP
- 重启

或者换一个自定义路径
`mongod --dbpath '/usr/local/mongodb/data/db'`,但是每次启动mongod(服务器)都需要指定这个路径 太麻烦

**启动**:
		启用服务器
				`sudo mongod`
		启动客户端:未配路径的话进入bin
				`./mongo`