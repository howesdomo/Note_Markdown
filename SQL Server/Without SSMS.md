# Without SSMS （当远程环境没有SSMS）

1. 先用Windows身份连入数据库

~~~sql
Server = localhost\HOWE_SS12,1433; Database = master; Integrated Security = true;
~~~

2. 启用远程连接

~~~sql
EXEC sys.sp_configure N'remote access', N'1';
RECONFIGURE WITH OVERRIDE;
~~~

3. sa账号开启允许连接到数据库引擎

~~~sql
GRANT CONNECT SQL TO [sa];
~~~

授权/拒绝 GRANT/DENY

4. sa账号启用登陆名

~~~sql
ALTER LOGIN [sa] ENABLE;
~~~

启用/禁止 GRANT/DENY



## 新建数据库用户

~~~sql
-- 新建用户
CREATE LOGIN [填写新建用户名] WITH PASSWORD=N'填写密码', DEFAULT_DATABASE=[master], CHECK_EXPIRATION=OFF, CHECK_POLICY=OFF
GO

-- 允许登陆到授权数据库
USE [填写需要授权给用户的数据库]
CREATE USER [填写新建用户名] FOR LOGIN [填写新建用户名]
GO

-- 授权 db_owner 
USE [填写需要授权给用户的数据库]
ALTER ROLE [db_owner] ADD MEMBER [填写新建用户名]
GO
~~~

