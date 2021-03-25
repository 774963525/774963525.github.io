`CONNECT CCBIMAGE2@orcl`连接用户CCBIMAGE2

即可查询` select * FROM CCBIMAGE2."tttt";`

数据库应该连接system 

因为查询的是`用户名.表名`,所以如果连接CCBIMAGE2会找不到表名。