# ORACLE数据库导入导出基本技巧
## 1、oracle数据库导入dmp文件

1、以sysdba用户的身份登录到plsql,如下图：

![image](https://github.com/liertao/ORACLE/blob/master/images/loginplsql.png)

2、在打开的plsql左侧列表中找到users,如下图所示，单击右键创建用户，如图中右侧所示填写响应的用户名和密码，等相关信息，然后点击应用。

![image](https://github.com/liertao/ORACLE/blob/master/images/createUser.png)

3、打开一个sql窗口，执行

grant dba to userName;

grant connect to userName;

grant resource to userName;

4、在dos中执行如下命令：

imp cmes/cmes@orcl file=d:\20170822cmes.dmp full=y

其中file是数据库文件的路径

## 2、oracle导出dmp文件

## 3、oracle数据库加载Excel文件数据

oracle数据库导入Excel文件数据使用的是odbc导入器，首先需要Excel文件每列带有一个标题行，推荐标题字段与数据表字段对应，

1、工具-》选择ODBC导入器，如下图：

![image](https://github.com/liertao/ORACLE/blob/master/images/tools.png)

2、打开界面如下图：

![image](https://github.com/liertao/ORACLE/blob/master/images/odbcp1.png)

图中 用户/系统DSN 选择 Excel Files，用户名、口令选择要导入的用户

3、然后选择到Oracle的数据页，如下图：

![image](https://github.com/liertao/ORACLE/blob/master/images/odbcp2.png)

选择所有者，数据表，然后在左侧红框中会出现选择对应字段到对应列，在右侧可以选择数据类型或者是sql函数，最后点击执行导入即可

万级别的数据导入时间大概为10秒左右（紧供参考）。
