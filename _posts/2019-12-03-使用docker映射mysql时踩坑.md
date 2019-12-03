### Docker 映射mysql容器踩坑. 

1.安装docker

2.由于docker需要外网,故使用阿里云的源

3.`docker pull ubuntu` 拉取ubuntu最新版本,如果本地没有,则去阿里源拉取,需要选择版本号则 `docker pull ubuntu:0.0.0`

4.拉取mysql 

5.`docker run -d --name test -p 10086:3306 -e `

`MYSQL_ROOT_PASSWORD=123456 mysql:8.0.17` -d表示后台启动;test为名字;-p表示自定义映射端口号,-P则为计算机自动生成;123456为密码 mysql版本为8.0.17

6.`docker ps -a` 可以看到当前拥有的所有镜像,其中mysql的容器状态为up表示正在运行.进入`docker exec -it [容器名或容器id]`

7.成功,`mysql -uroot-p`创建一个database,去本地可视化查看,使用10086端口并输入密码准备连接,然而报错.

```
ERROR 2059 (HY000): Authentication plugin 'caching_sha2_password' cannot be loaded
```
原因是mysql新版本特性导致密码出现问题,命令行可以,可视化连接不上.

8.命令行输入`ALTER USER 'root'@'%' IDENTIFIED WITH mysql_native_password BY '123456'`修改密码为'123456'

9.可视化连接成功