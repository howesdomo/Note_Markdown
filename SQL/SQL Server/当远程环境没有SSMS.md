# 当远程环境没有SSMS(SQL Server Management Studio)

1. 先用Windows身份连入数据库

~~~sql
Server = localhost\HOWE_SS12,1433; Database = master; Integrated Security = true;
~~~

2. 启用远程连接

~~~sql
EXEC sys.sp_configure N'remote access', N'1';
RECONFIGURE WITH OVERRIDE;
~~~



__完成第1、2点后，可以先尝试能否远程用sa进行登陆__



## 新建数据库用户

~~~sql
-- 新建用户
CREATE LOGIN [填写新建用户名] WITH PASSWORD=N'填写密码', DEFAULT_DATABASE=[master], CHECK_EXPIRATION=OFF, CHECK_POLICY=OFF
GO

-- 允许登陆到授权数据库
USE [填写需要授权给用户的数据库]
CREATE USER [填写新建用户名] FOR LOGIN [填写新建用户名]
GO

-- 授权 db_owner 给指定的数据库
USE [填写需要授权给用户的数据库]
-- 根据版本选择授权执行语句
-- SQL Server 2012
ALTER ROLE [db_owner] ADD MEMBER [填写新建用户名] 
-- SQL Server 2008
EXEC sp_addrolemember N'db_owner', N'[填写新建用户名]' 
GO
~~~



## 设置用户-属性-状态

1. 新建用户开启允许连接到数据库引擎

~~~sql
GRANT CONNECT SQL TO [填写新建用户名];
~~~

授权/拒绝 GRANT/DENY

2. sa账号启用登陆名

~~~sql
ALTER LOGIN [填写新建用户名] ENABLE;
~~~

启用/禁止 ENABLE/DISABLE

