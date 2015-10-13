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
- [jQuery 事件与应用](#jquery-事件与应用)
- [jQuery 动画特效](#jquery-动画特效)
- [jQuery 实现Ajax应用](#jquery-实现ajax应用)
- [jQuery 常用插件](#jquery-常用插件)
- [jQuery UI型插件](#jquery-ui型插件)
- [jQuery 工具类函数](#jquery-工具类函数)

<!-- /MarkdownTOC -->

***

<a name="引入jquery文件库"></a>
## 引入jQuery文件库
> [jQuary CDN服务](http://www.bootcdn.cn/jquery/)

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

- __[使用 append() 方法向 __*元素内*__ 追加内容](#操作dom元素)__  `$(selector).append(content)`

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

<a name="jquery-事件与应用"></a>
## jQuery 事件与应用

- __[页面加载时出发 ready() 事件](#jquery-事件与应用)__ `$(document).ready(function(){}) 等价于 $(function(){})`

```js
$("#tip").ready(function () {
  $("#btntest").bind("click", function () {
    $("#tip").html("我被点击了！");
  });
});
```
>__*ready()*__ 事件类似于onLoad()事件，但前者只要页面的DOM结构加载后便触发，而后者必须在页面全部元素加载成功才触发， __*ready()*__ 可以写多个，按顺序执行。

- __[使用 bind() 方法绑定元素的事件](#jquery-事件与应用)__ `$(selector).bind(event,[data] function)`

```js
$(function () {
  $("#btntest").bind("mouseout click", function () {
    $(this).attr("disabled", "true");
  })
});
```
>绑定前，需要知道被绑定的元素名，绑定的事件名称，事件中执行的函数内容。  
>参数event为事件名称，多个事件名称用空格隔开，function为事件执行的函数。

- __[使用 hover() 方法切换事件](#jquery-事件与应用)__ `$(selector).hover(over，out)`

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

- __[使用 toggle() 方法绑定多个函数](#jquery-事件与应用)__ `$(selector).toggle(fun1(),fun2(),funN(),...)`

>__注意：__ toggle()方法支持目前主流稳定的jQuery版本1.8.2，在1.9.0之后的版本是不支持的。

- __[使用 unbind() 方法移除元素绑定的事件](#jquery-事件与应用)__ `$(selector).unbind(event,fun)`

```js
$("#btntest").bind("click", function () {
  $("div").unbind("click dblclick");
  $(this).attr("disabled", "true");
});
```
>其中参数 _event_ 表示需要移除的事件名称，多个事件名用空格隔开，_fun_ 参数为事件执行时调用的函数名称。

- __[使用 one() 方法绑定元素的一次性事件](#jquery-事件与应用)__ `$(selector).one(event,[data],fun)`

>这种方法绑定的事件只会触发一次。  
>参数 _event_ 为事件名称，_data_ 为触发事件时携带的数据，_fun_ 为触发该事件时执行的函数。

- __[调用 trigger() 方法手动触发指定事件](http://www.imooc.com/code/272)__ `$(selector).trigger(event)` ?!

- __[文本框的 focus 和 blur 事件](#jquery-事件与应用)__

>_focus_ 事件在元素获取焦点时触发，如点击文本框时，触发该事件。  
>_blur_ 事件在元素丢失焦点时触发，如点击除文本框的任何元素，都会触发该事件。

- __[下拉列表框的 change 事件](#jquery-事件与应用)__

>当一个元素的值发生变化时，将会触发 _change_ 事件，例如在选择下拉列表框中的选项时，就会触 _change_ 事件。

- __[调用 live() 方法绑定元素的事件](#jquery-事件与应用)__ `$(selector).live(event,[data],fun)`

>与 __*bind()*__ 方法相同， __*live()*__ 方法与可以绑定元素的可执行事件，除此相同功能之外， __*live()*__ 方法还可以绑定动态元素，即使用代码添加的元素事件。  
>参数 _event_ 为事件名称，_data_ 为触发事件时携带的数据，_fun_ 为触发该事件时执行的函数。  
>__注意：__从 jQuery 1.7 开始，不再建议使用 .live() 方法。1.9不支持.live()，本节代码编辑器里的js引用版本改为了1.8。

***

<a name="jquery-动画特效"></a>
## jQuery 动画特效

- __[调用 show() 和 hide() 方法显示和隐藏元素](#jquery-动画特效)__  
`$(selector).show(speed,[callback])`  
`$(selector).hide(speed,[callback])`

>参数 _speed_ 设置隐藏或显示时的速度值，可为 “ _slow_ ” 、“ _fast_ ” 或毫秒数值,“ _slow_ ” 、“ _fast_ ” 需要用 __" "__ 括起来，毫秒数值不需要括起来，可选项参数 _callback_ 为隐藏或显示动作执行完成后调用的函数名。

- __[调用 toggle() 方法实现动画切换效果](#jquery-动画特效)__ `$(selector).toggle(speed,[callback])`

```js
$(function () {
var $spn = $("#spnTip");
  $("h4").bind("click", function () {
    $("ul").toggle(1000, function () {
      $spn.html() == "隐藏" ? $spn.html("显示") : $spn.html("隐藏");
    })
  });
});
```
>调用 __*toggle()*__ 方法就可以很容易做到，即如果元素处于显示状态，调用该方法则隐藏该元素，反之，则显示该元素。

- __[使用 slideUp() 和 slideDown() 方法的滑动效果](#jquery-动画特效)__  
`$(selector).slideUp(speed,[callback])`  
`$(selector).slideDown(speed,[callback])`

>__注意：__ __*slideDown()*__ 仅适用于 __被隐藏__ 的元素； __*slideup()*__ 则相反。

- __[使用 slideToggle() 方法实现滑动效果](#jquery-动画特效)__ `$(selector).slideToggle(speed,[callback])`

>使用 __*slideToggle()*__ 方法可以切换 slideUp() 和 slideDown() ，即调用该方法时，如果元素已向上滑动，则元素自动向下滑动，反之，则元素自动向上滑动。

- __[使用 fadeIn() 与 fadeOut() 方法实现淡入淡出效果](#jquery-动画特效)__  
`$(selector).fadeIn(speed,[callback])`  
`$(selector).fadeOut(speed,[callback])`

>__*fadeIn()*__ 和 __*fadeOut()*__ 方法可以实现元素的淡入淡出效果，前者淡入隐藏的元素，后者可以淡出可见的元素。

- __[使用 fadeTo() 方法设置淡入淡出效果的不透明度](#jquery-动画特效)__ `$(selector).fadeTo(speed,opacity,[callback])`

```js
$(function () {
    $("span").each(function (index) {
        switch (index) {
            case 0:
                $(this).fadeTo(1000,0.2);
                break;
            case 1:
                $(this).fadeTo(1000,0.4);
                break;
            case 2:
                $(this).fadeTo(1000,0.6);
                break;
        }
    });
});
```
>其中 _speed_ 参数为效果的速度，_opacity_ 参数为指定的不透明值，它的取值范围是0.0~1.0，可选项参数 _callback_ 为效果完成后，回调的函数名。

- __[调用 animate() 方法制作简单的动画效果](#jquery-动画特效)__ `$(selector).animate({params},speed,[callback])`

```js
$(function () {
    $("span").animate({
        width: "80px",
        height: "80px"
    },
    3000, function () {
        $("#tip").html("执行完成!");
    });
});
```
> _params_ 参数为制作动画效果的CSS属性名与值，_speed_ 参数为动画的效果的速度，单位为毫秒，可选项 _callback_ 参数为动画完成时执行的回调函数名。

- __[调用 animate() 方法制作移动位置的动画](#jquery-动画特效)__ `$(selector).animate({params},speed,[callback])`

```js
$(function () {
    $("span").animate({
        left: "+=100px"
    }, 3000, function () {
        $("span").animate({
            height: '+=30px',
            width: '+=30px'
        }, 3000, function () {
            $("#tip").html("执行完成!");
        });
    });
});

先移动,再放大,最后显示字样
```
>调用 __*animate()*__ 方法不仅可以制作简单渐渐变大的动画效果，而且还能制作移动位置的动画，在移动位置之前，必须将被移元素的 “_position_” 属性值设为 “_absolute_” 或 “_relative_”，否则，该元素移动不了。

- __[调用 stop() 方法停止当先所有动画效果](#jquery-动画特效)__ `$(selector).stop([clearQueue],[goToEnd])`

>__*stop()*__ 方法的功能是在动画完成之前，停止当前正在执行的动画效果，这些效果包括滑动、淡入淡出和自定义的动画。  
>其中，两个__可选项__参数 _clearQueue_ 和 _goToEnd_ 都是__布尔__类型值，前者表示是否停止正在执行的动画，后者表示是否完成正在执行的动画，默认为 _false_ 。

- __[调用 delay() 方法延时执行动画效果](#jquery-动画特效)__ `$(selector).delay(duration)`

>参数 _duration_ 为延时值，它的单位是毫秒，当超过延时值时，动画继续执行。

***

<a name="jquery-实现ajax应用"></a>
## jQuery 实现Ajax应用

- __[使用 load() 方法异步请求数据](#jquery-实现ajax应用)__ `load(url,[data],[callback])`

>使用 __*load()*__ 方法通过Ajax请求加载服务器中的数据，并把返回的数据放置到指定的元素中。  
>参数 _url_ 为加载服务器地址，可选项 _data_ 参数为请求时发送的数据， _callback_ 参数为数据请求成功后，执行的回调函数。

- __[使用 getJSON() 方法异步加载JSON格式数据](#jquery-实现ajax应用)__  
`jQuery.getJSON(url,[data],[callback])` __或__ `$.getJSON(url,[data],[callback])`

```js
$(function () {
    $("#btnShow").bind("click", function () {
        var $this = $(this);
        $.getJSON("http://www.imooc.com/data/sport.json",function(data){
            $this.attr("disabled", "true");
            $.each(data, function (index, sport) {
                if(index==3)
                $("ul").append("<li>" + sport["name"] + "</li>");
            });
        });
    });
});
```
>使用 __*getJSON()*__ 方法可以通过Ajax异步请求的方式，获取服务器中的数组，并对获取的数据进行解析，显示在页面中。  
> _url_ 参数为请求加载 _json_ 格式文件的服务器地址，可选项 _data_ 参数为请求时发送的数据，_callback_ 参数为数据请求成功后，执行的回调函数。

- __[使用 getScript() 方法异步加载并执行js文件](#jquery-实现ajax应用)__  
`jQuery.getScript(url,[callback])` __或__ `$.getScript(url,[callback])`

```js
加载例如这样的javascript文件

var data = [{
    "name": "足球"
}, {
    "name": "散步"
}, {
    "name": "篮球"
}, {
    "name": "乒乓球"
}, {
    "name": "骑自行车"
}];
$.each(data, function (index, sport) {
    if (index == 1)
        $("ul").append("<li>" + sport["name"] + "</li>");
});
```

- __[使用 get() 方法以 GET 方式从服务器获取数据](#jquery-实现ajax应用)__ `$.get(url,[callback])`

- __[使用 post() 方法以 POST 方式从服务器发送数据](#jquery-实现ajax应用)__ `$.post(url,[data],[callback])`

- __[使用 serialize() 方法序列化表单元素值](#jquery-实现ajax应用)__ `$(selector).serialize()`

```js
$(function () {
  $("#btnAction").bind("click", function() {
    $("#litest").html($("form").serialize() );
  });
});
```
>使用 __*serialize()*__方法可以将表单中有 _name_ 属性的元素值进行序列化，生成标准 _URL_ 编码文本字符串，直接可用于 _ajax_ 请求。其中 _selector_ 参数是一个或多个表单中的元素或表单元素本身。

- __[使用 ajax() 方法加载服务器数据](#jquery-实现ajax应用)__ `jQuery.ajax([settings])` 或 `$.ajax([settings])`

```js
$(function () {
    $("#btnCheck").bind("click", function () {
        $.ajax({
            url: "http://www.imooc.com/data/check.php",
            data: { num: $("#txtNumber").val() },
            type: "post",
            success: function (data) {
                $("ul").append("<li>你输入的<b>  "
                + $("#txtNumber").val() + " </b>是<b> "
                + data + " </b></li>");
            };
        });
    });
});
```
>使用 __*ajax()*__ 方法是最底层、功能最强大的请求服务器数据的方法，它不仅可以获取服务器返回的数据，还能向服务器发送请求并传递数值。  
>其中参数 _settings_ 为发送 _ajax_ 请求时的配置对象，在该对象中，_url_ 表示服务器请求的路径，_data_ 为请求时传递的数据，_dataType_ 为服务器返回的数据类型，_success_ 为请求成功的执行的回调函数，_type_ 为发送数据请求的方式，默认为 _get_ 。

- __[使用 ajaxSetup() 方法设置全局Ajax默认选项](#jquery-实现ajax应用)__ `jQuery.ajaxSetup([options])` 或 `$.ajaxSetup([options])`

```js
$(function () {
  $.ajaxSetup({
      type: "post",
      success: function (data) {
      $("ul").append("<li>你输入的<b>  "
          + $("#txtNumber").val() + " </b>是<b> "
          + data + " </b></li>");
      }
  });
  $("#btnShow_1").bind("click", function () {
      $.ajax({
          data: { num: $("#txtNumber").val() },
          url: "http://www.imooc.com/data/check.php"
      });
  });
  $("#btnShow_2").bind("click", function () {
      $.ajax({
          data: { num: $("#txtNumber").val() },
          url: "http://www.imooc.com/data/check_f.php"
      });
});
```
>使用 __*ajaxSetup()*__方法可以设置 Ajax 请求的一些全局性选项值，设置完成后，后面的 Ajax 请求将不需要再添加这些选项值。可选项 _options_ 参数为一个对象，通过该对象设置 Ajax 请求时的全局选项值。

- __[使用 ajaxStart() 和 ajaxStop() 方法](#jquery-实现ajax应用)__  
`$(selector).ajaxStart(function())`  
`$(selector).ajaxStop(function())`

>__*ajaxStart()*__ 和 __*ajaxStop()*__ 方法是绑定 Ajax 事件。__*ajaxStart()*__ 方法用于在 Ajax 请求发出前触发函数，__*ajaxStop()*__ 方法用于在 Ajax 请求完成后触发函数。两个方法中括号都是绑定的函数，当发送 Ajax 请求前执行 __*ajaxStart()*__ 方法绑定的函数，请求成功后，执行 __*ajaxStart()*__ 方法绑定的函数。  
>__注意：__ 该方法在1.8.2下使用是正常的

***

<a name="jquery-常用插件"></a>
## jQuery 常用插件

- __[表单验证插件 —— validate](#jquery-常用插件)__ `$(form).validate({options})`

```js
$(function () {
  $("#frmV").validate(
    {
      /*自定义验证规则*/
      rules: {
        email: {
            required: true,
            email: true
        }
      },
      /*错误提示位置*/
      errorPlacement: function (error, element) {
        error.appendTo(".tip");
      };
    };
  );
});
```
>该插件自带包含必填、数字、URL在内容的验证规则，即时显示异常信息，此外，还允许自定义验证规则。  
>其中 _form_ 参数表示表单元素名称，_options_ 参数表示调用方法时的配置对象，所有的验证规则和异常信息显示的位置都在该对象中进行设置。

- __[表单插件 —— form](#jquery-常用插件)__ `$(form).ajaxForm({options})`

```js
 $(function () {
  var options = {
    url: "http://www.imooc.com/data/form_f.php",
    target: ".tip"
  }
  $("#frmV").ajaxForm(options);
});
```
>通过表单 _form插件_，调用 __*ajaxForm()*__ 方法，实现 ajax 方式向服务器提交表单数据，并通过方法中的 _options_ 对象获取服务器返回数据。其中 _form_ 参数表示表单元素名称；_options_ 是一个配置对象，用于在发送 ajax 请求过程，设置发送时的数据和参数。

- __[图片灯箱插件 —— liaghtBox](#jquery-常用插件)__ `$(linkimage).lightBox({options})`

```js
$(function () {
    $(".divPics a").lightBox({
        overlayBgColor: "#666", //图片浏览时的背景色
        overlayOpacity: .5, //背景色的透明度
        containerResizeSpeed: 100 //图片切换时的速度
    })
});
```
>该插件可以用圆角的方式展示选择中的图片，使用按钮查看上下张图片，在加载图片时自带进度条，还能以自动播放的方式浏览图片。其中 _linkimage_ 参数为包含图片的 `<a>`元素名称，_options_ 为插件方法的配置对象。

- __[图片放大插件 —— jqzoom](#jquery-常用插件)__ `$(linkimage).jqzoom({options})`

```js
 $(function () {
    $("#jqzoom").jqzoom({ //绑定图片放大插件jqzoom
        zoomWidth: 123, //小图片所选区域的宽
        zoomHeight: 123, //小图片所选区域的高
        zoomType: 'reverse' //设置放大镜的类型
    });
});
```
>在调用 _jqzoom图片放大镜插件_ 时，需要准备一大一小两张一样的图片，在页面中显示小图片，当鼠标在小图片中移动时，调用该插件的 __*jqzoom()*__ 方法，显示与小图片相同的大图片区域，从而实现放大镜的效果。其中 _linkimage_ 参数为包含图片的`<a>`元素名称，_options_ 为插件方法的配置对象。

- __[cookie插件 —— cookie](#jquery-常用插件)__  
`保存：$.cookie(key，value)`  
`读取：$.cookie(key)`  
`删除：$.cookie(key，null)`

```js
$(function () {
    if ($.cookie("email")) {
        $("#email").val($.cookie("email"));
    }
    $("#btnSet").bind("click", function () {
        if ($("#chksave").is(":checked")) {
            $.cookie("email",$("#email".val()), {
                path: "/", expires: 7
            })
        }
        else {
            $.cookie("email",null), {
                path: "/"
            })
        };
    });
});

expires 保存的有效天数
```
>使用 _cookie插件_ 后，可以很方便地通过 _cookie对象_ 保存、读取、删除用户的信息，还能通过 _cookie插件_ 保存用户的浏览记录。其中参数 _key_ 为保存 _cookie对象_ 的名称，_value_ 为名称对应的 _cookie值_。

- __[搜索插件 —— autocomplete](#jquery-常用插件)__ `$(textbox).autocomplete(urlData,[options])`

```js
$(function () {
    var arrUserName = ["王五", "刘明", "李小四", "刘促明", "李渊", "张小三", "王小明"];
    $("#txtSearch").autocomplete(arrUserName,{
        minChars: 0, //双击空白文本框时显示全部提示数据
        formatItem: function (data, i, total) {
            return "<I>" + data[0] + "</I>"; //改变匹配数据显示的格式
        },
        formatMatch: function (data, i, total) {
            return data[0];
        },
        formatResult: function (data) {
            return data[0];
        }
    }).result(SearchCallback); //选中匹配项目的某项数据时，调用插件的result()方法
    function SearchCallback(event, data, formatted) {
        $(".tip").show().html("您的选择是：" + (!data ? "空" : formatted));
    }
});
```
>搜索插件的功能是通过插件的 __*autocomplete()*__ 方法与文本框相绑定，当文本框输入字符时，绑定后的插件将返回与字符相近的字符串提示选择。其中，_textbox_ 参数为文本框元素名称，_urlData_ 为插件返回的相近字符串数据，可选项参数 _options_ 为调用插件方法时的配置对象。

- __[右键菜单插件 —— contextmenu](#jquery-常用插件)__ `$(selector).contextMenu(menuId,{options})`

```js
$(function () {
    $("#btnSubmit").contextMenu("sysMenu",
      { bindings:
         {
             'Li3': function (Item) {
                 $(".tip").show().html("您点击了“保存”项");
             },
             'Li4': function (Item) {
                 $(".tip").show().html("您点击了“退出”项");
             }
         }
      });
});
```
>右键菜单插件可以绑定页面中的任意元素，绑定后，选中元素，点击右键，便通过该插件弹出一个快捷菜单，点击菜单各项名称执行相应操作。_Selector_ 参数为绑定插件的元素，_meunId_ 为快捷菜单元素，_options_ 为配置对象。

- __[自定义对象级插件 —— lifocuscolor](#jquery-常用插件)__ `$(Id).focusColor(color)`

```js
$(function () {
    $("#u1").focusColor("#ccc"); //调用自定义的插件
})
```
>自定义的 _lifocuscolor插件_ 可以在`<ul>`元素中，鼠标在表项`<li>`元素移动时，自定义其获取焦点时的背景色，即定义`<li>`元素选中时的背景色。其中，参数 _Id_ 表示`<ul>`元素的 _Id_ 号，_color_ 表示`<li>`元素选中时的背景色。

- __[自定义类级别插件 —— twoaddresult](#jquery-常用插件)__  
`$.addNum(p1,p2)`  
`$.subNum(p1,p2)`

```js
$(function () {
    $("#btnCount").bind("click", function () {
        $("#Text3").val(
            $.subNum($("#Text1").val(),$("#Text2").val())
        );
    });
});
```
>通过调用自定义插件 _twoaddresult_ 中的不同方法，可以实现对两个数值进行相加和相减的运算，上述调用格式分别为计算两数值相加和相减的结果，_p1_ 和 _p2_ 为任意数值。

***

<a name="jquery-ui型插件"></a>
## jQuery UI型插件

- __[拖拽插件 —— draggable](#jquery-ui型插件)__ `$(selector).draggable({options})`

```js
$(function () {
    $("#x").draggable({containment:"parent",axis:"x"})
    $("#y").draggable({containment:"parent",axis:"y"})
});
```
>拖曳插件 _draggable_ 的功能是拖动被绑定的元素，当这个jQuery UI插件与元素绑定后，可以通过调用 __*draggable()*__ 方法，实现各种拖曳元素的效果。_options_ 参数为方法调用时的配置对象，根据该对象可以设置各种拖曳效果，如“_containment_”属性指定拖曳区域，“_axis_”属性设置拖曳时的坐标方向。

- __[放置插件 —— droppable](#jquery-ui型插件)__ `$(selector).droppable({options})`

```js
$(function () {
    $(".drag").draggable();
    $(".cart").droppable({
        drop: function () {
                $(this)
                .addClass("focus")
                .find("#tip").html("");
        }
    });
    $("#divtest").children(':first').droppable({
        drop:function(){
            $(".cart").removeClass("focus");
            $("#tip").html("还没有产品");
        }
    });
});
```
```js
禁用id号为test的div元素的拖动动作后,重新开启的代码为:

$("#test").draggable("enable");
```
>除使用 _draggable插件_ 拖曳任意元素外，还可以调用 _droppable UI插件_ 将拖曳后的任意元素放置在指定区域中，类似购物车效果。_selector_ 参数为接收拖曳元素，_options_ 为方法的配置对象，在对象中，_drop函数_ 表示当被接收的拖曳元素完全进入接收元素的容器时，触发该函数的调用。

- __[拖拽排序插件 —— sortable](#jquery-ui型插件)__ `$(selector).sortable({options})`

```js
$(function () {
    $("ul").sortable({
        delay: 2,   //为了防止与点击事件冲突，延迟2秒
        opacity: 0.35   //以透明度0.35随意拖动
    })
});
```
>拖曳排序插件的功能是将序列元素（例如`<option>`、`<li>`）按任意位置进行拖曳从而形成一个新的元素序列，实现拖曳排序的功能。_selector_ 参数为进行拖曳排序的元素，_options为_ 调用方法时的配置对象。

- __[面板折叠插件 —— accordion](#jquery-ui型插件)__ `$(selector).accordion({options})`

```js
<div id="divtest">
    <div id="accordion">
        <h3>
            <a href="#">白富美</a>
        </h3>
        <p>咱们结婚吧!</p>
        <h3>
            <a href="#">土豪族</a>
        </h3>
        <p>咱们交个朋友吧!</p>
    </div>
</div>

<script type="text/javascript">
    $(function () {
        $("#accordion").accordion();
    });
</script>
```
>面板折叠插件可以实现页面中指定区域类似“手风琴”的折叠效果，即点击标题时展开内容，再点另一标题时，关闭已展开的内容。其中，参数 _selector_ 为整个面板元素，_options_ 参数为方法对应的配置对象。

- __[选项卡插件 —— tabs](#jquery-ui型插件)__ `$(selector).tabs({options})`

```js
<div id="divtest">
    <div id="tabs">
        <ul>
            <li><a href="#tabs-1">最爱吃的水果</a></li>
            <li><a href="#tabs-2">最喜欢的运动</a></li>
        </ul>
        <div id="tabs-1">
            <p>橘子</p>
            <p>香蕉</p>
            <p>葡萄</p>
            <p>苹果</p>
            <p>西瓜</p>
        </div>
        <div id="tabs-2">
            <p>足球</p>
            <p>散步</p>
            <p>篮球</p>
            <p>乒乓球</p>
            <p>骑自行车</p>
        </div>
    </div>
</div>

<script type="text/javascript">
    $(function () {
       $("#tabs").tabs({
            //设置各选项卡在切换时的动画效果
            fx: { opacity: "toggle", height: "toggle" },
            event: "mousemove" //通过移动鼠标事件切换选项卡
        })
    });
</script>
```
>使用选项卡插件可以将`<ul>`中的`<li>`选项定义为选项标题，在标题中，再使用`<a>`元素的“_href_”属性设置选项标题对应的内容。_selector_ 参数为选项卡整体外围元素，该元素包含选项卡标题与内容，_options_ 参数为 __*tabs()*__方法的配置对象，通过该对象还能以 _ajax_ 方式加载选项卡的内容。

- __[对话框插件 —— dialog](#jquery-ui型插件)__ `$(selector).dialog({options})`

```js
<div id="divtest">
    <div class="content">
        <span id="spnName" class="fl">张三</span>
        <input id="btnDelete" type="button" value="删除"  class="fr"/>
    </div>
    <div id='dialog-modal'></div>
</div>

<script type="text/javascript">
    $(function () {
        $("#btnDelete").bind("click", function () { //询问按钮事件
            if ($("#spnName").html() != null) { //如果对象不为空
                sys_Confirm("您真的要删除该条记录吗？");
                return false;
            }
        });
    });
    function sys_Confirm(content) { //弹出询问信息窗口
        $("#btnDelete").dialog({
            height: 140,
            modal: true,
            title: '系统提示',
            hide: 'slide',
            buttons: {
                '确定': function () {
                    $("#spnName").remove();
                    $(this).dialog("close");
                },
                '取消': function () {
                    $(this).dialog("close");
                }
            },
            open: function (event, ui) {
                $(this).html("");
                $(this).append("<p>" + content + "</p>");
            }
        });
    }
</script>
```
>对话框插件可以用动画的效果弹出多种类型的对话框，实现JavaScript代码中 _alert()_ 和 _confirm()_ 函数的功能。_selector_ 参数为显示弹出对话框的元素，通常为`<div>`，_options_ 参数为方法的配置对象，在对象中可以设置对话框类型、“确定”、“取消”按钮执行的代码等。

- __[菜单工具插件 —— menu](#jquery-ui型插件)__ `$(selector).menu({options})`

```js
<ul id="menu">
    <li><a href="#">小明一中</a>
        <ul>
            <li><a href="#">高中部</a>
                <ul>
                    <li><a href="#">高一(1)班</a></li>
                    <li><a href="#">高一(2)班</a></li>
                    <li><a href="#">高一(3)班</a>
                        <ul>
                            <li><a href="#">小胡</a></li>
                            <li><a href="#">小李</a></li>
                            <li><a href="#">小陈</a></li>
                        </ul>
                    </li>
                </ul>
            </li>
            <li><a href="#">初中部</a>
                <ul>
                    <li><a href="#">初一(1)班</a></li>
                    <li><a href="#">初一(2)班</a></li>
                    <li><a href="#">初一(3)班</a></li>
                </ul>
            </li>
            <li><a href="#">教研部</a></li>
        </ul>
    </li>
    <li class="ui-state-disabled"><a href="#">大明二中</a></li>
</ul>

<script type="text/javascript">
    $(function () {
        $("#menu").menu();
    });
</script>
```
>菜单工具插件可以通过`<ul>`创建多级内联或弹出式菜单，支持通过键盘方向键控制菜单滑动，允许为菜单的各个选项添加图标。_selector_ 参数为菜单列表中最外层`<ul>`元素，_options_ 为 __*menu()*__ 方法的配置对象。  
>将`<li>`元素的 _class_ 属性值设为“_ui-state-disabled_”，可将菜单选项置为不可用状态。

- __[微调按钮插件 —— spinner](#jquery-ui型插件)__ `$(selector).spinner({options})`

```js
$(function () {
    //定义变量
    var intR = 0, intG = 0, intB = 0, strColor;
    $("input").spinner({
        //初始化插件
        max: 10,
        min: 0,
        //设置微调按钮递增/递减事件
        spin: function (event, ui) {
            if (ui.value == 8)
                spnPrev.style.backgroundColor = "red";
            else
                spnPrev.style.backgroundColor = "green";
        },
        //设置微调按钮值改变事件
        change: function (event, ui) {
            var intTmp = $(this).spinner("value");
            if (intTmp < 0) $(this).spinner("value", 0);
            if (intTmp > 10) $(this).spinner("value", 10);
            if (intTmp == 8)
                spnPrev.style.backgroundColor = "red";
            else
                spnPrev.style.backgroundColor = "green";
        }
    });
});
```
>微调按钮插件不仅能在文本框中直接输入数值，还可以通过点击输入框右侧的上下按钮修改输入框的值，还支持键盘的上下方向键改变输入值。_selector_ 参数为文本输入框元素，可选项 _options_ 参数为 __*spinner()*__ 方法的配置对象，在该对象中，可以设置输入的最大、最小值，获取改变值和设置对应事件。

- __[工具提示插件 —— tooltip](#jquery-ui型插件)__ `$(selector).tooltip({options})`

```js
<div id="divtest">
    <div class="title">
        工具提示插件</div>
    <div class="content">
        <div>
            <label for="name">
                姓名</label>
            <input id="name" name="name" title="我是土豪，欢迎与我做朋友" />
        </div>
    </div>
</div>

<script type="text/javascript">
    $(function () {
        $("#name").tooltip({
            show: {
                effect: "slideDown",
                delay: 350
            },
            hide: {
                effect: "explode",
                delay: 350
            },
            position: {
                my: "left top",
                at: "left bottom"
            }
        });
    });
</script>
```
>工具提示插件可以定制元素的提示外观，提示内容支持变量、Ajax远程获取，还可以自定义提示内容显示的位置。其中 _selector_ 为需要显示提示信息的元素，可选项参数 _options_ 为 __*tooltip()*__ 方法的配置对象，在该对象中，可以设置提示信息的弹出、隐藏时的效果和所在位置。

***

<a name="jquery-工具类函数"></a>
## jQuery 工具类函数

- __[获取浏览器的名称与版本信息](#jquery-工具类函数)__ `$.browser.[browsername/version]`

```js
$(function () {
    var strTmp = "您的浏览器名称是：";
    if ($.browser.chrome) { //谷歌浏览器
        strTmp += "Chrome";
    }
    if ($.browser.mozilla) { //火狐相关浏览器
        strTmp += "Mozilla FireFox";
    }
    strTmp += "<br /><br /> 版本号是：" //获取版本号
           + $.browser.version;
    $(".content").html(strTmp);
});
```
>在jQuery中，通过`$.browser`对象可以获取浏览器的名称和版本信息，如`$.browser.chrome`为true，表示当前为Chrome浏览器，`$.browser.mozilla`为true，表示当前为火狐浏览器，还可以通过`$.browser.version`方式获取浏览器版本信息。

- __[检测浏览器是否属于W3C盒子模型](#jquery-工具类函数)__ `$.support.boxModel`

```js
$(function () {
    var strTmp = "您打开的页面是：";
    if ($.support.boxModel) { //是W3C盒子模型
        strTmp += "W3C盒子模型";
    }
    else { //是IE盒子模型
        strTmp += "IE盒子模型";
    }
    $(".content").html(strTmp);
});
```
>浏览器的盒子模型分为两类，一类为标准的 _w3c_ 盒子模型，另一类为 _IE_ 盒子模型，两者区别为在 _Width_ 和 _Height_ 这两个属性值中是否包含 _padding_ 和 _border_ 的值，_w3c_ 盒子模型不包含，_IE_ 盒子模型则包含，而在jQuery中，可以通过`$.support.boxModel`对象返回的值，检测浏览器是否属于标准的 _w3c_ 盒子模型。

- __[检测对象是否为空](#jquery-工具类函数)__ `$.isEmptyObject(obj)`

```js
$(function () {
    var obj = { "姓名": "土豪一族" };
    var strTmp = "您定义了一个：";
    if ($.isEmptyObject(obj)) { //检测是否为空
        strTmp += "空对象";
    }
    else {
        strTmp += "非空对象";
    }
    $(".content").html(strTmp);
});
```
>在jQuery中，可以调用名为`$.isEmptyObject`的工具函数，检测一个对象的内容是否为空，如果为空，则该函数返回 _true_，否则，返回 _false_ 值。其中，参数 _obj_ 表示需要检测的对象名称。

- __[检测对象是否为原始对象](#jquery-工具类函数)__ `$.isPlainObject(obj)`

```js
$(function () {
    var obj = "null";
    var strTmp = "您定义了一个：";
    if ($.isPlainObject(obj)) { //检测是否为原始对象
        strTmp += "原始对象";
    }
    else {
        strTmp += "非原始对象";
    }
    $(".content").html(strTmp);
});
```
>调用名为`$.isPlainObject`的工具函数，能检测对象是否为通过 _{}_ 或 _new Object()_ 关键字创建的原始对象，如果是，返回 _true_，否则，返回 _false_ 值。其中，参数 _obj_ 表示需要检测的对象名称。

- __[检测两个节点的包含关系](#jquery-工具类函数)__ `$.contains(container, contained)`

```js
$(function () {
    var node_a = document.body.firstChild;
    var node_b = document.body;
    var strTmp = "对象node_a";
    if ($.contains(node_a, node_b)) { //检测是否包含节点
        strTmp += " 包含 ";
    }
    else {
        strTmp += " 不包含 ";
    }
    strTmp += "对象node_b";
    $(".content").html(strTmp);
});
```
>调用名为`$.contains`的工具函数，能检测在一个DOM节点中是否包含另外一个DOM节点，如果包含，返回 _true_，否则，返回 _false_ 值。参数 _container_ 表示一个DOM对象节点元素，用于包含其他节点的容器，_contained_ 是另一个DOM对象节点元素，用于被其他容器所包含。

- __[字符串操作函数](#jquery-工具类函数)__ `$.trim(str)`

```js
$(function () {
    $("#btnShow").bind("click", function () {
        $(".tip").html("");
        var strTmp = "内容：";
        var strOld = $("#txtName").val();
        var strNew = $.trim(strOld);
        strTmp += strOld;
        strTmp += "<br/><br>除掉空格符前的长度："
        strTmp += strOld.length;
        strTmp += "<br/><br>除掉空格符后的长度："
        strTmp += strNew.length;
        $(".tip").show().append(strTmp);
    });
});
```
>调用名为`$.trim`的工具函数，能删除字符串中左右两边的空格符，但该函数不能删除字符串中间的空格。参数 _str_ 表示需要删除左右两边空格符的字符串。

- __[URL操作函数](#jquery-工具类函数)__ `$.param(obj)`

```js
$(function () {
    //基本信息对象
    var objInfo = new Object();
    objInfo.name = "白富美";
    objInfo.sex = 1;
    //序列化对象
    var objNewInfo =$.param(objInfo);
    //显示序列化后的对象
    var strTmp = "<b>对象 白富美 序列化后</b>：<br/><br/>";
    strTmp += objNewInfo;
    //显示在页面中
    $(".tip").show().append(strTmp);
});
```
>调用名为`$.param`的工具函数，能使对象或数组按照`key/value`格式进行序列化编码，该编码后的值常用于向服务端发送URL请求。参数 _obj_ 表示需要进行序列化的对象，该对象也可以是一个数组，整个函数返回一个经过序列化编码后的字符串。

>__注意 _param_ 和 _serialize_ 的区别:__ 前者是对任意的参数进行 _URL_ 地址格式的转换，而后者仅属于 _form_ 提交的数据转换。

- __[使用 $.extend() 扩展工具函数](#jquery-工具类函数)__ `$.extend({options})`

```js
/*------------------------------------------------------------/
功能：返回两个数中最小值
参数：数字p1,p2
返回：最小值的一个数
示例：$.MinNum(1,2);
/------------------------------------------------------------*/
(function ($) {
    $.extend({
        "MinNum": function (p1, p2) {
            return (p1 > p2) ? p2 : p1;
        }
    });
})(jQuery);
$(function () {
    $("#btnShow").bind("click", function () {
        $(".tip").html("");
        var strTmp = "17与18中最小的数是：";
        strTmp +=$.MinNum (17, 18);
        //显示在页面中
        $(".tip").show().append(strTmp);
    });
});
```
>调用名为`$.extend`的工具函数，可以对原有的工具函数进行扩展，自定义类级别的jQuery插件。参数 _options_ 表示自定义插件的函数内容。

- __[使用 $.extend() 扩展 Object 对象](#jquery-工具类函数)__ `$.extend(obj1,obj2,…objN)`

>除使用`$.extend`扩展工具函数外，还可以扩展原有的 _Object_ 对象，在扩展对象时，两个对象将进行合并，当存在相同属性名时，后者将覆盖前者。参数 _obj1_ 至 _objN_ 表示需要合并的各个原有对象。

***






