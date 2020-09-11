#### 1.导入pom依赖

```
   <!-- mysql -->
        <dependency>
            <groupId>mysql</groupId>
            <artifactId>mysql-connector-java</artifactId>
            <version>8.0.11</version>
        </dependency>

        <!--mybatis-->
        <dependency>
            <groupId>org.mybatis.spring.boot</groupId>
            <artifactId>mybatis-spring-boot-starter</artifactId>
            <version>1.3.1</version>
        </dependency>
```

#### 2.配置application.properties 
注意mysql8的url
`com.mysql.cj.jdbc.Driver`报红是由于mysql的scope为`runtime `只在运行时使用,重新编译可以解决或者改成`<scope>compile</scope>`默认
`mybatis.mapper-locations= classpath:mapper/*.xml`必须配置 不然找不到xml
`classpath`的路径为resource.
```
spring.datasource.url = jdbc:mysql://localhost:3306/dfn?characterEncoding=utf8&useSSL=false&serverTimezone=UTC&rewriteBatchedStatements=true
spring.datasource.driver-class-name=com.mysql.cj.jdbc.Driver
spring.datasource.username = root
spring.datasource.password = abcd2007

mybatis.mapper-locations= classpath:mapper/*.xml

```

#### 3.dao不要忘记加上@Mapper