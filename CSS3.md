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
  |E[attr~=val]|选择匹配E元素，且E元素定义了属性attr，attr属性值具有多个空格分隔的值，其中一个值等于val。例如，.info[title~=more]将匹配元素具有类名info，而且这个元素设置了一个属性title，同时title属性值以包含了“more”的任何元素，例如<a class="info" title="click here for more information">click me</a>|
  |E[attr*=val]|选择匹配元素E，且E元素定义了属性attr，其属性值任意位置包含了“val”。换句话说，字符串val与属性值中的任意位置相匹配|
  |E[attr^=val]|选择匹配元素E，且E元素定义了属性attr，其属性值以val开头的任何字符串|
  |E[attr$=val]|选择匹配元素E，且E元素定义了属性attr，其属性值以val结尾的任何字符串。与E[attr^=val]相反|

  E[attr|=val] 选择匹配E元素，且E元素定义了属性attr，attr属性值是一个具有val或者以val-开始的属性值。常用于lang属性（例如lang=“en-us”）。例如p[lang|=en]将匹配定义为英语的任何段落，无论时英式英语还是美式英语

  >注意：E[attr=val]选择器中，属性和属性值必须完全匹配，特别对于属性值是词列表的形式，例如，`<a href="#" class="links item"></a>`，其中a[class="links"]{...}是找不到匹配元素，只有a[class="link item"]{...}才匹配。

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
  >`border: border-width border-style border-color;` 其中border-style必须有

  * border-width: 设置元素边框的粗细，默认值“medium”（大约等于3~4px）
  * border-color: 设置元素边框的颜色
  >border-color: [ <color\> | trabsparent ]{1,4} | inherit  下列属性中color是复数colors
    + border-top-colors:[ <color\> | trabsparent ]{1,4} | inherit;
    + border-right-colors:[ <color\> | trabsparent ]{1,4} | inherit;
    + border-bottom-colors:[ <color\> | trabsparent ]{1,4} | inherit;
    + border-left-colors:[ <color\> | trabsparent ]{1,4} | inherit;


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
>`border-image: none | <image> [<number> | <percentage>] {1,4} [/ <broder-width> {1,4}] ?[stretch | repeat | round] {0,2}`

> * none: 默认值，表示边框无背景图片
  * <image>: 设置背景图片，这跟background-image一样，可以使用绝对或相对的URL地址，来指定边框的背景图片
  * <number>: number时一个数值，用来设置边框或者边框背景图片的大小，其单位时像素（px），可以使用1~4个值，表示4个方位的值，可以参考border-width设置方式
  * <percentage>: percentage也是用来设置边框或者边框背景图片的大小，跟number不同之处是，percentage使用的是百分比
  * stretch、repeat、round: 这三个属性参数是用来设置边框背景图片的铺放方式，类似于background-position，其中stretch会拉伸边框背景图片、repeat是会重复边框背景图片、round是平铺边框背景图片，其中stretch为默认值

>  border-image 和 background-image 之间有一些类似之处，包括图片的引用和排列方式等

<a name="圆角边框属性"></a>
#### 圆角边框属性

>`border-radius: none | <length> {1,4}[/<length>{1,4}] ？`

特殊应用：

* 当border-radius半径小于或等于border的厚度时，元素边框内部就不具有圆角效果。如圆角半径比边框值大时，内圆角就会出来。
* 元素相邻边有不同的宽度，这个角将会从宽的边平滑过渡到窄的一边，其中一条边甚至可以是0，元素相邻转角是由大向小转。

注意：表格元素table用border-radius时不一样的，当表格样式属性border-collapse是collapse时，表格不能正常显示，只有border-collapse属性值为separate时，表格圆角才能正常显示。

<a name="盒子阴影属性"></a>
#### 盒子阴影属性

>`box-shadow:none | [ <length> <length> <length>?<length>? || <color> ], [ <length> <length> <length>? <length>? || <color> ]+`  
简写：  
`box-shadow:none | [inset x-offset y-offset blur-radius spread-radius color], [inset x-offset y-offset blur-radius spread-radius color]`

>* none：默认值，元素没有任何阴影效果。
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
`background-position: <percentage> || <length> || [left|center|right], [top|center|bottom]` 默认值为“(0,0)||(0%, 0%)||(left top)”

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





