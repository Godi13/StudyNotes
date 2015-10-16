#索引

<!-- MarkdownTOC -->

- [图解CSS3读书笔记](#图解css3读书笔记)
  - [1.CSS3选择器](#1css3选择器)
    - [CSS中常见的通配符](#css中常见的通配符)
  - [2.CSS3 边框](#2css3-边框)
    - [边框基本属性](#边框基本属性)
    - [图片边框属性](#图片边框属性)

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
  >border: border-width border-style border-color; 其中border-style必须有

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
>border-image: none | <image\> [<number\> | <percentage\>] {1,4} [/ <broder-width\> {1,4}] ?[stretch | repeat | round] {0,2}

> * none: 默认值，表示边框无背景图片
  * <image\>: 设置背景图片，这跟background-image一样，可以使用绝对或相对的URL地址，来指定边框的背景图片
  * <number\>: number时一个数值，用来设置边框或者边框背景图片的大小，其单位时像素（px），可以使用1~4个值，表示4个方位的值，可以参考border-width设置方式
  * <percentage\>: percentage也是用来设置边框或者边框背景图片的大小，跟number不同之处是，percentage使用的是百分比
  * stretch、repeat、round: 这三个属性参数是用来设置边框背景图片的铺放方式，类似于background-position，其中stretch会拉伸边框背景图片、repeat是会重复边框背景图片、round是平铺边框背景图片，其中stretch为默认值

>  border-image 和 background-image 之间有一些类似之处，包括图片的引用和排列方式等






