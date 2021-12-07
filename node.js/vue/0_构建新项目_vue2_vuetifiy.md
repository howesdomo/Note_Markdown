# vue+vuetifiy项目构建

~~~bash
## vue create [项目名称]
vue create vue_testcors // 创建一个名为 vue_testcors 的 vue项目
~~~

![image-20211203155231100](https://howesdomo.github.io/Note_Markdown/node.js/vue/0_构建新项目_vue2_vuetifiy/image-20211203155231100.png)



__遇到的坑：__ __选择vue3后, 添加 vuetify 插件报错. 暂时未能解决__

![image-20211203155352358](https://howesdomo.github.io/Note_Markdown/node.js/vue/0_构建新项目_vue2_vuetifiy/image-20211203155352358.png)



~~~bash
# 创建 vue 项目成功后, 进入创建的项目目录里面
cd vue_testcors

# 增加 vuetify 插件
vue add vuetify
~~~

![image-20211203155647313](https://howesdomo.github.io/Note_Markdown/node.js/vue/0_构建新项目_vue2_vuetifiy/image-20211203155647313.png)



~~~bash
## vuetify 插件成功添加后, 运行 vue 项目
npm run serve
~~~



成功看到 vuetify 的图标, 表示添加成功

![image-20211203155926691](https://howesdomo.github.io/Note_Markdown/node.js/vue/0_构建新项目_vue2_vuetifiy/image-20211203155926691.png)