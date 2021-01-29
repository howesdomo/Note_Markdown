# SSMS清除历史记录

SQL Server Management Studio清除连接过账号密码记录

清除之前务必关闭__SSMS__



### SSMS版本号18或以上

SSMS（SQL Server Management Studio）在SqlServer2016版及以上，都是单独的独立安装包。

~~~javascript
-- 以SSMS18为例 （含SSMS18.0 ~ SSMS18.9等）SQL Server Management Studio 2016 delete the file 

C:\Users\%username%\AppData\Roaming\Microsoft\SQL Server Management Studio\18.0\UserSettings.xml
~~~



### SQL Server 2012 ~ SQL Server 2014

SSMS（SQL Server Management Studio）在SqlServer2016版本之前，都是集成在SqlServer程序中的,无法单独安装。

~~~javascript
--(2014)：SQL Server Management Studio 2014 delete the file C:\Users\%username%\AppData\Roaming\Microsoft\SQL Server Management Studio\12.0\SqlStudio.bin
直接在我的电脑或任何一个文件夹的地址栏里输入后面路径,回车进入目录：%AppData%\Microsoft\SQL Server Management Studio\12.0\
删除 SqlStudio.bin文件，重新启动 SSMS 就可以了。。
 
 
-- (2012)：SQL Server Management Studio 2012 delete the file C:\Users\%username%\AppData\Roaming\Microsoft\SQL Server Management Studio\11.0\SqlStudio.bin　
直接在我的电脑或任何一个文件夹的地址栏里输入后面路径,回车进入目录：%AppData%\Microsoft\SQL Server Management Studio\11.0\
删除SqlStudio.bin文件，重新启动 SSMS 就可以了。。
~~~



### SQL Server 2005 ~ SQL Server 2008

~~~javascript
服务器列表、登陆帐户、密码等信息都记录在 ：
--(2008)： %AppData%\Microsoft\Microsoft SQL Server\100\Tools\Shell\SqlStudio.bin 
直接在我的电脑或任何一个文件夹的地址栏里输入后面路径,回车进入目录：%AppData%\Microsoft\Microsoft SQL Server\100\Tools\Shell\
删除 SqlStudio.bin文件，再次启动 SSMS 就可以了。。
 
--(2005)： %AppData%\Microsoft\Microsoft SQL Server\90\Tools\Shell\mru.dat
 直接在我的电脑或任何一个文件夹的地址栏里输入后面路径,回车进入目录：%AppData%\Microsoft\Microsoft SQL Server\90\Tools\Shell\
删除mru.dat文件，再次启动 SSMS 就可以了。。
~~~

