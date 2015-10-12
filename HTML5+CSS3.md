# 索引
<!-- MarkdownTOC -->

- [WEB 基础学习笔记](#web-基础学习笔记)
    - [1. HTML5 新增内容](#1-html5-新增内容)
        - [1.1 新增的元素](#11-新增的元素)
        - [1.2 新增的属性](#12-新增的属性)
        - [1.3 新增表单元素与属性](#13-新增表单元素与属性)
        - [1.4 input元素type类型](#14-input元素type类型)
        - [1.5 增强的页面元素](#15-增强的页面元素)
    - [2. CSS3 基本样式](#2-css3-基本样式)
        - [2.1 CSS样式-背景](#21-css样式-背景)
        - [2.2 CSS样式-文本](#22-css样式-文本)
        - [2.3 CSS样式-字体](#23-css样式-字体)
        - [2.4 CSS样式-链接](#24-css样式-链接)
        - [2.5 CSS样式-列表](#25-css样式-列表)
        - [2.6 CSS样式-表格](#26-css样式-表格)
        - [2.7 CSS样式-轮廓](#27-css样式-轮廓)
    - [3 CSS 定位](#3-css-定位)
        - [3.1 CSS 定位-定位](#31-css-定位-定位)
        - [3.2 CSS 定位-浮动](#32-css-定位-浮动)
        - [3.3 CSS 外边距合并](#33-css-外边距合并)
    - [4. CSS 选择器](#4-css-选择器)
        - [4.1 属性选择器](#41-属性选择器)
        - [4.2 后代选择器](#42-后代选择器)
        - [4.3 子元素选择器](#43-子元素选择器)
        - [4.4 相邻兄弟选择器](#44-相邻兄弟选择器)
    - [5. CSS 页面特效](#5-css-页面特效)
        - [5.1 CSS 2D效果](#51-css-2d效果)
        - [5.2 CSS 3D效果](#52-css-3d效果)
        - [5.3 CSS 过渡](#53-css-过渡)
        - [5.4 CSS 动画](#54-css-动画)
        - [5.5 CSS 多列](#55-css-多列)
        - [5.6 CSS3 动画](#56-css3-动画)

<!-- /MarkdownTOC -->


<a name="web-基础学习笔记"></a>
# WEB 基础学习笔记

<a name="1-html5-新增内容"></a>
## 1. HTML5 新增内容

<a name="11-新增的元素"></a>
#### 1.1 新增的元素

|元素    |说明           |
|:------|:--------------|
|article|元素时可以嵌套使用的，可以表示插件，强调独立性|
|section|不推荐没有标题的内容使用该元素，强调分段或分块|
|nav    |html5中不能使用menu代替nav|
|aside  |表示当前或文章的附属信息部分|
|time   |`<time datetime="2015-10-10T20:00Z"></time>`|
|header |可以出现多次|
|hgroup |可以用来包裹多个标题|
|address|联系人，地址，联系方式等|

<a name="12-新增的属性"></a>
#### 1.2 新增的属性

|属性            |说明           |
|:--------------|:--------------|
|contentEditable|使当前元素下内容可编辑，如 ul|
|designMode     |在 js 中设置 on/off 启动，全局控制contentEditable属性|
|hidden         |显示/隐藏|
|spellcheck     |查看拼写正确与否，chrome中没有反应|
|tabindex       |属性值为数字，可以控制按tab键选择的顺序|
|pubdate        |`<time datetime="2015-10-10T20:00Z" pubdate="true"></time>` 明确发布时间|

<a name="13-新增表单元素与属性"></a>
#### 1.3 新增表单元素与属性

|属性         |说明           |
|:-----------|:--------------|
|form        |指定一个 form 属性，属性值为表单的 id，即可声明该元素从属于指定表单|
|formaction  |为提交按钮增加不同的formaction属性，使单击不同的按钮时可以将表单提交到不同的页面|
|formmethod  |指定post/get，对每一个表单元素分别指定不同的提交方法|
|formenctype|对表单元素分别指定不同的编码方式|
|formtarget  |分别指定提交后在何处打开所需加载的页面|
|autofocus   |为文本框、选择框或按钮控件加上该属性，当画面打开时，该控件自动获得光标焦点|
|required    |应用在输入元素上，在提交时，如果内容为空白，则不允许提交，同时在浏览器中显示信息提示文字|
|label       |为所有可使用元素的表单元素，button、select等，定义labels属性，属性值为一个NodeList对象，代表该元素所绑定的元素元素所构成的集合，[参考视频](http://www.jikexueyuan.com/course/772_4.html?ss=1)|
|control     |在元素内部放置一个表单元素，并且通过该元素的control属性来访问该表单元素|
|placeholder |指当文本框处于未输入状态时显示的输入提示，当文本框处于未输入状态且未获取光标焦点时，模糊显示输入提示文字|
|list        |与下拉菜单选择有关，[参考视频](http://www.jikexueyuan.com/course/801_2.html?ss=1)|
|autocomplete|on/off值控制|
|pattern     |input元素中使用，用于限制输入内容|
|selectionDirection|chrome不支持，[参考视频](http://www.jikexueyuan.com/course/801_3.html?ss=1)|
|indeterminate     |可以再JavaScript脚本代码中对该元素使用该属性，以说明复选框处于“尚未明确是否选取”状态，[参考视频](http://www.jikexueyuan.com/course/801_4.html?ss=1)|

<a name="14-input元素type类型"></a>
#### 1.4 input元素type类型
|属性    |说明          |
|:------|:-------------|
|url    |点击提交时会验证文本框中输入的信息是否为url格式  |
|email  |点击提交时会验证文本框中输入的信息是否为email格式|
|date   |自动生成日历选项框供选择|
|time   |自动生成时间选项|
|datetime|与time类似|
|datetime-local|本地时间|
|month  |自动生成日历选项框供选择|
|week   |自动生成日历选项框供选择|
|number |提交前自动检查，如果不为数字，将提交空白数据,可以设置min、max以及step|
|range  |滑竿，可以设置min、max以及step,如不设置max，默认为100|
|search ||
|tel    ||
|color  |生成颜色选择器，[参考资料](http://www.jikexueyuan.com/course/835_3.html?ss=1)|

<a name="15-增强的页面元素"></a>
#### 1.5 增强的页面元素

|元素    |属性   |说明     |
|:-------|:-----|:-------|
|figure  |figurecaption|[参考视频](http://www.jikexueyuan.com/course/852.html)|
|details |summary|[参考视频](http://www.jikexueyuan.com/course/852.html)|
|mark    | |为文字添加高亮效果|
|progress| |生成进度条，[参考视频](http://www.jikexueyuan.com/course/852_2.html?ss=1)|
|meter   | |生成进度条，[参考视频](http://www.jikexueyuan.com/course/852_2.html?ss=1)|
|ol      |start设置从什么数字开始，reversed倒序| |
|dl      |dt，dd|[参考视频](http://www.jikexueyuan.com/course/852_3.html?ss=1) |

<a name="2-css3-基本样式"></a>
## 2. CSS3 基本样式

<a name="21-css样式-背景"></a>
#### 2.1 CSS样式-背景

|属性                  |属性     |描述      |
|:--------------------|:--------|:--------|
|background-image     |:url("image.jpg"); |设置背景图片|
|background-color     ||设置元素的背景颜色   |
|background-attachment|如：fixed|背景图像是否固定或者随着页面的其余部分滚动|
|background-repeat    |如：no-repeat|设置背景图片是否以及如何重复|
|background-position  ||设置背景图片的起始位置|
|background-size      ||规定背景图片的尺寸   |
|background-origin    ||规定背景图片的定位区域|
|background-clip      ||规定背景的绘制区域   |

<a name="22-css样式-文本"></a>
#### 2.2 CSS样式-文本

|属性            |描述     |
|:--------------|:--------|
|color          |文本颜色|
|direction      |文本方向|
|line-height    |行高|
|letter-spacing |字符间距|
|text-align     |对齐元素中的文本|
|text-decoration|向文本添加修饰|
|text-indent    |缩进元素中文本的首行|
|text-transform |元素中的字母|
|unicode-bidi   |设置文本方向|
|white-space    |元素中空白的处理方式|
|word-spacing   |字间距|
|text-shadow    |向文本添加阴影|
|word-wrap      |规定文本的换行规则|

<a name=""></a>
<a name="23-css样式-字体"></a>
#### 2.3 CSS样式-字体

|属性            |描述     |
|:--------------|:--------|
|font-family    |设置字体系列|
|font-size      |设置字体的尺寸|
|font-size      |设置字体风格|
|font-variant   |以小型大写字体或正常字体显示文本|
|font-weight    |设置字体的粗细|

<a name="24-css样式-链接"></a>
#### 2.4 CSS样式-链接

|链接状态  |描述     |
|:--------|:--------|
|a:link   |普通的、未被访问的链接|
|a:visited|用户已访问的链接|
|a:hover  |鼠标指针位于链接的上方|
|a:active |链接被点击的时刻|

`text-decoration: none`用于去掉链接中的下划线

<a name="25-css样式-列表"></a>
#### 2.5 CSS样式-列表

|属性               |描述     |
|:------------------|:-------|
|list-style         |简写列表项|
|list-style-image   |列表项图像|
|list-style-position|列表标识位置|
|list-style-type    |列表类型,更改符号的样式|

<a name="26-css样式-表格"></a>
#### 2.6 CSS样式-表格

|属性            |描述   |
|:--------------|:------|
|border-collapse|折叠边框|

<a name="27-css样式-轮廓"></a>
#### 2.7 CSS样式-轮廓

|属性         |描述        |
|:------------|:----------|
|outline      |设置轮廓属性 |
|outline-color|设置轮廓的颜色|
|outline-style|设置轮廓的样式|
|outline-width|设置轮廓的宽度|


<a name="3-css-定位"></a>
## 3 CSS 定位

<a name="31-css-定位-定位"></a>
#### 3.1 CSS 定位-定位

CSS定位机制：普通流、浮动、绝对布局  
>普通流:元素按照其在HTML中的位置书序决定排布的过程

|属性           |描述       |
|:-------------|:----------|
|overflow      |设置元素溢出其区域发生的事情|
|clip          |设置元素显示的形状|
|vertical-align|设置元素垂直对齐方式|
|z-index       |设置元素的堆叠顺序，数越大越靠前|

|position属性 |描述       |
|:-----------|:----------|
|static  |静态，偏移量将失效|
|relative|相对位置，在页面中还占位置|
|absolute|绝对位置，在页面中不占位置，字不环绕|
|fixed   |固定在一个位置，无视滚动条|

<a name="32-css-定位-浮动"></a>
#### 3.2 CSS 定位-浮动
`float`效果类似于`absolute`，在页面中不占位置，但是字会环绕  
`inherit`：从父级继承浮动属性

<a name="33-css-外边距合并"></a>
#### 3.3 CSS 外边距合并
相邻的外边距会合并，遵循保留较大值原则

<a name="4-css-选择器"></a>
## 4. CSS 选择器

<a name="41-属性选择器"></a>
#### 4.1 属性选择器
例如`[title]{}` `[title="te"]{}` `[title~="title"] 部分匹配`

<a name="42-后代选择器"></a>
#### 4.2 后代选择器
用空格隔开，例如`p strong i{}`，执行效率高

<a name="43-子元素选择器"></a>
#### 4.3 子元素选择器
只能选择作为某元素子元素的元素，例如`h1>strong{}`

<a name="44-相邻兄弟选择器"></a>
#### 4.4 相邻兄弟选择器
可选择紧接在另一个元素后的元素，且二者有相同父元素，例如`h1+p{}`

<a name="5-css-页面特效"></a>
## 5. CSS 页面特效

<a name="51-css-2d效果"></a>
#### 5.1 CSS 2D效果

```sass
transform:translate(100px,100px);          //移动
-o-transform:translate(100px,100px);       //opera
-ms-transform:translate(100px,100px);      //IE 360
-moz-transform:translate(200px,100px);     //firefox
-webkit-transform:translate(100px,100px);  //safari chrome
```
```sass
transform:rotate(180deg);                  //旋转
-o-transform:rotate(180deg);               //opera
-ms-transform:rotate(180deg);              //IE 360
-moz-transform:rotate(180deg);             //firefox
-webkit-transform:rotate(180deg);          //safari chrome
```
```sass
transform:scale(1,2);                      //缩放
-o-transform:scale(1,2);                   //opera
-ms-transform:scale(1,2);                  //IE 360
-moz-transform:scale(1,2);                 //firefox
-webkit-transform:scale(1,2);              //safari chrome
```
```sass
transform:skew(20deg,20deg);               //倾斜
-o-transform:skew(20deg,20deg);            //opera
-ms-transform:skew(20deg,20deg);           //IE 360
-moz-transform:skew(20deg,20deg);          //firefox
-webkit-transform:skew(20deg,20deg);       //safari chrome
```
```sass
transform:matrix(2,2);                     //矩阵
-o-transform:matrix(2,2);                  //opera
-ms-transform:matrix(2,2);                 //IE 360
-moz-transform:matrix(2,2);                //firefox
-webkit-transform:matrix(2,2);             //safari chrome
```

<a name="52-css-3d效果"></a>
#### 5.2 CSS 3D效果

```sass
transform:rotateX(120deg);                  //X轴旋转
-o-transform:rotateX(120deg);               //opera
-ms-transform:rotateX(120deg);              //IE 360
-moz-transform:rotateX(120deg);             //firefox
-webkit-transform:rotateX(120deg);          //safari chrome
```
```sass
transform:rotateY(120deg);                  //Y轴旋转
-o-transform:rotateY(120deg);               //opera
-ms-transform:rotateY(120deg);              //IE 360
-moz-transform:rotateY(120deg);             //firefox
-webkit-transform:rotateY(120deg);          //safari chrome
```

<a name="53-css-过渡"></a>
#### 5.3 CSS 过渡

|属性                       |描述    |
|:-------------------------|:-------|
|transition                |设置四个过渡属性|
|transition-property       |过渡的名称|
|transition-duration       |过渡效果花费的时间|
|transition-timing-function|过渡效果的时间曲线|
|transition-delay          |过渡效果延时开始时间|

```sass
transition:width 2s,height 2s,transform 2s;         //动画过渡时间
-o-transition:width 2s,height 2s,transform 2s;      //opera
-ms-transition:width 2s,height 2s,transform 2s;     //IE 360
-moz-transition:width 2s,height 2s,transform 2s;    //firefox
-webkit-transition:width 2s,height 2s,transform 2s; //safari chrome
```

<a name="54-css-动画"></a>
#### 5.4 CSS 动画
CSS动画需要遵循 __*@keyframes*__ 规则  
>* 规定动画的时长
>* 规定动画的名称

```sass
animation:anim 5s infinite alternate;  //名称anim,时长5s,循环执行,单次动画完成后倒序执行一次
-webkit-animation:anim 5s infinite alternate;

@keyframes anim{
      0%{background:red    ;left:  0px;top:  0px}
     25%{background:blue   ;left:200px;top:  0px}
     50%{background:#ccffcc;left:200px;top:200px}
     75%{background:#00ffff;left:  0px;top:200px}
    100%{background:red    ;left:  0px;top:  0px}
}
@-webkit-keyframes anim{
      0%{background:red    ;left:  0px;top:  0px}
     25%{background:blue   ;left:200px;top:  0px}
     50%{background:#ccffcc;left:200px;top:200px}
     75%{background:#00ffff;left:  0px;top:200px}
    100%{background:red    ;left:  0px;top:  0px}
}
```

<a name="55-css-多列"></a>
#### 5.5 CSS 多列

|属性         |描述    |
|:-----------|:-------|
|column-count|分列的数量|
|column-width|分列的宽，需声明浏览器|
|column-gap  |每列之间间隔的距离|
|column-rule |每列间隔之间的线与线的颜色|

```sass
column-count:3;
-webkit-column-count:3;
-webkit-column-gap:30px;
column-gap:30px;
column-rule:5px outset #FF0000;
-webkit-column-rule:5px outset #FF0000;
```

<a name="56-css3-动画"></a>
#### 5.6 CSS3 动画

```sass
transition：property duration timing-function；  //做动画的属性，持续时间，动画方式

&:hover{
    property: XXX ;
}
```
```sass
div{
    background-color: red;
}
@-webkit-keyframes mycolor {
      0%{background-color: red;}
     40%{background-color: yellow;}
     70%{background-color: auqa;}
    100%{background-color: red;}
}
div:hover{
    -webkit-animation: mycolor 5s linear;
}
```
|属性        |描述      |
|:----------|:---------|
|linear     |匀速      |
|ease-in    |先慢后快   |
|ease-out   |先快后慢   |
|ease       |先慢再快在慢|
|ease-in-out|跟ease一样 |
