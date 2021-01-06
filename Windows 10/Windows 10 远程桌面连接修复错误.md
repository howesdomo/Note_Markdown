# Windows 10 远程桌面连接修复错误

注册表工具

拷贝以下地址

~~~html
计算机\HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Policies\System
~~~

在 `CredSSP\Parameters` 中创建 `AllowEncryptionOracle` 类型为 `REG_DWORD` 数值为 `2`

操作如下图

![01](https://howesdomo.github.io/Note_Markdown/Windows 10/Windows 10 远程桌面连接修复错误/01.png)



