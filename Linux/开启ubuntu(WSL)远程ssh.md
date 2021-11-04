# 开启ubuntu(WSL)远程ssh

### 第一步

~~~bash
sudo vi /etc/ssh/sshd_config
~~~

修改以下内容

~~~config
## 开启注释
Port 22 

## 开启注释
ListenAddress 0.0.0.0

## 修改配置为 yes
PasswordAuthentication yes
~~~

保存修改后的文件, 用 cat 命令查看是否修改成功

~~~bash
cat /etc/ssh/sshd_config
~~~



### 第二步

~~~bash
sudo dpkg-reconfigure openssh-server ## 创建 RSA_KEY
~~~

![image-20211104110642086](https://howesdomo.github.io/Note_Markdown/Linux/开启ubuntu(WSL)远程ssh/image-20211104110642086.png)



### 第三步

~~~bash
sudo service ssh restart ## 重启SSH服务
~~~

![image-20211104110746315](https://howesdomo.github.io/Note_Markdown/Linux/开启ubuntu(WSL)远程ssh/image-20211104110746315.png)



### 第四步

打开 finalshell, 填上 ip, port, linux 系统的账号密码即可

![image-20211104110841341](https://howesdomo.github.io/Note_Markdown/Linux/开启ubuntu(WSL)远程ssh/image-20211104110841341.png)

