# ASUS RT-AC86U 路由器设置自动重启

~~~linux
## 编辑 wan-start 文件, 位于jffs内
cd jffs/scripts

## 用ls命令查看wan-start文件是否存在
ls 

## 编辑 wan-start 文件
vi wan-start
~~~

vi编辑器的基本用法 请查阅 /Linux/Vi 基本用法.md

~~~sh
#!/bin/sh
/koolshare/bin/ks-wan-start.sh start
cru a autoreboot_1 "50 6 * * * /sbin/reboot"
cru a autoreboot_2 "0 18 * * * /sbin/reboot"
~~~



### cru / crontab 定时命令使用方法

| key    | 描述         | 命令                                                  |
| ------ | ------------ | ----------------------------------------------------- |
| add    | 新建定时任务 | cru a <unique id> <"min hour day month week command"> |
| delete | 删除定时任务 | cru d <unique id>                                     |
| list   | 列出所有任务 | cru l                                                 |

 



