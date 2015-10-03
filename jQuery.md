# jQuery 学习笔记
>总结自[慕课网 - jQuery基础课程](http://www.imooc.com/learn/11)，在此感谢

## 索引
<!-- MarkdownTOC -->

- [引入jQuery文件库](#引入jquery文件库)
- [选择器](#选择器)
- [过滤选择器](#过滤选择器)
- [属性选择器](#属性选择器)
- [表单选择器](#表单选择器)
- [操作DOM元素](#操作dom元素)
- [jQuery事件与应用](#jquery事件与应用)
- [jQuery动画特效](#jquery动画特效)

<!-- /MarkdownTOC -->

***

<a name="引入jquery文件库"></a>
## 引入jQuery文件库
```js
<script src="http://libs.baidu.com/jquery/1.9.0/jquery.js" type="text/javascript"></script>
```

***

##### JavaScript代码
```js
var page_ps=document.getElementsByTagName("p");
for(var i = 0; i < page_ps.length; i++) {
  page_ps[i].innerHTML = "Hello imooc!";
}
```
##### jQuery代码
```js
$("p").html("Hello imooc!");
```

***

<a name="选择器"></a>
## 选择器

- __[#id选择器](#选择器)__ `$("#my_id")`

```js
<div id="divtest">div的内容</div>
<div id="default"></div>
<script type="text/javascript">
  $("#default").html($("#divtest").html());
</script>
```

- __[element选择器](#选择器)__ `$("element")`

```js
<button id="btntest">点我</button>
<script type="text/javascript">
  $("button").attr("disabled","true");
</script>
```

- __[.class选择器](#选择器)__ `$(".class")`

- __[*选择器](#选择器)__ `$("*")`

```js
<form action="#">
  <input id="Button1" type="button" value="button" />
  <input id="Text1" type="text" />
  <input id="Radio1" type="radio" />
  <input id="Checkbox1" type="checkbox" />
</form>
<script type="text/javascript">
  $("form *").attr("disabled", "true");
</script>
```
>实践证明，由于使用*选择器获取的是全部元素，因此，有些浏览器将会比较缓慢，这个选择器也需要谨慎使用。

- __[sele1,sele2,seleN选择器](#选择器)__ `$("sele1,sele2,seleN")`

```js
$(".red,.green").html("Hello");
$("div,p").html("World");
```

- __[ance desc选择器](http://www.imooc.com/code/86)__ `$("ance desc")` ?!

>其中ance desc是使用空格隔开的两个参数。ance参数（ancestor祖先的简写）表示父元素；desc参数（descendant后代的简写）表示后代元素，即包括子元素、孙元素等等。

```js
<div>
  <p>
    <label></label>
  </p>
  <label></label>
</div>
<script type="text/javascript">
  $("div label").css("background-color","blue");
</script>
```

- __[parent > child选择器](http://www.imooc.com/code/95)__ `$("parent > child")` ?!

>获取子辈元素，不包括孙辈元素

- __[prev + next选择器](#选择器)__ `$("prev + next")`

>“prev”元素最紧邻的下一个元素由“next”选择器返回的并且只返回唯的一个元素。

- __[prev ～ siblings选择器](#选择器)__ `$("prev ～ siblings")`

>获取prev元素后面全部相邻的元素,不包含不属于同辈的元素

***

<a name="过滤选择器"></a>
## 过滤选择器

- __[:first 过滤选择器](#过滤选择器)__  `例如：$("li:first")`

>__*:first*__ 过滤选择器的功能是获取第一个元素，常常与其它选择器一起使用，获取指定的一组元素中的第一个元素。

- __[:eq(index) 过滤选择器](#过滤选择器)__  `例如：$("li:eq(3)")`

>其中参数 __*index*__ 表示索引号（即：一个整数），它从0开始，如果index的值为3，表示选择的是第4个元素。

- __[:contains(text) 过滤选择器](#过滤选择器)__  `例如：$("li:contains('jQuery')")`

>选择包含指定字符串的全部元素，它通常与其他元素结合使用，获取包含 __*text*__ 字符串内容的全部元素对象。其中参数 __*text*__ 表示页面中的文字。  
>__注意：____*text*__ 中的文字要用`''`引号括起来。

- __[:has(selector) 过滤选择器](#过滤选择器)__  `例如：$("li:has('p')")`

>__*:has(selector)*__ 过滤选择器的功能是获取选择器中包含指定元素名称的全部元素，其中 __*selector*__ 参数就是包含的元素名称，是被包含元素。  
>__注意：____*selector*__ 中的元素要用`''`引号括起来。

- __[:hidden 过滤选择器](http://www.imooc.com/code/119)__  `例如：$("p:hidden")` ?!

>获取全部不可见的元素，这些不可见的元素中包括type属性值为hidden的元素。

- __[:visible 过滤选择器](http://www.imooc.com/code/122)__  `例如：$("p:visible")` ?!

>与 __*:hidden*__ 过滤选择器相反， __*:visible*__ 过滤选择器获取的是全部可见的元素，也就是说，只要不将元素的 *display* 属性值设置为 *“none”*，那么，都可以通过该选择器获取。

- __[:first-child 子元素过滤选择器](#过滤选择器)__  `例如：$("li:first-child")`

>使用 __*:first-child*__ 子元素过滤选择器则可以获取每个父元素中返回的首个子元素，它是一个集合，常用多个集合数据的选择处理。

- __[:last-child 子元素过滤选择器](#过滤选择器)__  `例如：$("li:last-child")`

***

<a name="属性选择器"></a>
## 属性选择器

- __[[attribute = value] 属性选择器](#属性选择器)__  `例如：$("li[title='蔬菜']")`

>获取属性值中包含指定内容的全部元素，其中[]是专用于属性选择器的括号符，参数attribute表示属性名称，value参数表示对应的属性值。  
>属性值中的‘’单引号可以不写，由于属性名与属性值是等号，因此，它们之间不是包含关系，而是完全相同。

- __[[attribute != value] 属性选择器](#属性选择器)__  `例如：$("li[title!='蔬菜']")`

```js
$("li[title!='蔬菜']").css("background-color", "green");
```

- __[[attribute *= value] 属性选择器](#属性选择器)__  `例如：$("li[title*='菜']")`

***

<a name="表单选择器"></a>
## 表单选择器

- __[:input 表单选择器](#表单选择器)__  `例如：$("#frmTest :input")`

>返回__全部的表单元素__，不仅包括所有`<input>`标记的表单元素，而且还包括`<textarea>`、`<select>` 和 `<button>`标记的表单元素，因此，它选择的表单元素是最广的。

- __[:text 表单文本选择器](#表单选择器)__  `例如：$("#frmTest :text")`

>__*:text*__ 表单文本选择器可以获取表单中全部单行的文本输入框元素，单行的文本输入框就像一个不换行的字条工具，使用非常广泛。

- __[:password 表单密码选择器](#表单选择器)__  `例如：$("#frmTest :password")`

>获取表单中全部的密码输入文本框元素。

- __[:radio 单选按钮选择器](#表单选择器)__  `例如：$("#frmTest :radio")`

>获取表单中的__全部单选按钮__元素。

- __[:checkbox 复选框选择器](#表单选择器)__  `例如：$("#frmTest :checkbox")`

```js
$("#frmTest :checkbox").attr("disabled","true"); 将属性设置为不可用
```

- __[:submit 提交按钮选择器](http://www.imooc.com/code/171)__  `例如：$("#frmTest input:submit")` ?!

```js
<form id="frmTest" action="#">
  <input type="button" value="Input Button" /><br />
  <input type="submit" value="点我就提交了" /><br />
  <button>  Button  </button>
</form>
<script type="text/javascript">
  $("#frmTest input:submit").addClass("bg_red");
</script>
```
>通常情况下，一个表单中只允许有一个“type”属性值为“submit”的提交按钮，使用 __*:submit*__ 选择器可获取表单中的这个提交按钮元素。  
>__注意：__在上例中，`$("#frmTest input:submit")`的`:submit`前面有`input`,因为`<button>`按钮通常也被认为是提交按钮。

- __[:image 图像域选择器](#表单选择器)__  `例如：$("#frmTest :image")`

>当一个`<input>`元素的“type”属性值设为“image”时，该元素就是一个图像域，使用 __*:image*__ 选择器可以快速获取该类全部元素。  
>使用 __*:image*__ 选择器只能获取`<input>`图像域，而不能获取`<img>`格式的图像元素。

- __[:button 表单按钮选择器](#表单选择器)__  `例如：$("#frmTest :button")`

>表单中包含许多类型的按钮，而使用 __*:button*__ 选择器能获取且只能获取“_type_”属性值为“button”的`<input>`和`<button>`这两类普通按钮元素。

- __[:checked 选中状态选择器](#表单选择器)__  `例如：$("#frmTest :checked")`

>有一些元素存在选中状态，如复选框、单选按钮元素，选中时“checked”属性值为“checked”，调用 __*:checked*__ 可以获取处于选中状态的全部元素。

- __[:selected 选中状态选择器](#表单选择器)__  `例如：$("#frmTest :selected")`

>与 __*:checked*__ 选择器相比，__*:selected*__ 选择器只能获取`<select>`下拉列表框中全部处于选中状态的`<option>`选项元素。

***

<a name="操作dom元素"></a>
## 操作DOM元素

- __[使用attr()方法控制元素的属性](#操作dom元素)__  `attr("属性名") attr("属性名"，"属性值")`

```js
$("#test").attr("checked",false); 取消id为test的复选框选中状态
```
>__*attr()*__ 方法的作用是设置或者返回元素的属性，其中 *attr(”属性名“)* 格式是 __获取__ 元素属性名的值，*attr(”属性名“，”属性值“)* 格式则是 __设置__ 元素属性名的值。

- __[操作元素的内容](http://www.imooc.com/code/186)__  `html() text()` ?!

>使用 __*html()*__ 和 __*text()*__ 方法操作元素的内容，当两个方法的参数为空时，表示获取该元素的内容，而如果方法中包含参数，则表示将参数值设置为元素内容。  
> __注意：__ __*html()*__ 方法可以获取元素的HTML内容，因此，原文中的格式代码也被一起获取，而 __*text()*__ 方法只是获取元素中的文本内容，并不包含HTML格式代码。

- __[操作元素的样式](#操作dom元素)__  `addclass() css()`

```js
$("#content").addClass("blue white");
$("#content").css({"background-color":"red","color":"white"});
```
>前者括号中的参数为增加元素的样式名称,增加多个样式名称时，要用__空格__隔开。  
>后者直接将样式的属性内容写在括号中，同时设置多属性如上例所示。

- __[移除属性和样式](#操作dom元素)__  `removeAttr(name) removeClass(class)`

>分别可以实现移除元素的属性和样式的功能，前者方法中参数表示移除的__属性名__，后者方法中参数则表示移除的__样式名__

- __[使用 append() 方法向元素内追加内容](#操作dom元素)__  `$(selector).append(content)`

```js
var $html = "<div id='test' title='hi'>动态创建</div>";
function rethtml() {
  var $html = "<div id='test' title='hi'>调用函数创建</div>";
  return $html;
}
$("body").append($html);
$("body").append(rethtml());
```
>__*append(content)*__ 方法的功能是向指定的元素中追加内容，被追加的 _content_ 参数，可以是字符、HTML元素标记，还可以是一个返回字符串内容的函数。

- __[使用 appendTo() 方法向 _被选元素内_ 插入内容](#操作dom元素)__  `$(content).appendTo(selector)`

>参数 _content_ 表示需要插入的内容，参数 _selector_ 表示被选的元素，即把 _content_ 内容插入 _selector_ 元素__内__，默认是在尾部。

- __[使用 before() 和 after() 在 _元素前后_ 插入内容](#操作dom元素)__  `$(selector).before(content) $(selector).after(content)`

>将 _content_ 内容插入到原有 _selector_ 元素内容前后，而并不仅是它的内部。

- __[使用 clone() 方法复制元素](#操作dom元素)__ `$(selector).clone()`

>调用 __*clone()*__ 方法可以生成一个被选元素的副本，即复制了一个被选元素，包含它的__节点__、__文本__和__属性__.

- __[替换内容](#操作dom元素)__ `$(selector).replaceWith(content) $(content).replaceAll(selector)`

- __[使用 wrap() 和 wrapInner() 方法包裹元素和内容](#操作dom元素)__ `$(selector).wrap(wrapper) $(content).wrapInner(wrapper)`

>前者用于包裹元素本身，后者则用于包裹元素 __*内*__ 的内容。  
>参数 _selector_ 为被包裹的元素， _wrapper_ 参数为包裹元素的格式。

- __[使用 each() 方法遍历元素](#操作dom元素)__ `$(selector).each(function(index))`

```js
$("span").each(function (index) {
  if (index == 1) {
    $(this).attr("class", "red");
  }
});
```
>参数 _function_ 为遍历时的回调函数， _index_ 为遍历元素的序列号，它从0开始。

- __[使用 remove() 和 empty() 方法删除元素](http://www.imooc.com/code/197)__ `remove() empty()` ?!

>__*remove()*__ 方法删除所选元素本身和子元素，该方法可以通过添加过滤参数指定需要删除的某些元素，而 __*empty()*__ 方法则只删除所选元素的子元素。

***

<a name="jquery事件与应用"></a>
## jQuery事件与应用

- __[页面加载时出发 ready() 事件](#jquery事件与应用)__ `$(document).ready(function(){}) 等价于 $(function(){})`

```js
$("#tip").ready(function () {
  $("#btntest").bind("click", function () {
    $("#tip").html("我被点击了！");
  });
});
```
>__*ready()*__ 事件类似于onLoad()事件，但前者只要页面的DOM结构加载后便触发，而后者必须在页面全部元素加载成功才触发， __*ready()*__ 可以写多个，按顺序执行。

- __[使用 bind() 方法绑定元素的事件](#jquery事件与应用)__ `$(selector).bind(event,[data] function)`

```js
$(function () {
  $("#btntest").bind("mouseout click", function () {
    $(this).attr("disabled", "true");
  })
});
```
>绑定前，需要知道被绑定的元素名，绑定的事件名称，事件中执行的函数内容。  
>参数event为事件名称，多个事件名称用空格隔开，function为事件执行的函数。

- __[使用 hover() 方法切换事件](#jquery事件与应用)__ `$(selector).hover(over，out)`

```js
$(function () {
  $("div").hover(
  function () {
    $(this).addClass("orange");
  },
  function () {
    $(this).removeClass("orange")；
  })
});
```
>__*hover()*__ 方法的功能是当鼠标移到所选元素上时，执行方法中的第一个函数，鼠标移出时，执行方法中的第二个函数，实现事件的切实效果。_over_ 参数为移到所选元素上触发的函数，_out_ 参数为移出元素时触发的函数。

- __[使用 toggle() 方法绑定多个函数](#jquery事件与应用)__ `$(selector).toggle(fun1(),fun2(),funN(),...)`

>__注意：__ toggle()方法支持目前主流稳定的jQuery版本1.8.2，在1.9.0之后的版本是不支持的。

- __[使用 unbind() 方法移除元素绑定的事件](#jquery事件与应用)__ `$(selector).unbind(event,fun)`

```js
$("#btntest").bind("click", function () {
  $("div").unbind("click dblclick");
  $(this).attr("disabled", "true");
});
```
>其中参数 _event_ 表示需要移除的事件名称，多个事件名用空格隔开，_fun_ 参数为事件执行时调用的函数名称。

- __[使用 one() 方法绑定元素的一次性事件](#jquery事件与应用)__ `$(selector).one(event,[data],fun)`

>这种方法绑定的事件只会触发一次。  
>参数 _event_ 为事件名称，_data_ 为触发事件时携带的数据，_fun_ 为触发该事件时执行的函数。

- __[调用 trigger() 方法手动触发指定事件](http://www.imooc.com/code/272)__ `$(selector).trigger(event)` ?!

- __[文本框的 focus 和 blur 事件](#jquery事件与应用)__

>_focus_ 事件在元素获取焦点时触发，如点击文本框时，触发该事件。  
>_blur_ 事件在元素丢失焦点时触发，如点击除文本框的任何元素，都会触发该事件。

- __[下拉列表框的 change 事件](#jquery事件与应用)__

>当一个元素的值发生变化时，将会触发 _change_ 事件，例如在选择下拉列表框中的选项时，就会触 _change_ 事件。

- __[调用 live() 方法绑定元素的事件](#jquery事件与应用)__ `$(selector).live(event,[data],fun)`

>与 __*bind()*__ 方法相同， __*live()*__ 方法与可以绑定元素的可执行事件，除此相同功能之外， __*live()*__ 方法还可以绑定动态元素，即使用代码添加的元素事件。  
>参数 _event_ 为事件名称，_data_ 为触发事件时携带的数据，_fun_ 为触发该事件时执行的函数。  
>__注意：__从 jQuery 1.7 开始，不再建议使用 .live() 方法。1.9不支持.live()，本节代码编辑器里的js引用版本改为了1.8。

***

<a name="jquery动画特效"></a>
## jQuery动画特效

- __[调用 show() 和 hide() 方法显示和隐藏元素](#jquery动画特效)__  
`$(selector).show(speed,[callback])`  
`$(selector).hide(speed,[callback])`



