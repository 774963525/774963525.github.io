## 安装登录mysql后  登录mysql 出现此报错

 

这是未添加环境变量的问题：

下面解决方案：

    1.执行命令    open .zshrc

 2.在最后一行添加：

    export PATH=${PATH}:/usr/local/mysql/bin
    

3.然后   立即生效

    source ~/.zshrc

 



之后就可以在zsh  愉快的通过命令

$ mysql -u root -p

登录mysql了

原文链接：https://blog.csdn.net/Cherishlife_/article/details/88713226