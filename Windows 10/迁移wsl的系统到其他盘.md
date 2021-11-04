# 迁移wsl的系统到其他盘

### 整体流程如下图

![image-20211104114542892](https://howesdomo.github.io/Note_Markdown/Windows 10/迁移wsl的系统到其他盘/image-20211104114542892.png)



### 下面分部详细解释每行命令的意思

~~~bash
wsl -l ## 查看目前 wsl 上的 linux 系统

## 导出系统到指定路径 ( 注意导出目录结构要预先创建, 否则报错找不到指定路径 )
wsl --export Ubuntu-18.04 F:\wsl\Ubuntu-18.04.tar

## 导出成功后, 注销系统
wsl --unregister Ubuntu-18.04

## 查看目前 wsl 上的 linux 系统是否注销成功 ( 没有指定版本即成功注销 )
wsl -l

## 导入系统到非 C盘 位置
wsl --import Ubuntu-18.04 F:\wsl\Ubuntu-18.04 F:\wsl\Ubuntu-18.04.tar

## 查看导入情况, 发现有导入的版本 18.04
wsl -l


## (未知有没有用) 转换为 wsl 2
## 作用是 这样迁移过后的子系统默认还是wsl1版本的,如果是1版本是不能玩儿docker的.
wsl --set-version Ubuntu-18.04 2
~~~



