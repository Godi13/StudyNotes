#索引

<!-- MarkdownTOC -->

- [图解CSS3读书笔记](#图解css3读书笔记)
  - [1.CSS3选择器](#1css3选择器)
    - [CSS中常见的通配符](#css中常见的通配符)
  - [2.CSS3 边框](#2css3-边框)
    - [边框基本属性](#边框基本属性)
    - [图片边框属性](#图片边框属性)
    - [圆角边框属性](#圆角边框属性)
    - [盒子阴影属性](#盒子阴影属性)
  - [3.CCS3 背景](#3ccs3-背景)
    - [背景的基本属性](#背景的基本属性)
    - [背景新增属性](#背景新增属性)
    - [多背景属性](#多背景属性)
  - [4.CSS3 文本](#4css3-文本)
    - [字体类型](#字体类型)
    - [文本类型](#文本类型)
    - [溢出文本属性](#溢出文本属性)
    - [文本换行](#文本换行)
  - [5. CSS3 颜色特性](#5-css3-颜色特性)
    - [透明属性](#透明属性)
  - [6. CSS3 盒模型](#6-css3-盒模型)
    - [盒模型属性](#盒模型属性)
    - [内容溢出属性](#内容溢出属性)
    - [自由缩放属性](#自由缩放属性)
    - [外轮廓属性](#外轮廓属性)
  - [7. CSS3 伸缩布局盒模型](#7-css3-伸缩布局盒模型)
    - [旧版本Flexbox模型的基本使用](#旧版本flexbox模型的基本使用)
    - [混合版本Flexbox模型的基本使用](#混合版本flexbox模型的基本使用)
    - [新版本Flexbox模型的基本使用](#新版本flexbox模型的基本使用)
  - [8. CSS3 多列布局](#8-css3-多列布局)
    - [多列布局基本属性](#多列布局基本属性)
    - [多列布局列宽属性](#多列布局列宽属性)
    - [多列布局列数属性](#多列布局列数属性)
    - [多列布局列间距属性](#多列布局列间距属性)
    - [多列布局列边框样式属性](#多列布局列边框样式属性)
    - [多列布局跨列属性](#多列布局跨列属性)
    - [多列布局列高度属性](#多列布局列高度属性)
  - [9. CSS3 渐变](#9-css3-渐变)
    - [线性渐变](#线性渐变)
    - [径向渐变](#径向渐变)
    - [重复渐变](#重复渐变)
  - [10. CSS3 变形](#10-css3-变形)
    - [变形属性详解](#变形属性详解)
    - [2D变形](#2d变形)
    - [多重变形](#多重变形)
  - [11. CSS3 过渡](#11-css3-过渡)
    - [过渡属性](#过渡属性)
  - [12. CSS3 动画](#12-css3-动画)
  - [13. 媒体特性与Responsive设计](#13-媒体特性与responsive设计)

<!-- /MarkdownTOC -->

<a name="图解css3读书笔记"></a>
# 图解CSS3读书笔记
<a name="1css3选择器"></a>
## 1.CSS3选择器

  * [基本选择器](#1css3选择器)
    - 通配选择器：  * {}
    - 元素选择器
    - ID选择器
    - 类/多类选择器
    >IE 6 不支持多类选择器，其将以末尾类名为准
    - 群组选择器：selector1,selectorN
  * [层次选择器](#1css3选择器)
    - 后代选择器：E F
    - 子选择器：E > F
    - 相邻兄弟选择器：E + F
    - 通用选择器：E ～ F
  * [伪类选择器](#1css3选择器)：E:pseudo-class {property:value}
    - 动态伪类选择器

      |选择器|类型|功能描述|
      |-----|:----:|-------|
      |E:link|链接伪类选择器|选择匹配的E元素，而且匹配元素被定义了超链接并__未__被访问过。常用于链接锚点上|
      |E:visited|链接伪类选择器|选择匹配的E元素，而且匹配元素被定义了超链接并__已__被访问过。常用于链接锚点上|
      |E:active|用户行为伪类选择器|选择匹配的E元素，且匹配元素被激活。常用于锚点与按钮上|
      |E:hover|用户行为伪类选择器|选择匹配的E元素，且用户鼠标在停留再元素E上。IE6及以下浏览器仅支持a:hover|
      |E:focus|用户行为伪类选择器|选择匹配的E元素，且匹配的元素获得焦点|

    - 目标伪类选择器  
        E:target 选择匹配E的所有元素，且匹配元素被相关URL指向
      >目标伪类选择器是动态选择器，只有存在URL指向该匹配元素时，样式效果才会生效。
    - 语言伪类选择器
    - UI元素状态伪类选择器

      |选择器|类型|功能描述|
      |-----|:----:|-------|
      |E:checked|选中状态伪类选择器|匹配选中的复选按钮或单选按钮表单元素|
      |E:enabled|启用状态伪类选择器|匹配所有启用的表单元素|
      |E:disabled|不可用状态伪类选择器|匹配所有禁用的表单元素|

    - 结构伪类选择器

      |选择器        |功能描述|
      |-------------|-------|
      |E:first-child|作为父元素的第一个子元素的元素E。与E:nth-child(1)等同|
      |E:last-child|作为父元素的最后一个子元素的元素E。与E:nth-last-child(1)等同|
      |E:root|选择匹配元素E所在文档的根元素。在HTML文档中，根元素始终是html，此时该选择器与html类型选择器匹配的内容相同|
      |E F:nth-child(n)|选择父元素E的第n个子元素F。其中n可以是整数(1、2、3)、关键字（even、odd）、可以是公式（2n+1、-n+5），而且n值起始值为1，而不是0|
      |E F:nth-last-child(n)|选择元素E的倒数第n个子元素F。此选择器与E F:nth-child(n)选择器计算顺序刚好想法，但使用方法都是一样的，其中 :nth-last-child(1) 始终匹配的时最后一个元素，与 :last-child 等同|
      |E:nth-of-type(n)|选择父元素内具有指定类型的第n个E元素|
      |E:nth-last-of-type(n)|选择父元素内具有指定类型的倒数第n个E元素|
      |E:first-of-type|选择父元素内具有指定类型的第一个E元素，与E:nth-of-type(1)等同|
      |E:last-of-type|选择父元素内具有指定类型的最后一个E元素，与E:nth-last-of-type(1)等同|
      |E:only-child|选择父元素只包含一个子元素，且该子元素匹配E元素|
      |E:only-of-type|选择父元素只包含一个同类型的子元素，且该子元素匹配E元素|
      |E:empty|选择没有子元素的元素，而且该元素也不包含任何文本节点|

    - 否定伪类选择器  
      E:not(F) 匹配所有除元素F外的E元素

  * [伪元素](#1css3选择器)

  |元素名         |功能描述|
  |--------------|-------|
  |::first-letter|选择文本块的第一个字母，除非在同一行中包含一些其他元素|
  |::first-line|选择文本块的第一个字母，除非在同一行中包含一些其他元素|
  |::before,::after|要为伪元素生成内容，还需要配合content属性|
  |::selection|用来匹配突出显示的文本，仅接受background，color两个属性|

  * [属性选择器](#1css3选择器)

  |选择器         |功能描述|
  |--------------|-------|
  |E[attr]|选择匹配具有属性attr的E元素。其中E可以省略，表示选择定义了attr属性的任意类型元素|
  |E[attr=val]|选择匹配具有属性attr的E元素，并且attr的属性值为val（其中val区分大小写），同样E元素省略时表示选择定义了attr属性值为val的任意类型元素|
  |E[attr~=val]|选择匹配E元素，且E元素定义了属性attr，attr属性值具有多个空格分隔的值，其中一个值等于val。例如，.info[title~=more]将匹配元素具有类名info，而且这个元素设置了一个属性title，同时title属性值以包含了“more”的任何元素，例如`<a class="info" title="click here for more information">click me</a>`|
  |E[attr*=val]|选择匹配元素E，且E元素定义了属性attr，其属性值任意位置包含了“val”。换句话说，字符串val与属性值中的任意位置相匹配|
  |E[attr^=val]|选择匹配元素E，且E元素定义了属性attr，其属性值以val开头的任何字符串|
  |E[attr$=val]|选择匹配元素E，且E元素定义了属性attr，其属性值以val结尾的任何字符串。与E[attr^=val]相反|

  E[attr|=val] 选择匹配E元素，且E元素定义了属性attr，attr属性值是一个具有val或者以val-开始的属性值。常用于lang属性（例如lang=“en-us”）。例如p[lang|=en]将匹配定义为英语的任何段落，无论时英式英语还是美式英语

>注意：`E[attr=val]`选择器中，属性和属性值必须完全匹配，特别对于属性值是词列表的形式，例如，`<a href="#" class="links item"></a>`，其中`a[class="links"]{...}`是找不到匹配元素，只有`a[class="link item"]{...}`才匹配。

<a name="css中常见的通配符"></a>
#### CSS中常见的通配符

|通配符|功能描述|示例|
|-----|-------|---|
|^|匹配起始符|span[class^=span]表示选择以类名以“span”开头的所有span元素|
|$|匹配终止符|a[herf$=pdf]表示选择以“pdf”结尾的href属性的所有a元素|
|\*|匹配任意字符|a[title*=site]匹配a元素，而且a元素的title属性值中任意位置有“site”字符的任何字符串|

<a name="2css3-边框"></a>
## 2.CSS3 边框
<a name="边框基本属性"></a>
#### 边框基本属性
`border: border-width border-style border-color;` 其中border-style必须有

  * border-width: 设置元素边框的粗细，默认值“medium”（大约等于3~4px）
  * border-color: 设置元素边框的颜色

  `border-color: [ <color> | trabsparent ]{1,4} | inherit`

    下列属性中color是复数colors
      border-top-colors:[ <color> | trabsparent ]{1,4} | inherit;
      border-right-colors:[ <color> | trabsparent ]{1,4} | inherit;
      border-bottom-colors:[ <color> | trabsparent ]{1,4} | inherit;
      border-left-colors:[ <color> | trabsparent ]{1,4} | inherit;

  * border-style: 设置元素边框的类型
    - border-top-style:设置元素顶部边框类型
    - border-right-style:设置元素右边边框类型
    - border-bottom-style:设置元素底部边框类型
    - border-left-style:设置元素左边边框类型

    |属性值|功能描述|
    |-----|-------|
    |none|定义无边框|
    |hidden|与“none”相同。不过应用与表时除外，对于表，hidde用于解决边框冲突|
    |dotted|定义点状边框|
    |dashed|定义虚线边框|
    |solid|定义实线边框|
    |double|定义双线。双线的宽度等于border-width的值|
    |groove|定义3D凹槽边框，其效果取决于border-color的值|
    |ridge|定义3D垄状边框，其效果取决于border-color的值|
    |inset|定义3D inset边框，其效果取决于border-color的值|
    |outset|定义3D outset边框，其效果取决于border-color的值|
    |inherit|规定应该从父元素继承边框样式，部分浏览器不支持这个属性值|

<a name="图片边框属性"></a>
#### 图片边框属性
`border-image: none | <image> [<number> | <percentage>] {1,4} [/ <broder-width> {1,4}] ?[stretch | repeat | round] {0,2}`

* none: 默认值，表示边框无背景图片
* \<image\>: 设置背景图片，这跟background-image一样，可以使用绝对或相对的URL地址，来指定边框的背景图片
* \<number\>: number时一个数值，用来设置边框或者边框背景图片的大小，其单位时像素（px），可以使用1~4个值，表示4个方位的值，可以参考border-width设置方式
* \<percentage\>: percentage也是用来设置边框或者边框背景图片的大小，跟number不同之处是，percentage使用的是百分比
* stretch、repeat、round: 这三个属性参数是用来设置边框背景图片的铺放方式，类似于background-position，其中stretch会拉伸边框背景图片、repeat是会重复边框背景图片、round是平铺边框背景图片，其中stretch为默认值

border-image 和 background-image 之间有一些类似之处，包括图片的引用和排列方式等

<a name="圆角边框属性"></a>
#### 圆角边框属性

`border-radius: none | <length> {1,4}[/<length>{1,4}] ？`

特殊应用：

* 当border-radius半径小于或等于border的厚度时，元素边框内部就不具有圆角效果。如圆角半径比边框值大时，内圆角就会出来。
* 元素相邻边有不同的宽度，这个角将会从宽的边平滑过渡到窄的一边，其中一条边甚至可以是0，元素相邻转角是由大向小转。

注意：表格元素table用border-radius时不一样的，当表格样式属性border-collapse是collapse时，表格不能正常显示，只有border-collapse属性值为separate时，表格圆角才能正常显示。

<a name="盒子阴影属性"></a>
#### 盒子阴影属性

`box-shadow:none | [ <length> <length> <length>?<length>? || <color> ], [ <length> <length> <length>? <length>? || <color> ]+`  
简写：  
`box-shadow:none | [inset x-offset y-offset blur-radius spread-radius color], [inset x-offset y-offset blur-radius spread-radius color]`

* none：默认值，元素没有任何阴影效果。
* inset：阴影类型，可选值。如果不设置，其默认的投影方式是外阴影；如果取其唯一值“inset”，就是给元素设置内阴影。
* x-offset：阴影水平偏移量，其值可以是正负值。如果取正值，则阴影在元素的右边，反之取负值，阴影在元素的左边。
* y-offset：阴影垂直偏移量，其值可以是正负值。如果取正值，则阴影在元素的底部，反之取负值，阴影在元素的顶部。
* blur-radius：阴影模糊半径，可选参数。其值只能是正值，如果取值为“0”时，表示阴影不具有模糊效果，如果取值越大，阴影的边缘就越模糊。
* spread-radius：阴影扩展半径，可选参数。其值可以是正负值，如果取值为正值，则整个阴影都延展扩大，反之取值为负值，则整个阴影都缩小。
* color：阴影颜色，可选参数，如果不设定任何颜色时，浏览器会取默认色，但各浏览器默认色不一样，特别是在Webkit内核下的浏览器将无色，也就是透明，建议不要省略这个参数。

<a name="3ccs3-背景"></a>
## 3.CCS3 背景

<a name="背景的基本属性"></a>
#### 背景的基本属性

`background: [<background-color>], [<background-image>], [<background-repeat>], [<background-attachment>], [<background-position>]`

* background-color（背景颜色）  
`background-color: transparent || <color>` 默认值为“transparent”

* background-image（背景图片）  
`background-image: none || <url>` 默认值为“none”

* background-repeat（背景图片展开方式）  
`background-repeat: repeat || repeat-x || repeat-y || no-repeat` 默认值为“repeat”

* background-attachment（背景图片是固定还是滚动）  
`background-attachment: scroll || fixed` 默认值为“scroll”  
注意：取值为“fixed”时，一般运用在html或body标签上，使用在其他标签上不能达到固定效果

* background-position（背景图片位置）  
`background-position: <percentage> || <length> || [left|center|right], [top|center|bottom]` 默认值为“(0,0) || (0%, 0%) || (left top)”

<a name="背景新增属性"></a>
#### 背景新增属性

* background-origin:指定绘制背景图片的起点  
`background-origin: padding || border || content` 较老  
`background-origin: padding-box || border-box || content-box` 新版
    * padding-box(padding):默认值，决定background-position起始位置从padding的外边缘（border的内边缘）开始显示背景图片。
    * border-box(border):决定background-position起始位置从border的外边缘开始显示背景图片。
    * content-box(content):决定background-position起始位置从content的外边缘（padding的内边缘）开始显示背景图片。

>注意：IE8一下版本background-origin的默认值为border，背景图片的background-position是从border开始显示背景图片。  
如果background-attachment设置为fixed，background-origin将不起任何作用。

* background-clip:指定背景图片的显示范围  
`bakgroung-clip : border-box || padding-box || content-box`

    * border-box（背景图片再边框下，这个也是background-clip的默认值）

    >默认值，元素背景图像从元素的border区域向外裁剪，即元素边框之外的背景图片都将被裁减掉。

    * padding-box（背景延伸到padding的外边缘，但不会超出边框的范围）

    >元素背景图像从padding区域向外裁剪，即元素padding区域之外的背景图像将被裁剪掉。

    * content-box（背景仅在内容区域绘制，不会超出padding和边框的范围）

    >元素背景图像从content区域向外裁剪，即元素内容区域之外的背景图像将被裁剪掉。

  >在Webkit内核下，background-clip还有一个text属性，配合Webkit内核的私有属性text-fill-color:transparent可以制作背景图片填充文本的效果。

* background-size:指定背景图片的尺寸大小  
`background-size: auto || <length> || <perentage> || cover || contain`
    * auto:默认值。将保持背景片的原始高度和宽度。
    * <length>:取具体的整数值（例如px值），将改变背景图片的大小。
    * <percentage>:取值为百分值，可以时0%~100%。此时，同样改变背景图片的大小，但此值是相对于元素的宽度来进行计算，并不是根据背景图片的宽度来进行计算。
    * cover:将背景图片放大，以适合铺满整个容器。但这种方法会致使背景图片失真。
    * contain:保持背景图像本身的宽高比例，将背景图像缩放到宽度或高度正好适应所定义背景容器的区域。

* background-break:指定内联元素的背景图片进行平铺时的循环方式

      >目前仅支持Firefox，并且需要修改属性写法

<a name="多背景属性"></a>
#### 多背景属性

>background:[background-image] | [background-position] | [background-size] | [background-repeat] | [background-attachment] | [background-clip] | [background-origin],*  

>可以把上面的缩写拆解成以下形式：  

>background-image:url1,url2,...,urlN;  
background-repeat:repeat1,repeat2,...,repeatN;  
background-position:position1,position2,...,positionN;  
background-size:size1,size2,...,sizeN;  
background-attachment:attachment1,attachment2,...,attachmentN;  
background-clip:clip1,clip2,...,clipN;  
background-origin:origin1,origin2,...,originN;  
background-color:color;

<a name="4css3-文本"></a>
## 4.CSS3 文本

<a name="字体类型"></a>
#### 字体类型
|属性       |功能描述|取值|
|----------|------|----|
|font-family|定义字体的类型||
|font-style|定义字体样式|normal（默认）、italic（斜体）、oblique（倾斜）|
|font-weight|定义字体粗细，除了关键字，还可以设定数值100~900|normal（默认）、bold（粗体）、bolder（特粗体）、lighter（细体）|
|font-size-adjust|定义是否强制对文本使用同一尺寸||
|font-stretch|定义是否横向拉伸变形字体||
|font-variant|定义字体大小写|normal（默认）、small-caps（小型的大写字母字体）|

<a name="文本类型"></a>
#### 文本类型

|属性       |功能描述     |取值    |
|----------|------------|--------|
|word-spacing|定义词与词之间的间距|normal(默认)、length（设置词与词之间的距离值，可以是负数）|
|letter-spacing|定义字符之间的间距|normal(默认)、length（设置字符与字符之间的距离，可以是负数）|
|vertical-align|定义文本的垂直对齐方式|baseline(默认)、sub（上标对齐）、super（下标对齐）、bottom（行框底端对齐）、text-bottom（行内文本底端对齐）、top（顶端对齐）、middle（居中对齐）、blink（闪烁线）|
|text-decoration|定义文本的修饰线|none（默认值）、underline（下划线）、overline（上划线）、line-through（删除线）、blink（闪烁线）|
|text-indent|定义文本首行缩进|length（长度单位）和百分比|
|text-align|定义文本水平对齐方式|left（左对齐）、center（水平居中）、right（右对齐）、justify（两端对齐）|
|line-height|定义文本行高|normal（默认）、长度值、百分比值、数字|
|text-transform|定义文本大小写|none（默认）、uppercase（大写）、lowercase（小写）、capitalize（首字大写）|
|text-shadow|定义文本阴影效果||
|white-space|定义文字之间和文本之间的空白符间距|normal（默认）、nowrap（空白符合并、换行符忽略）、pre（空白符、换行符保留）、pre-wrap（空白符、换行符保留）、pre-line（空白符合并、换行符保留）|
|direction|控制文本流入的方向|ltr（默认）、rtl（文本从右到左流入）、inherit（文本流入方向由继承获得）|

* 文本阴影  
`text-shadow: none | <length> none | [<shadow>,] * <shadow> 或 none | <color> [,<color>]*` 也就是  
`text-shadow:[颜色 color] x轴位移（x-offset） y轴位移（y-offset） 模糊半径（blur-radius）`

<a name="溢出文本属性"></a>
#### 溢出文本属性

* text-overflow  
`text-overflow:clip | ellipsis`
    * clip:不显示省略标记（…），只是简单的裁切。
    * ellipsis:文本溢出时显示省略标记（…），省略标记插入的位置是最后一个字符。
    >实际上，text-overflow属性仅用于决定文本溢出时是否显示省略标记（…），并不具备样式定义的功能。要实现文本溢出时裁切文本显示省略标记（…）效果，还需要两个属性的配合：强制文本再一行显示（white-space:nowrap）和溢出内容隐藏（overflow:hidden），并且需要定义容器的宽度。

<a name="文本换行"></a>
#### 文本换行

* word-wrap  
`word-wrap:normal | break-word`  
>注意：word-wrap 应用在`<pre>`和`<table>`中时，没有任何效果。
    * normal：默认值，浏览器只在半角空格或连字符的地方进行换行。
    * break-word:将内容在边界内换行（不截断英文单词换行）

* word-break  
`word-break:normal | break-all | keep-all`  
用于设置或检索对象内文本的字内换行行为，在出现多种语言的情况下尤为有用。
    * normal： 默认值，根据语言自己的规则确定换行方式，中文到边界上的汉字换行，英文从整个单词换行。
    * break-all：可以强行截断英文单词，达到词内换行。
    >不同的浏览器下效果不一
    * keep-all：不允许字断开。如果是中文把前后标点符号内的一个汉字短语整个换行，英文单词整个换行；如果出现某个英文字符长度超过容器边界，后面的部分将撑破容器；如果边框为固定属性，则后面部分无法显示。
    >在Chrome和Safari下不生效

* white-space  
`white-space: normal || pre || nowrap || pre-line || pre-wrap || inherit`
    * normal：默认值。空白处会被浏览器忽略。可以通过这个值恢复到属性的默认值。
    * pre：文本空白处会被浏览器扣留，其行为类似于HTML中的`<pre>`标签效果。
    * nowrap：文本不会换行，文本会在同一行上，直到碰到换行标签`<br/>`为止。
    * pre-line：合并空白符序列，但保留换行符，此属性不支持IE7.0-、Firefox 3.0- 和 Opera 9.2-以下版本的浏览器。
    * pre-wrap：保留空白符序列，但是正常进行换行，此属性值不支持IE7.0和Firefox 3.0以下版本浏览器。
    * inherit：继承父元素的white-space属性值，此属性值再所有的IE浏览器都不支持。

<a name="5-css3-颜色特性"></a>
## 5. CSS3 颜色特性

<a name="透明属性"></a>
#### 透明属性

`opacity: alphavalue || inherit`

* alphavalue: 默认值为1，可以取0~1任意浮点数。其中取值为1时，元素是完全不透明的；反之，取值为0时，元素是完全透明不可见。其值不可以是负数。  
* inherit： 表示继承父元素的opacity设置的值，即继承父元素的不透明性。

>opacity属性、alpha通道、transparent属性值的区别：

>opacity是CSS3中专门用来设置透明度的一个属性，其取值范围从0~1,0表示完全透明，1表示不透明。  
opacity只能给整个元素设置一个透明度，并且其透明度直接会继承给其后代元素。  

>alpha通道是用来对元素设置透明度，针对元素的背景色、文字颜色、边框颜色等设置透明度。

>transparent属性值给元素的颜色设置完全透明色，例如背景色、边框色、文字颜色、阴影色等，相当于alpha的通道值设置为0。在CSS3中，可以在一切指定的颜色值的属性中指定transparent值。

<a name="6-css3-盒模型"></a>
## 6. CSS3 盒模型

CSS中主要的几种盒模型：inline、inline-block、block、table、absolute position、float  
IE6以下版本浏览器的宽度包含了元素的padding和border值

<a name="盒模型属性"></a>
#### 盒模型属性

`boxsizing: content-box | border-box | inherit`

* content-box：默认值，让元素维持W3C的标准盒模型。`element width/height = border + padding + content width/height`
* border-box：让元素维持IE传统的盒模型。
* inherit：此值使元素继续父元素的盒模型模式。
* padding-box：Firefox浏览器独有。`element width/height = content + padding width/height`

<a name="内容溢出属性"></a>
#### 内容溢出属性

`overflow-x: visible | hidden | scroll | auto | no-display | no-content`  
`overflow-y: visible | hidden | scroll | auto | no-display | no-content`

* visible：默认值。表示不剪切容器中的任何内容、不添加滚动条，元素将被剪切为包含对象的窗口大小，而且clip属性设置将失效。
* auto：再需要时剪切内容并添加滚动条。也就是说当内容超过容器的宽度或者高度时，溢出的内容将会隐藏在容器中，并且会添加滚动条，用户可以拖动滚动条查看隐藏在容器中的内容。
* hidden：内容溢出容器时，所有内容都将隐藏，而且不显示滚动条。
* scroll：不管内容有没有溢出容器，overflow-x都会显示横向的滚动条，而overflow-y会显示纵向的滚动条。
* no-display：当内容溢出容器时不显示元素，此时类似于元素添加了display：none声明一样。
* no-content：当内容溢出容器时不显示内容，此时类似于添加了visibility：hidden声明一样。

<a name="自由缩放属性"></a>
#### 自由缩放属性

`resize: none | both | horizontal | vertical | inherit `

* none：用户不能拖动元素修改尺寸大小。
* both：用户可以拖动元素，同时修改元素的高度和宽度。
* horizontal：用户可以拖动元素，仅可以修改元素的宽度，但不能修改元素的高度。
* vertical：用户可以拖动元素，仅可以修改元素的高度，但不能修改元素的宽度。
* inherit：继承父元素的resize属性值。

>表单中的文本域textarea元素默认情况就具有resize功能，属性默认值为“both”

<a name="外轮廓属性"></a>
#### 外轮廓属性

`outline: [outline-color] || [outline-style] || [outline-width] || [outline-offset] || inherit`

* outline-color：定义轮廓线的颜色，省略时此参数默认值为黑色。
* outline-style：定义轮廓线的样式，省略时此参数默认值none。
* outline-width：定义轮廓线的宽度，省略时此参数默认值miedium，表示绘制中等宽度的轮廓线。
* outline-offset：定义轮廓边框的偏移位置的数值，此值可以取负数值。
* inherit：继承父元素的outline效果。

>outline与border的不同：  
outline制作的边框只能同时四边出现，不能单边出现，而且outline制作的模拟边框不会影响盒模型大小，而border制作的边框直接影响元素盒模型大小。

<a name="7-css3-伸缩布局盒模型"></a>
## 7. CSS3 伸缩布局盒模型

>如何辨别旧 Flexbox 和 Flexbox：

>* 看到 `display:box` 或者 `box-{*}` 属性，说明是2009年版本的Flexbox
* 看到 `display:flexbox` 或者 `flex()` 函数，说明时2011年版本，已称为Flexbox混合版本
* 看到 `display:flex` 或者 `flex-{*}` 属性，说明时当前规范，也就是W3C标准规范版本的Flexbox

<a name="旧版本flexbox模型的基本使用"></a>
#### [旧版本Flexbox模型的基本使用](#7-css3-伸缩布局盒模型)

##### 1.伸缩容器设置
`display: box | inline-box`

* box：设置为块伸缩容器。
* inline-box：设置为内联级伸缩容器。

##### 2.伸缩流方向
`box-orient: horizontal | vertical | inline-axis | block-axis`

* horizontal：伸缩项目在伸缩容器中从左到右在一条水平线上排列显示。
* vertical：伸缩项目在伸缩容器中从上到下在一条垂直线上排列显示。
* inline-axis：伸缩项目沿着内联轴排列显示。
* block-axis：伸缩项目沿着块轴排列显示。

##### 3.布局顺序

`box-direction: normal | reverse`

布局顺序是指伸缩项目再伸缩容器中的流动顺序，根据W3C规范可知，文档流方向是按照文档在HTML（DOM）中出现的先后顺序决定的。

##### 4.伸缩换行

`box-lines: single | multiple`

* single：伸缩容器的所有伸缩项目一行或一列显示。如果伸缩容器设置了overflow属性，可以直接控制伸缩项目是否隐藏、裁剪或者出现滚动条。
* multiple：指定伸缩容器多行或多列显示伸缩项目，当伸缩容器没有足够空间放置所有伸缩项目的时候，伸缩项目就会自动换行或多列显示。

如果没有给伸缩容器显示设置box-lines属性值时，一旦伸缩容器没有足够的空间容纳伸缩项目时，伸缩项目就会溢出伸缩容器。

##### 5.主轴对齐

指定如何在伸缩项目之间分布伸缩容器额外空间

`box-pack: start | end | center | justify`

* start：伸缩项目向一行的起始位置靠齐。伸缩容器沿着布局轴方向的所有额外空间都被置于布局轴的末尾。
* end：和start值相反，伸缩项目向一行的结束位置靠齐。伸缩容器沿着布局轴方向的所有额外空间都被置于布局轴的开始。
* center：伸缩项目向一行的中间位置靠齐。伸缩容器所有额外空间平均分布在第一伸缩项目前面和最后一个伸缩项目的后面。
* justify：伸缩项目会平均分布在一行里。伸缩容器所有额外空间平均分布在所有伸缩项目之间，而且在第一个伸缩项目之前和最后一个伸缩项目之后不分配伸缩容器的任何额外空间。

##### 6.侧轴对齐

`box-align: start | end | center | baseline | stretch`

* start：伸缩项目顶部边缘放置在伸缩容器的顶端，伸缩容器的额外空间放置在伸缩项目底端。
* end：和start值相反，所有伸缩项目底部边缘放置在伸缩容器的底端，伸缩容器的额外空间放置在伸缩项目顶端。
* center：伸缩项目紧靠在一起，垂直居中于伸缩容器。伸缩容器额外的空间平均分配在伸缩项目的顶部和底部。
* baseline：伸缩项目根据它们的基线对齐。伸缩容器额外空间可前可后显示。
* stretch：伸缩项目填充整个伸缩容器。

##### 7.伸缩性

`box-flex: <number>`

box-flex属性能够灵活地控制伸缩项目在伸缩容器中的显示空间。

##### 8.显示顺序

`box-ordinal-group: <integer>` 默认值为1，正整数

<a name="混合版本flexbox模型的基本使用"></a>
#### [混合版本Flexbox模型的基本使用](#7-css3-伸缩布局盒模型)

伸缩布局模型混合版本主要用于IE10浏览器，在使用混合版本时需要使用浏览器前缀“-ms-”

##### 1.伸缩容器设置

`display: flexbox | inline-flexbox`

##### 2.伸缩流方向

`-ms-flex-direction: row | row-reverse | colum | column-reverse` 类似于旧版`box-orient`

##### 3.伸缩换行

`flex-wrap: nowrap | wrap | wrap-reverse` 类似于旧版`box-lines`

##### 4.伸缩流方向与换行

`flex-flow: <flex-direction> | <flex-wrap>`

##### 5.主轴对齐

`flex-pack: start | end | center | justify | distribute`

* distribute：伸缩项目会平均分布在同一行里，两端保留中间相邻伸缩项目之间间距一半的空间。如果伸缩容器没有足够空间或者只有一个伸缩项目的时候就会遵循center方式。

##### 6.侧轴对齐

`flex-align: start | end | center | baseline |stretch` 类似于旧版`box-align`

* stretch：伸缩项目拉伸填充整个伸缩容器，如果伸缩容器没有足够的空间，将以start方式显示

##### 7.堆栈伸缩行

`flex-line-pack: start | end | center | justify | distribute | stretch` 类似于`flex-pack`

##### 8.伸缩性

`-ms-flex` 属性指定伸缩项目的宽度或高度是否基于伸缩容器中的可用空间具有弹性。该值还指示分配给子元素可用空间比例。  
当伸缩项目设置了 -ms-flex 属性时，则查询 -ms-flex 而不是width或height属性以确定伸缩项目的主要尺寸。如果元素不是伸缩项目，则 -ms-flex 属性不起作用。

`-ms-flex: <positive-flex> <negative-flex> <preferred-size> | none`

* \<positive-flex\>:设置正弹性的整数。如果忽略，该伸缩项目的正弹性为1。负值无效。
* \<negative-flex\>:设置负弹性的整数。如果忽略，该伸缩项目的正弹性为0。负值无效。
* \<perferred-size\>:设置伸缩项目的首选大小。可以为width或height属性的任何有效值，包括inherit。如果忽略，首选大小默认为0px。如果\<preferred-size\>组件在伸缩容器的伸缩项目上为auto，首选大小为该伸缩项目的width或height属性（平行于主轴的那个属性）。
* none:相当于正弹性\<positive-flex\>值为0，负弹性\<negative-flex\>值为0，首选大小\<preferred-size\>值为auto，也就是-ms-flex值为 “0 0 auto”

##### 9.显示顺序

`flex-order: <integer>`  
integer是一个自然数，默认值为0

<a name="新版本flexbox模型的基本使用"></a>
#### [新版本Flexbox模型的基本使用](#7-css3-伸缩布局盒模型)

##### 1.伸缩容器 _`flex`_

    display: flex | inline-flex

其中属性值`flex`等同于`box`和`flexbox`，将一个容器设置为伸缩容器，而属性值`inline-flex`等同于`inline-box`和`inline-flexbox`，将一个容器设置为内联伸缩容器。

>注意：CSS的`columns`在伸缩容器上没有效果；`float`、`clear`和`vertical-align`在伸缩项目上没有效果。

##### 2.伸缩流方向 _`flex-direction`_

    flex-direction: row | row-reverse | column | column-reverse

`flex-direction`适用于伸缩容器，也就是伸缩项目的父元素。主要用来创建主轴，从而定义了伸缩项目放置在伸缩容器的方向。

|属性|描述 |
|:--|:----|
|row|在ltr排版方式下从左向右排列；在rtl排版方式下从右向左排列（默认值）|
|row-reverse|与row排列方向相反，在ltr排版方式下从右向左排列；在rtl排版方式下从左向右排列|
|column|类似于row，不过是从上到下排列|
|column-reverse|类似于row-reverse，不过是从下到上排列|

##### 3.伸缩换行 _`flex-wrap`_

    flex-wrap: nowrap | wrap | wrap-reverse

`flex-wrap`适用于伸缩容器，也就是伸缩项目的父元素。主要用来定义伸缩容器里是单行还是多行显示，侧轴的方向决定了新行堆放的方向。

|属性|描述 |
|:--|:----|
|nowrap|伸缩容器单行显示，ltr排版下，伸缩项目从左到右排列；rtl排版上伸缩项目从右向左排列（默认值）|
|wrap|伸缩容器多行显示，ltr排版下，伸缩项目从左到右排列；rtl排版上伸缩项目从右向左排列|
|wrap-reverse|伸缩容器多行显示，ltr排版下，伸缩项目从右向左排列；rtl排版上伸缩项目从左向右排列（和wrap相反）|

##### 4.伸缩流方向与换行 _`flex-flow`_

    flex-flow: <'flex-direction'> || <'flex-wrap'>

`flex-flow`适用于伸缩容器，也就是伸缩项目的父元素。这是`flex-direction`和`flex-wrap`属性的__缩写版本__，同时定义了伸缩容器的主轴和侧轴。其默认值为`row` `nowrap`

>注意：`flex-flow`属性和`writing-mode`有直接的关系。当使用`writing-mode:vertical-rl`时转向垂直布局（如传统的中文、日文和韩文排版，也就是竖排），`flex-flow:row`将垂直排列伸缩项目，和column将水平排列伸缩项目。

##### 5.主轴对齐 _`justify-content`_

    justify-content: flex-start | flex-end | center | space-between | space-around

`justify-content`适用于伸缩容器，也就是伸缩项目的父元素。主要用来定义伸缩项目沿着主轴线的对齐方式。当一行的所有伸缩项目都不能伸缩或可伸缩但已经达到其最大长度时，这一属性才会对伸缩容器额外空间进行分配。当伸缩项目溢出某一行时，这一属性也会在项目的对齐上施加一些控制。

|属性|描述 |
|:--|:----|
|flex-start|伸缩项目向一行的起始位置靠齐。类似旧的规范版本中的start（默认值）|
|flex-end|伸缩项目向一行的结束位置靠齐。类似旧的规范版本中的end|
|center|伸缩项目向一行的中间位置靠齐。类似旧的规范版本中的center|
|space-between|伸缩项目会平均地分布在行里。第一个伸缩项目一行中的最开始位置，最后一个伸缩项目在一行中最终的位置。类似旧的规范版本中的justify|
|space-around|伸缩项目会平均地分布在行里，两端保留一半的空间。类似旧规范版本中的distribute|

##### 6.侧轴对齐 _`align-items`_  _`align-self`_

    align-items: flex-start | flex-end | center | baseline | stretch

`align-items` 和 `justify-content` 相呼应。`align-items` 调整伸缩项目在侧轴上的定位方式。主要用来定义伸缩项目可以在伸缩容器的当前行的侧轴上的对齐方式。可以把它想象成侧轴（垂直于主轴）的 `justify-content`

|属性|描述 |
|:--|:----|
|flex-start|伸缩项目在侧轴起点边的外边距紧靠住该行在侧轴起始边|
|flex-end|伸缩项目在侧轴起点边的外边距紧靠住该行在侧轴终点边|
|center|伸缩项目的外边距盒在该边的侧轴上居中放置|
|baseline|伸缩项目根据伸缩项目的基线对齐，基线根据伸缩项目的内容计算得到|
|stretch|默认值，伸缩项目拉伸填充整个伸缩容器。此值会使用伸缩项目的外边距盒的尺寸在遵照（min/max-width/height）属性的限制下尽可能接近所在行的尺寸|

伸缩项目的`align-self`属性主要是用来设置单独伸缩项目在侧轴对齐的方式，可以用来覆盖该伸缩项目的伸缩容器的`align-items`属性。它的值和`align-items`一样。  
对于匿名伸缩项目，`align-self`的值永远与其关联的伸缩容器的`align-items`的值相同。另外，如果伸缩项目的任一个侧轴上的外边距为`auto`，则`align-self`没有效果。如果`align-self`的值为`auto`，则其计算值为伸缩项目的伸缩容器的`align-items`值，如果该伸缩项目没有伸缩容器，则计算值为`stretch`。

##### 7.堆栈伸缩行 _`align-content`_

    align-content: flex-start | flex-end | center | space-between | space-around | stretch

`align-content`属性会更改`flex-wrapd`的行为。与`align-items`相似，主要用来调准__伸缩行__在伸缩容器里的对齐方式。

|属性|描述 |
|:--|:----|
|flex-start|各行向伸缩容器的起点位置堆叠|
|flex-end|各行向伸缩容器的结束位置堆叠|
|center|各行向伸缩容器的中间位置堆叠|
|space-between|各行向伸缩容器中平均分布|
|space-around|各行向伸缩容器中平均分布，在两边各有一半的空间|
|stretch|align-content的默认值，各行将会伸展以占用额外的空间|

>这个属性只有伸缩项目有多行时才生效，这种情况只有`display`的`flex-wrap`为`wrap`时，并且没有足够的空间把伸缩项目行放在同一行中。也就是这个属性将对每一行起作用而不是每个伸缩项目。

##### 8.伸缩性 _`flex`_

    flex:none | [ <'flex-grow'> <'flex-shrink'>? || <'flex-basis'> ]

`flex`属性可以用来指定可伸缩长度的部件：扩展比率、收缩比率，以及伸缩基准值。当一个元素是伸缩项目时，`flex`属性将代替主轴长度属性决定元素的主轴长度。若元素不是伸缩项目，则`flex`属性没有效果。

* `flex-grow: <number>` 默认值为：`0`，扩展比率
* `flex-shrink: <number>` 默认值为：`1`，此属性根据需要用来定义伸缩项目收缩的能力。`<number>`部件可以用来设置`flex-shrink`长度并指定收缩比率，也就是额外空间是负值的时候，此收缩项目对于伸缩容器里其他伸缩项目能收缩的空间比例。若省略此部件，它会被设置为1。在收缩的时候收缩比率会以伸缩基准值加权。`flex-shrink`负值同样生效
* `flex-basis: <length> | auto` 默认值为： `auto`，适用于伸缩项目，此属性用来设置伸缩项目的伸缩基准值，伸缩容器的额外空间按比率进行伸缩。若在`flex`缩写省略此部件，`flex-basis`的指定值是长度是`0`。若`flex-basis`的指定值是`auto`，则伸缩基准值的指定值是元素主轴长度属性的值。
* `flex: none` 相当于 `flex: 0 0 auto`
* `flex: auto` 相当于 `flex: 1 1 auto`

##### 9.显示顺序

    order: <number>

默认状态下，元素是按照文档流的结构顺序排列。在Flexbox模型中，可以通过`order`属性来改变伸缩项目出现在源文档的次序。

<a name="8-css3-多列布局"></a>
## 8. CSS3 多列布局

* columns：集成column-width和column-count两个属性，用于实现元素多列布局效果。
* column-width：定义每列列宽度。
* column-count：定义分列列数。
* column-gap：定义列间距。
* column-rule：定义列边框。
* column-span：定义多布布局中子元素跨列效果。
* column-fill：控制每列的列高效果。

<a name="多列布局基本属性"></a>
#### 多列布局基本属性

`column: <column-width> || <column-count>`

<a name="多列布局列宽属性"></a>
#### 多列布局列宽属性

`column-width: auto | <length>`

<a name="多列布局列数属性"></a>
#### 多列布局列数属性

`column-count: auto | <integer>`

* auto：默认值，表示元素只有一列。其主要依靠浏览器计算自动设置。
* \<integer\>：正整数值，主要用来定义元素的列数，取值为大于0的整数，负值无效。

列数=（容器宽度 - 间距）/ 列间距

<a name="多列布局列间距属性"></a>
#### 多列布局列间距属性

`column-gap: normal | <length>`

* normal: 默认值，主要通过浏览器默认设置时行解析，一般情况下，normal值相当于1em。
* \<length\>：由浮点数字和单位标识符组成的长度值，主要用来设置列与列之间的间距，常用px、em单位的任何整数值，但其不能为负值。

<a name="多列布局列边框样式属性"></a>
#### 多列布局列边框样式属性

`column-rule: <column-rule=width> | <column-rule-style> | <column-rule-color>`

* column-rule-width：类似于border-width属性，主要用来定义列边框的宽度，其默认值medium，该属性接受任意浮点数，但不接受负值。像border-width属性一样，可以使用关键词medium、thick和thin。
* column-rule-style：此值类似于border-style属性，主要用来定义列边框样式，其默认值为none。该属性值与border-style属值相同，包括none、hidden、dotted、dashed、solid、double、groove、ridge、inset、outset。
* column-rule-color：此值类似于border-color属性，主要用来定义列边框样色，其默认值为前景色color的值，使用时相当于border-color。该属性接受所有的颜色。如果不希望显示颜色，也可以将其设置为transparent（透明色）。

<a name="多列布局跨列属性"></a>
#### 多列布局跨列属性

`column-span: none | all`

* none：默认值，表示不跨越任何列。
* all：跟none值刚好相反，表示的是元素跨越所有列，并定位在列的Z轴之上。

<a name="多列布局列高度属性"></a>
#### 多列布局列高度属性

`column-fill: auto | balance`

* auto： 默认值，各列的高度随其内容的变化自动变化。
* balance： 各列的高度将会根据内容最多的一列的高度进行统一。

<a name="9-css3-渐变"></a>
## 9. CSS3 渐变

<a name="线性渐变"></a>
#### 线性渐变

Webkit引擎老式语法  
`-webkit-gradient(<type>,<point>[,<radius>]?,<point>[,<radius>]?[,<stop>]*)`

Webkit引擎新式语法  
`-webkit-linear-gradient([<point> || <angle>,]?<stop>,<stop>[,<stop>*]`

Geocko引擎  
`-moz-linear-gradient([<point>||<angle>,]?<stop>,<stop>[,<stop>]*)`

Presto引擎  
`-o-linear-gradient([<point>||<angle>,]?<stop>,<stop>[,<stop>]*)`

Trident引擎  
`-ms-linear-gradient([<point>||<angle>,]?<stop>,<stop>[,<stop>]*)`

W3C标准线性渐变语法  
`linear-gradient([[<angle> | to <side-or-corner> ],]?<color-stop>[,<color-stop>]+)`

<a name=""></a>
<a name="径向渐变"></a>
#### 径向渐变

Webkit引擎老式语法  
`-webkit-gradient([<type>],[<position> || <angle>,]?[<shape> || <size>,]?<color-stop>,<color-stop>[,<color-stop>]*)`

Webkit引擎新式语法  
`-webkit-linear-gradient([<position> || <angle>,]?[<shape> || <size>,]?<color-stop>,<color-stop>[,<color-stop>]*)`

Geocko引擎  
`-moz-radial-gradient([<position> || <angle>,]?[<shape> || <size>,]?<color-stop>,<color-stop>[,<color-stop>]*)`

Presto引擎  
`-o-radial-gradient([<position> || <angle>,]?[<shape> || <size>,]?<color-stop>,<color-stop>[,<color-stop>]*)`

Trident引擎  
`-ms-radial-gradient([<position> || <angle>,]?[<shape> || <size>,]?<color-stop>,<color-stop>[,<color-stop>]*)`

W3C标准线性渐变语法  
`radial-gradient([[<shape> || <size>] [at <position>]?, | at <position>,]?<color-stop>[,<color-stop>]+)`

<a name="重复渐变"></a>
#### 重复渐变

<a name="10-css3-变形"></a>
## 10. CSS3 变形

CSS3 变形中具有X/Y可用的函数：translateX()、translateY()、scaleX()、scaleY()、skewX()、skewY()  
CSS3 2D 变形函数包括：translate()、scale()、rotate()、skew()、matrix()  
CSS3 3D 变形函数包括：rotateX()、rotateY()、rotate3d()、translateZ()、translate3d()、scaleZ()、scale3d()、matrix3d()

<a name="变形属性详解"></a>
#### 变形属性详解

`transform: none | <transform-function> [<transform-function>]*`

`transform-origin: [<percentage> | <length> | left | center | right | top | bottom] | [<percentage> | <length> | left | center | right] | [[<percentage> | <length> |  left | center | right] && [<percentage> | <length> | top | center | bottom]] <length> ?`

`transform-style: flat | preserve-3d`
>注意：如果元素设置了transform-style值为preserve-3d，就不能为了防止子元素溢出容器而设置overflow值为hidden，如果设置了overflow:hidden同样可以迫使子元素出现再同一平面（和元素设置了transform-style为flat一样的效果）

`perspective: none | <length>`

`perspective-origin: [<percentage> | <length> | left | center | right | top | bottom] | [[<percentage> | <length> |  left | center | right] && [<percentage> | <length> | top | center | bottom]]`

`backface-visibility: visible | hidden`

<a name="2d变形"></a>
#### 2D变形

`translate(tx,ty)`

`scale(sx,sy)`

<a name="多重变形"></a>
#### 多重变形

`transform: <transform-function> <transform-function>*`

<a name="11-css3-过渡"></a>
## 11. CSS3 过渡

<a name="过渡属性"></a>
#### 过渡属性

`transition: [<'transition-property'> || <'transition-duration'> || <'transition-timing-function'> || <'transition-delay'>] [,[<'transition-propertry'> || <'transtion-duration'> || <'transition-timing-function'> || <'transition-delay'>]]*`

<a name="12-css3-动画"></a>
## 12. CSS3 动画

<a name="13-媒体特性与responsive设计"></a>
## 13. 媒体特性与Responsive设计











