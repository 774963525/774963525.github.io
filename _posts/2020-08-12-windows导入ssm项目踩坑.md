### windows导入ssm项目踩坑 

#### 一.注意jdk，tomcat环境
#### 二.如果版本不同需要下载相应的版本

踩坑：
		

1.安装jdk的时候同目录下应有jre，但是没有
<img src="/Users/wujiyan/Library/Application Support/typora-user-images/image-20200812210938966.png" alt="image-20200812210938966" style="zoom:33%;" />		
​		解决：有同版本的jdk没有卸载干净

2. 安装tomcat  startup.bat启动不了 
		解决： 
	
	原因一：
	tomcat在启动时，会读取环境变量的信息，需要一个CATALINA_HOME 与JAVA_HOME的信息，CATALINA_HOME即tomcat的主目录，JAVA_HOME即java安装的主目录，jdk的主目录。首先，要在环境变量处，配置JAVA_HOME，注意变量值是jdk的主目录，不是bin目录，并且不要加分号
	
	<img src="https://img-blog.csdnimg.cn/20190619152316584.png" alt="在这里插入图片描述" style="zoom:50%;" />
			
	原因二：
	如果这样配置，startup.bat还是一闪而过，可以右键点击startup.bat，编辑，在文本的最后敲上pause，保存后重新运行startup.bat，这时候窗口不会再一闪而过，而是停留在桌面上（调试成功，把pause去掉即可）。此时，有问题的话会在首行显示。
	
	

#### 三.下载的项目需要转成maven项目

#### 四.eclipse配置tomcat

https://www.cnblogs.com/li-yan-long/p/10339919.html
踩坑：配置完无法启动tomcat 报错oom

解决：点击run旁边的小三角，按run configuration，argument vmargument中添加`-Xms256M -Xmx512M -XX:PermSize=256m -XX:MaxPermSize=512m`

<img src="/Users/wujiyan/Library/Application Support/typora-user-images/image-20200812213243207.png" alt="image-20200812213243207" style="zoom:50%;" />

仍然报错

解决：

<img src="/Users/wujiyan/Library/Application Support/typora-user-images/image-20200812213400253.png" alt="image-20200812213400253" style="zoom:50%;" />

#### 五.成功跑出