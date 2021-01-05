# Hello MarkDown



## 标题

### 1. 使用 = (一级标题) 和 - (二级标题) (一级二级标题都带横线)

### 2. 使用 # 标记

使用 1 个井号 表示 1级标题, 2 个井号表示 2级标题, 效果如下

![01](https://howesdomo.github.io/Note_Markdown/Markdown/Hello_MarkDown/标题_01.png)


## 段落

段落的换行是使用两个以上的空格加回车  



## 字体

*斜体*  使用星号包围

使用2个星号 __粗体__  或者2个下划线包围 **粗体**

使用3个星号 ___粗体加斜体___  或者 3个下划线包围 ***粗体加斜体***



## 分割线

你可以在一行中用三个以上的星号、减号、底线来建立一个分隔线，行内不能有其他东西。你也可以在星号或是减号中间插入空格。下面每种写法都可以建立分隔线：



3个或以上星号

***



3个或以上减号

---



3个或以上底线

___



## 删除线

使用两个波浪线包围内容即可

~~8158~~



## 下划线

使用一对 <u></u> 包围

<u>下划线效果</u>



## 脚注

脚注是对文本的补充说明。

Markdown 脚注的格式如下:



效果Gif

![脚注效果Gif](https://howesdomo.github.io/Note_Markdown/Markdown/Hello_MarkDown/脚注_01.gif)



创建脚注的作用类似这样, [^DOMO]



[^DOMO]: 多磨



## 列表

### 无序列

无序列表使用星号(*)、加号(+)或是减号(-)作为列表标记，这些标记后面要添加一个空格，然后再填写内容：

~~~ markdown
* 李白
* 杜甫
* 苏轼

+ 李白
+ 杜甫
+ 苏轼

- 李白
- 杜甫
- 苏轼
~~~

* 李白
* 杜甫
* 苏轼



### 有序列

使用数字并加上 . 号来表示，如：

~~~html
1. 第一点
2. 第二点
3. 第三点
~~~



1. 第一点
2. 第二点
3. 第三点



### 列表嵌套

只需在子列表中的选项前面添加四个空格即可：

~~~markdown
1. 第一项：
    - 第一项嵌套的第一个元素
    - 第一项嵌套的第二个元素
2. 第二项：
    - 第二项嵌套的第一个元素
    - 第二项嵌套的第二个元素
~~~



实际效果

1. 第一项：
    - 第一项嵌套的第一个元素
    - 第一项嵌套的第二个元素
2. 第二项：
    1. 第二项内嵌套有序元素 1
    2. 第二项内嵌套有序元素 2



## 区块

区块引用是在段落开头使用 > 符号 ，然后后面紧跟一个 **空格** 符号：



> 这里是区块的范围
>
> 这里是区块的范围
>
> 这里是区块的范围

区块是可以嵌套的

~~~markdown
> 最外层
> > 第一层嵌套
> > > 第二层嵌套
~~~

实际效果如下

> 最外层
> > 第一层嵌套
> >
> > > 第二层嵌套



### 区块中使用列表

~~~markdown
> 区块中使用列表
> 1. 第一项
> 2. 第二项
> + 第一项
> + 第二项
> + 第三项
~~~

> 区块中使用列表
> 1. 第一项
> 2. 第二项
> + 第一项
> + 第二项
> + 第三项



### 列表中使用区块

如果要在列表项目内放进区块，那么就需要在 > 前添加四个空格的缩进。

区块中使用列表实例如下：

~~~markdown
1. 第一项
   > 第一项列表中使用区块 Start
   > ABC
   > 第一项列表中使用区块 End
2. 第二项
~~~

1. 第一项

   > 第一项列表中使用区块 Start
   >
   > ABC
   >
   > 第一项列表中使用区块 End

2. 第二项



## 代码

### 代码区块

用 ``` 包裹一段代码，并指定一种语言（也可以不指定）：

~~~markdown
```javascript
$(document).ready(function () {
    alert('Hello Markdown');
});
```
~~~

显示结果如下:

```javascript
$(document).ready(function () {
    alert('Hello Markdown');
});
```



### 代码片段

用一对 ` (反引号) 包围代码内容

~~~ markdown
`alert('Hello Markdown');`
~~~

例如:

执行以下代码 `alert('Hello Markdown');` 弹出对话框



## 链接

使用方法如下：

```	markdown
(链接名称)[链接地址]

或者

前往 <链接地址> 必应
```

```markdown
[访问百度](www.baidu.com)

或者

前往 <www.bing.com>  必应
```

实际效果如下:

[访问百度](www.baidu.com)

或者

前往 <www.bing.com>  必应



#### 高级链接

可以通过变量来设置一个链接，变量赋值在文档末尾进行：

```markdown
这是一个通过变量设置的链接 [必应][argsBing]
这是一个通过变量设置的链接 [谷歌][argsGoogle]


[argsBing]: http://www.bing.com
[argsGoogle]:http://www.google.com
```

实际效果如下:

这是一个通过变量设置的链接 [必应][argsBing]
这是一个通过变量设置的链接 [谷歌][argsGoogle]




[argsBing]: http://www.bing.com
[argsGoogle]:http://www.google.com



## 图片

插入图片的语法如下:

```markdown
![alt 属性文本](图片地址)

![alt 属性文本](图片地址 "可选标题")
```

使用实例:

```markdown
![RUNOOB 图标](http://static.runoob.com/images/runoob-logo.png)

![RUNOOB 图标](http://static.runoob.com/images/runoob-logo.png "RUNOOB")
```

![icon](https://howesdomo.github.io/Note_Markdown/Markdown/Hello_MarkDown/图片_01.png)





### 高级图片

Markdown 还没有办法指定图片的高度与宽度，如果你需要的话，你可以使用普通的 <img> 标签。

![icon](https://howesdomo.github.io/Note_Markdown/Markdown/Hello_MarkDown/图片_01.png)





