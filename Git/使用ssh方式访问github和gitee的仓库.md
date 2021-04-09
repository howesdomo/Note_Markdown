## 1. 私钥与公钥

### (1) 创建 github rsa 私钥与公钥

~~~cmd.exe
ssh-keygen -t rsa -C '邮箱地址' -f .ssh/github_id_rsa
~~~

要求输入和确认passphrase, 输入回车即可(共2次)

![1](https://howesdomo.github.io/Note_Markdown/Git/使用ssh方式访问github和gitee的仓库/1.png)

### (2) 创建 gitee rsa 私钥与公钥

~~~cmd.exe
ssh-keygen -t rsa -C '邮箱地址' -f .ssh/gitee_id_rsa
~~~

![2](https://howesdomo.github.io/Note_Markdown/Git/使用ssh方式访问github和gitee的仓库/2.png)

要求输入和确认passphrase, 输入回车即可(共2次)



### (3) 修改Config文件

在 .ssh 目录下打开 config文件 ( 若不存在config文件则新建一个 )

其中 **Host** 和 **HostName** 填写git服务器的域名，**IdentityFile** 指定私钥的路径

Windows系统 拷贝下列配置代码 (linux, mac os 系统需要修改 **IdentityFile** 的值指向私钥的路径 )

~~~ini
# gitee
Host gitee.com
HostName gitee.com
PreferredAuthentications publickey
IdentityFile C:\Users\填写用户名\.ssh\gitee_id_rsa

# github
Host github.com
HostName github.com
PreferredAuthentications publickey
IdentityFile C:\Users\填写用户名\.ssh\github_id_rsa
~~~



### (4) 各自将公钥更新到 github 和 gitee 的 ssh 中

公钥是以 **.pub** 结尾的文件。

拷贝 **gitee_id_rsa.pub** 文本内容到 **gitee**

拷贝 **github_id_rsa.pub** 文本内容到 **github**



### (5) 测试ssh

测试连接 github，若有成功信息（successfully），则表示配置成功。

~~~cmd.exe
ssh -T git@github.com
~~~

![3](https://howesdomo.github.io/Note_Markdown/Git/使用ssh方式访问github和gitee的仓库/3.png)



测试连接gitee，若有成功信息（successfully），则表示配置成功。

~~~cmd.exe
ssh -T git@gitee.com
~~~

![4](https://howesdomo.github.io/Note_Markdown/Git/使用ssh方式访问github和gitee的仓库/4.png)





## 2. 额外设置 TortoiseGit

我平时喜欢使用 TortoiseGit，如果需要使用 ssh 方式连接外部 Git服务器，需要重置SSH客户端，

选中 git安装目录下 usr\bin\ssh.exe

![5](https://howesdomo.github.io/Note_Markdown/Git/使用ssh方式访问github和gitee的仓库/5.png)