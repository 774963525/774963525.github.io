# Ubuntu安装配置MongoDB

## 一.下载安装

#### 1.更新列表

`sudo apt update`

#### 2.安装MongoDb

`sudo apt install -y mongodb`
×加-y是为了在后面安装过程中跳过要输入一次Y的步骤。

该命令安装了几个包含最新稳定版本的MongoDB的软件包，以及MongoDB服务器的有用管理工具。 数据库服务器在安装后自动启动。

## 二.检查是否成功

首先检查服务的状态：
`sudo systemctl status mongodb`
如果输出下面类似的内容，说明安装成功了
```
 mongodb.service - An object/document-oriented database
   Loaded: loaded (/lib/systemd/system/mongodb.service; enabled; vendor preset: enabled)
   Active: active (running) since Sat 2018-11-03 14:21:52 CST; 2min 38s ago
     Docs: man:mongod(1)
 Main PID: 20731 (mongod)
    Tasks: 23 (limit: 4915)
   CGroup: /system.slice/mongodb.service
           └─20731 /usr/bin/mongod --unixSocketPrefix=/run/mongodb --config /etc/mongodb.conf
```
可以通过实际连接到数据库服务器并执行诊断命令来进一步验证：
`mongo --eval 'db.runCommand({ connectionStatus: 1 })'`
这将输出当前的数据库版本，服务器地址和端口以及状态命令的输出：
```
MongoDB shell version v3.6.3
connecting to: mongodb://127.0.0.1:27017
MongoDB server version: 3.6.3
{
    "authInfo" : {
        "authenticatedUsers" : [ ],
        "authenticatedUserRoles" : [ ]
    },
    "ok" : 1
}

```
响应中的ok字段的值为1表示服务器工作正常。

## 三.管理 添加path
默认情况下，MongoDB被配置为自动启动服务器。 如果希望禁用自动启动：
`sudo systemctl disable mongodb`
启动:
`sudo systemctl enable mongodb`
服务状态验证:
`sudo systemctl status mongodb`
停止服务器:
`sudo systemctl stop mongodb`
启动服务器
`sudo systemctl start mongodb`
重启服务器:
`sudo systemctl restart mongodb`

## 四.配置密码

mongodb默认不使用密码即可登录,导致很没有安全性,为它添加密码吧.
#### 添加管理员:
因配置了path所以可以直接使用`mongo`进入库
`use admin`进入admin数据库

创建用户:
```
db.createUser({
	user: 'admin',
	pwd:'123456',
	roles:[
		{role:'userAdminAnyDatabase', db:'admin'}
	]
});
```
创建拥有所有权限的root账户
```
db.createUser({
	user:'root',
	pwd:'123456',
	roles: [
		{role:'root', db:'admin'}
	]
})
```

修改ＭongoDB的配置文件,(因为我们是用命令行安装的,所以配置文件默认放在etc目录中)将/etc/mongod.conf文件中的auth=true前面的注释去掉，然后用

`sudo service mongod restart`重启MongDB.

此时再输入`mongo` 可以进入库,但是不能使用命令了.
默认情况下会进入test数据库,我们需要先进入admin
`use admin;`
输入账户密码:
```
>db.auth('admin','123456');
1
```
当返回'1'则输入正确;
此时,我们可以使用命令,但依然不能操作数据库.故需要添加普通管理员.
**进入对应数据库,添加普通管理员**
```
db.createUser({
	user:'mydbUser',
	pwd:'123456',
	roles: [
		{role:'readWrite', db:'mydb'},
		{role:'dbAdmin', db:'mydb'}
	]
})
```
`role:'readWrite', db:'mydb'`表示该用户在当前表下可读可写,去其他表依然不管用.

如此MongoDB配置安装完毕.





转载:https://www.cnblogs.com/darklights/p/9900794.html


转载:https://blog.csdn.net/monkey_four/article/details/38059729



