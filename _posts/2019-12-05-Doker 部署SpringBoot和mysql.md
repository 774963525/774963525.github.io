### Doker 部署java项目和mysql 


1. 创建mysql镜像
```
 docker run -d -e MYSQL_ROOT_PASSWORD=root --name mysql8  mysql:8.0.17  --default-authentication-plugin=mysql_native_password

 '-d' 表示后台启动,可以用 '-it'代替.
 'i'表示为已交互模式运行容器
 't'为容器重新分配一个伪终端
 '--name' 为容器起名
 'mysql:8.0.17' mysql的版本号
 由于mysql 8 的新特性,
 加一个--default-authentication-plugin=mysql_native_password
```

连接上后去可视化测试,**注意:**创建一个同名的数据库后才可以导入本机导出的mysql文件.

2. 配置java项目中的配置页 

`spring.datasource.url=jdbc:mysql://mysql8:3306/learn`

**mysql8: 我的mysql镜像中准备好的容器名;**

**leran: 容器对应的database**

将密码修改为创建容器时的密码

碰到个奇怪的问题:保存后打完包,配置页修改的内容变回之前的.未解决.

3. 根据之前的文档重新打包

4. 容器互联

```
docker run --name test100 --link mysql8:mysql8 -d -p 8080:8080 test100
	
 -p 端口映射
 --name 为容器 起一个别名 可以略写--name
 --link mysql8 第一个参数为运行 mysql 镜像后容器的名称，mysql8 第二个参数为别名，此处和 application.properties 文件中连接mysql的地址保持一致 
 test100 刚刚 build 的 java 项目镜像名称
```

完成.

