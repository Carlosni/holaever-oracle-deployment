哈咯 Oracle 自动化部署
==============================
Holaever Oracle Deployment

## Oracle 11g

> Windows 7 旗舰版（64位） + Oracle11g + Plsql

1、[下载](http://www.oracle.com/technetwork/database/enterprise-edition/downloads/index.html) Oracle 11g R2 for Windows，其中包括两个压缩包：`win64_11gR2_database_1of2.zip`，`win64_11gR2_database_2of2.zip`。

2、将两个压缩包解压到同一个目录下，即“database”，然后单击解压目录下的“setup.exe”文件： 



3、在出现的“配置安全更新”窗口中，取消“我希望通过My Oracle Support接受安全更新”，单击“下一步”： 



4、在“安装选项”窗口中，选择“创建和配置数据库”，单击“下一步”： 



5、在“系统类”窗口中，选择“桌面类”，单击“下一步”： 



6、在“典型安装”窗口中，选择Oracle的基目录，选择“企业版”和“默认值”并输入统一的密码为：Oracle11g，单击“下一步”： 



7、在“先决条件检查”窗口中，单击“下一步”： 



8、在“概要”窗口中，单击“完成”，即可进行安装： 



9、出现的安装过程如下： 





数据库创建完成后，会出现如下“Database Configuration Assistant”界面： 



选择“口令管理”，查看并修改以下用户： 
（1）普通用户：SCOTT（密码：tiger） 
（2）普通管理员：SYSTEM（密码：manager） 
（3）超级管理员：SYS（密码：change_on_install） 
修改完成后，单击“确定”。 

10、在“完成”窗口中，单击“关闭”即可。 

安装完成界面中的内容： 
Enterprise Manager Database Control URL - (orcl) : 
https://localhost:1158/em 
数据库配置文件已经安装到 C:\app\Administrator,同时其他选定的安装组件也已经安装到 C:\app\Administrator\product\11.2.0\dbhome_1。 

Oracle完成安装后，会在系统中进行服务的注册，在注册的这些服务中有以下两个服务必须启动，否则Oracle将无法正常使用： 



（1）OracleOraDb11g_home1TNSListener：表示监听服务，如果客户端要想连接到数据库，此服务必须打开。在程序开发中该服务也要起作用。 
（2）OracleServiceORCL：表示数据库的主服务，命名规则：OracleService数据库名称。此服务必须打开，否则Oracle根本无法使用。 

附： 

A、32位Oracle 11g Client（win32_11gR2_client.zip）的安装注意点： 

在选择安装类型时，选择“管理员”，如下图： 



其他的步骤和安装服务器端类似。 

B、PL/SQL Developer 安装注意点： 

安装PL/SQL前，需要先安装Oracle客户端。 

我的系统环境： 
1、64位Windows 7旗舰版 
2、64位Oracle 11g R2 DB 
3、32位Oracle 11g Client（64位Oracle 11g Client会出错） 
4、PL/SQL Development 8.0.4 

注意： 
（1）PL/SQL Development不要安装在默认的C:\Program Files (x86)目录下，否则会报错，原因是不能解析这个带()的路径。 
（2）当Oracle客户端安装的是64位Oracle 11g Client，启动PL/SQL Developer会提示错误。 
原因：oci.dll是64位的，32位应用程序PL/SQL Developer无法加载，可以安装一个32位的Oracle Client来解决。 

=================================================

一、安装64位oracle11g

二、安装32位oracle11g客户端

三、安装pl/sql developer。在tools->perference->connection里面设置oracle home和oci library。

 如：oracle home : C:\app\Administrator\product\11.2.0

  oci library : C:\app\Administrator\product\11.2.0\client_1\bin\oci.dll

有疑惑?1
----------

如果你有任何问题，可以随时查阅
[哈咯（Holaever）数据库工程面板](https://trello.com/b/h0rHIVo0)。
