# ORACLE数据库导入导出基本技巧
## 1、oracle数据库导入dmp文件

1、以sysdba用户的身份登录到plsql,如下图：

![image](https://github.com/liertao/ORACLE/blob/master/images/loginplsql.png)

2、在打开的plsql左侧列表中找到users,如下图所示，单击右键创建用户，如图中右侧所示填写响应的用户名和密码，等相关信息，然后点击应用。

![image](https://github.com/liertao/ORACLE/blob/master/images/createUser.png)

3、打开一个sql窗口，执行

·grant dba to userName;

·grant connect to userName;

·grant resource to userName;

4、在dos中执行如下命令：

·imp cmes/cmes@orcl file=d:\20170822cmes.dmp full=y

其中file是数据库文件的路径

## 2、oracle导出dmp文件

