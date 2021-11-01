### 安装 TypeScript

![image-20211015095856632](https://howesdomo.github.io/Note_Markdown/node.js/Typescript/TypeScript运行环境配置/image-20211015095856632.png)

~~~bash
npm i -g ts-node
npm i -g typescript ## 把 ts 文件转换 js 文件依赖工具
~~~

__推荐将 TypeScript 安装在全局环境中__, 所以加上了 -g



### 开启系统运行脚本权限

![image-20211015095915824](https://howesdomo.github.io/Note_Markdown/node.js/Typescript/TypeScript运行环境配置/image-20211015095915824.png)

需要用管理员权限开启 powershell

~~~powershell
set-ExecutionPolicy RemoteSigned
~~~

![image-20211015095956369](https://howesdomo.github.io/Note_Markdown/node.js/Typescript/TypeScript运行环境配置/image-20211015095956369.png)

无管理员权限会报错



### 提示缺少 xxx 包文件

![image-20211015105224737](https://howesdomo.github.io/Note_Markdown/node.js/Typescript/TypeScript运行环境配置/image-20211015105224737.png)

~~~bash
npm install
~~~

根据 package.json 下载所需要的包

