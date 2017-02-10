# 说明：学习bootstrap时记的一些笔记，学习资料来源于[慕课网](http://www.imooc.com/learn/141)及[bootstrap官网](http://getbootstrap.com/)。学习内容为bootstrap3.3.7版本。小节的css源码是bootstrap的css文件中相应的该部分的代码，并且有些有个人的注释.
<h1>一、Bootstrap简介</h1>
<h2>Bootstrap简介：</h2>
Bootstrap 是 2011 年八月在 GitHub 上发布的开源产品。由 Twitter 的 Mark Otto 和 Jacob Thornton 开发。
Bootstrap 是一个用于开发 Web 应用程序和网站的前端框架，是html，css和JavaScript工具集。
Bootstrap包含的内容：基本结构，css，组件，JavaScript插件，定制。
<h2>如何使用bootstrap：</h2>
官方网站链接：http://getbootstrap.com/</br>
Bootstrap2（最后的版本2.3.2）与bootstrap3的主要区别：
![](https://github.com/Amy9210/bootstrapLearning/blob/master/images/difference.png)  
Bootstrap框架主要包含的文件：</br>
![](https://github.com/Amy9210/bootstrapLearning/blob/master/images/bootstrapFiles.jpg)  </br> 
Bootstrap中的js文件均依赖于jQuery，因此jQuery要在bootstrap之前引入。 以下为引入文件的位置及顺序：</br>
![](https://github.com/Amy9210/bootstrapLearning/blob/master/images/howToUseBootstrap.jpg)  </br>
<h2>Bootstrap全局样式：</h2>
* 移除body的margin声明
* 设置body的背景色为白色
*	为排版设置了基本的字体、字号和行高
*	设置全局链接颜色，且当链接处于悬浮“:hover”状态时才会显示下划线样式</br>
<h1>bootstrap中less的使用</h1>
bootstrap源码是由less编写的。bootstrap的less源码包含四十多个单独的less文件，将样式分开可以使多人分工合作，从而方便开发；此外有利于后期维护；最后也有利于用户修改样式。</br>
在[bootstrap官网](http://getbootstrap.com/getting-started/)下载“source code”，解压后就可看到Less的文件夹。</br>开发人员在编写样式的时候，对页面的元素进行了分离。
