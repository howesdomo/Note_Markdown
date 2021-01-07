# Windows 10 修改网卡MAC地址

1. 开启注册表编辑器，前往以下的位置

~~~注册表
计算机\HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Class\{4d36e972-e325-11ce-bfc1-08002be10318}
~~~

以下图为例，每个00XX的代号都代表一个网卡，要想分辨出你想要的网卡型号，点击编号，然后在右侧的DriverDesc值中确定型号。

![sss](https://howesdomo.github.io/Note_Markdown/Windows 10/Windows 10 修改网卡MAC地址/01.png)

2. 确定网卡所属的项，在里面新建一个名为 `NetworkAddress` 的 `字符串值`，数据填写MAC地址（不含符合 - ）。

![sss](https://howesdomo.github.io/Note_Markdown/Windows 10/Windows 10 修改网卡MAC地址/02.png)

3. 此时需要重启连接进行验证。可以在相应的“网络连接”中单击右键，选择“禁用”，然后再点击“启用”即可。

4. 用CMD 执行 `ipconfig -all`，观察查看更新后的MAC地址。