### Docker Java镜像导入jar包


1.新建文件夹,将打包好的jar包放入,创建Dockerfile文件
```
FROM java:8-alpine
//复制以spring-boot-demo-0.0.1-SNAPSHOT为名的jar包
COPY spring-boot-demo-0.0.1-SNAPSHOT.jar /

WORKDIR /

ENTRYPOINT ["java", "-jar", "spring-boot-demo-0.0.1-SNAPSHOT.jar"]

EXPOSE 8080
```
**EXPOSE命令只是声明了容器应该打开的端口并没有实际上将它打开**,也就是说，如果你不用-p或者-P中指定要映射的端口，你的容器是不会映射端口出去的，从而我们知道我们是没有办法在Dockerfile里面进行端口映射的，我们只能在容器启动的时候或者在docker-compose文件中使用ports来指定将要映射的端口。

那我们的EXPOSE能用来干什么呢?第一点就是写在Dockerfile中进行声明，能让运维人员或者后来者知道我们开启了容器的哪些端口。还有一点就是，当我们声明了EXPOSE端口之后，我们使用-P命令进行随机映射的时候，是会对这个端口进行映射的。比如说我们现在对一个tomcat容器进行EXPOSE 9999声明，那么我们进行-P随机映射的时候是会对9999端口进行映射的.

2.打开终端,cd进入新建文件夹`docker build -t [名(必须小些)] .`创建

3.`docker ps -a`可查看成功与否

4.`docker run -p 8080:8080 [name]`  即可运行
