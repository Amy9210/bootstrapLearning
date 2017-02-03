# 说明：学习bootstrap时记的一些笔记，学习资料来源于[慕课网](http://www.imooc.com/learn/141)及[bootstrap官网](http://getbootstrap.com/)。学习内容为bootstrap3.3.7版本。小节的“css源码”链接是bootstrap的css文件中相应的该部分的代码，并且有些有个人的注释，欢迎大家提出意见及建议~
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
<h1>二、排版</h1>
<h2>1、标题</h2>（[css源码](https://github.com/Amy9210/bootstrapLearning/blob/master/layout/title.css)）</br>
<strong>定义规则：</strong></br> 
<strong>样式说明：</strong></br>
（1）重新设置了margin-top和margin-bottom的值，  h1~h3重置后的值都是20px；h4~h6重置后的值都是10px。</br>
（2）所有标题的行高都是1.1（也就是font-size的1.1倍）,而且文本颜色和字体都继承父元素的颜色和字体。</br>
（3）固定不同级别标题字体大小，h1=36px，h2=30px，h3=24px，h4=18px，h5=14px和h6=12px。</br>
在Bootstrap中为了让非标题元素和标题使用相同的样式，还特意定义了.h1~.h6六个类名。</br>
<strong>用&lt;small&gt;标签显示副标题：</strong></br>
（1）行高都是1，而且font-weight设置了normal变成了常规效果（不加粗），同时颜色被设置为灰色（#999）。</br>
（2）由于&lt;small&gt;内的文本字体在h1~h3内，其大小都设置为当前字号的65%；而在h4~h6内的字号都设置为当前字号的75%。</br>
<h2>2、段落</h2>（[css源码](https://github.com/Amy9210/bootstrapLearning/blob/master/layout/p.css)）</br>
<strong>样式说明：</strong></br>
1、全局文本字号为14px(font-size)。</br>
2、行高为1.42857143（line-height），大约是20px。</br>
3、颜色为深灰色（#333）；</br>
4、字体为"Helvetica Neue", Helvetica, Arial, sans-serif;（font-family），或许这样的字体对我们中文并不太合适，但在实际项目中，大家可以根据自己的需求进行重置，该设置都定义在&lt;body&gt;元素上，由于这几个属性都是继承属性，所以Web页面中文本（包括段落p元素）如无重置都会具有这些样式效果。</br>
<strong>用css预处理器进行自定义排版设置：</strong></br>
在Bootstrap中，排版设置的默认值都存在variables.less文件中(Sass版本存在variables.scss中)的两个变量：</br>
LESS版本：</br>
@font-size-base: 14px; @line-height-base: 1.428571429; // 20/14</br>
Sass版本：</br>
$font-size-base: 14px !default; $line-height-base: 1.428571429 !default; // 20/14</br>
第一条语句用于设置字体大小，第二条语句用于设置行高。系统默认使用这两个值产生整个页面相应的margin、padding和line-height的值。换句话说，只需要修改这两个变量的值，然后重新编译，就可以自定义自己的Bootstrap排版样式。</br>
<h2>3、强调内容</h2>（[css源码](https://github.com/Amy9210/bootstrapLearning/blob/master/layout/emphasis.css)）
如果想让一个段落p突出显示，可以通过添加类名“.lead”实现，其作用就是增大文本字号，加粗文本，而且对行高和margin也做相应的处理。</br>
“.lead”对应的样式如下：
    lead {
    margin-bottom: 20px;
    font-size: 16px;
    font-weight: 300;
    line-height: 1.4;
    }
    @media (min-width: 768px) {/*大中型浏览器字体稍大*/
    .lead {
     font-size: 21px;
     }
     }
除此之外，Bootstrap还通过元素标签:&lt;small$gt;、&ltstrong&gt;、&lt;em&gt;和&lt;cite&gt;给文本做突出样式处理。

`b,strong {

  font-weight: bold; /*文本加粗*/
  
}

small,.small {

  font-size: 85%; /*标准字体的85%,也就是14px * 0.85px，差不多12px*/
  
}`

&lt;cite&gt;没有在源码3.3.7版本中找到源码，但使用&lt;cite&gt;标签时会显示斜体效果。
&lt;em&gt;与&lt;i&gt;均为斜体显示标签。
<h2>4、强调相关的类</h2>（[css源码](https://github.com/Amy9210/bootstrapLearning/blob/master/layout/emphasis-text.css)）
在Bootstrap中除了使用标签&lt;strong&gt;、&ltem&gt等说明正文某些字词、句子的重要性，Bootstrap还定义了一套类名，这里称其为强调类名（类似前面说的“.lead”）,这些强调类都是通过颜色来表示强调，具本说明如下：</br>
•	.text-muted：提示，使用浅灰色（#999）</br>
•	.text-primary：主要，使用蓝色（#428bca）</br>
•	.text-success：成功，使用浅绿色(#3c763d)</br>
•	.text-info：通知信息，使用浅蓝色（#31708f）</br>
•	.text-warning：警告，使用黄色（#8a6d3b）</br>
•	.text-danger：危险，使用褐色（#a94442)</br>
<h2>5、文本对齐风格</h2>（[css源码](https://github.com/Amy9210/bootstrapLearning/blob/master/layout/text-align.css)）
•	在CSS中常常使用text-align来实现文本的对齐风格的设置。其中主要有四种风格：
•	  ☑  左对齐，取值left
•	  ☑  居中对齐，取值center
•	  ☑  右对齐，取值right
•	  ☑  两端对齐，取值justify
•	为了简化操作，方便使用，Bootstrap通过定义四个类名来控制文本的对齐风格：
•	  ☑   .text-left：左对齐
•	  ☑   .text-center：居中对齐
•	  ☑   .text-right：右对齐
•	  ☑   .text-justify：两端对齐
<h2>6、列表</h2>（[css源码](https://github.com/Amy9210/bootstrapLearning/blob/master/layout/list.css)）
<h3>6.1无序列表和有序列表</h3>
Bootstrap对于列表，只是在margin上做了一些调整。
ul,
ol {
  margin-top: 0;
  margin-bottom: 10px;
}
ul ul,
ol ul,
ul ol,
ol ol {
  margin-bottom: 0;
}

<h3>6.2去点列表</h3>
通过给ul或ol添加一个类名“.list-unstyled”,这样就可以去除默认的列表样式的风格。
<h3>6.3内联列表</h3>
通过添加类名“.list-inline”来实现内联列表，简单点说就是把垂直列表换成水平列表，而且去掉项目符号（编号），保持水平显示。也可以说内联列表就是为制作水平导航而生。
<h3>6.4定义列表</h3>
对于定义列表而言，Bootstrap并没有做太多的调整，只是调整了行间距，外边距和字体加粗效果。
<h3>6.5水平定义列表</h3>
水平定义列表就像内联列表一样，Bootstrap可以给dl添加类名“.dl-horizontal”给定义列表实现水平显示效果。
源码添加了一个媒体查询。也就是说，只有屏幕大于768px的时候，添加类名“.dl-horizontal”才具有水平定义列表效果。其实现主要方式：
1、将dt设置了一个左浮动，并且设置了一个宽度为160px </br>
2、将dd设置一个margin-left的值为180px，达到水平的效果
3、当标题宽度超过160px时，将会显示三个省略号
<h2>7、代码</h2>（[css源码](https://github.com/Amy9210/bootstrapLearning/blob/master/layout/CodePreKbd.css)）
在Bootstrap主要提供了三种代码风格：
1、使用&lt;code&gt;&lt;code&gt;来显示单行内联代码
2、使用&lt;pre&gt;&lt;/pre&gt;来显示多行块代码
3、使用&lt;kbd&gt;&lt;/kbd&gt;来显示用户输入代码
在使用代码时，用户可以根据具体的需求来使用不同的类型：
1、&lt;code&gt;：一般是针对于单个单词或单个句子的代码
2、&lt;pre&gt;：一般是针对于多行代码（也就是成块的代码）
3、&lt;kbd&gt;:一般是表示用户要通过键盘输入的内容

code风格：
`<div>Bootstrap的代码风格有三种：
  <code>&lt;code&gt;</code>
  <code>&lt;pre&gt;</code>
  <code>&lt;kbd&gt;</code>
</div>`
pre风格：
`<div>
<pre>
&lt;ul&gt;
&lt;li&gt;...&lt;/li&gt;
&lt;li&gt;...&lt;/li&gt;
&lt;li&gt;...&lt;/li&gt;
&lt;/ul&gt;
</pre>
</div>`
kbd风格：
`<div>请输入<kbd>ctrl+c</kbd>来复制代码，然后使用<kbd>ctrl+v</kbd>来粘贴代码</div>`
