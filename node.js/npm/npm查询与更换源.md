# npm查询与更换源

### 查看当前的镜像源地址

~~~shell
npm get registry
~~~



### 更换镜像源地址

方法一：

~~~shell
## 使用 npm config set key value 命令
## 设置 key = registry 设置指定的镜像地址, value = http://yyy.xxx.com
npm config set registry http://yyy.xxx.com
~~~

例子：

~~~shell
npm config set registry http://registry.npm.taobao.org # 淘宝镜像地址

npm config set registry http://registry.cnpmjs.org # cnpm镜像地址
~~~





方法二: 

~~~shell
npm --registry https://registry.npm.taobao.org info underscore ## npm info underscore依然是为了检验是否设置成功
~~~





方法三:

修改配置文件~/.npmrc （win系统在C:\Users\用户名.npmrc） 加入下面内容

~~~
registry = https://registry.npm.taobao.org
~~~



__以上三种方法实际上都是修改 .npmrc 文件的 registry 设置__



方法四:

安装cnpm包，然后就可以敲cnpm install [name]命令了，很方便~~

~~~shell
npm install -g cnpm --registry=https://registry.npm.taobao.org
~~~

