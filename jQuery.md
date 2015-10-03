# jQuery 学习笔记
>总结自[慕课网 - jQuery基础课程](http://www.imooc.com/learn/11)，在此感谢

## 索引
<!-- MarkdownTOC -->

- [引入jQuery文件库](#引入jquery文件库)
- [选择器](#选择器)
- [过滤选择器](#过滤选择器)
- [属性选择器](#属性选择器)
- [表单选择器](#表单选择器)

<!-- /MarkdownTOC -->

***

<a name="引入jquery文件库"></a>
## 引入jQuery文件库
```javascript
<script src="http://libs.baidu.com/jquery/1.9.0/jquery.js" type="text/javascript"></script>
```

***

##### JavaScript代码
```javascript
var page_ps=document.getElementsByTagName("p");
for(var i = 0; i < page_ps.length; i++) {
  page_ps[i].innerHTML = "Hello imooc!";
}
```
##### jQuery代码
```javascript
$("p").html("Hello imooc!");
```

***

<a name="选择器"></a>
## 选择器

- __[#id选择器](#选择器)__ `$("#my_id")`

```javascript
<div id="divtest">div的内容</div>
<div id="default"></div>
<script type="text/javascript">
  $("#default").html($("#divtest").html());
</script>
```

- __[element选择器](#选择器)__ `$("element")`

```javascript
<button id="btntest">点我</button>
<script type="text/javascript">
  $("button").attr("disabled","true");
</script>
```

- __[.class选择器](#选择器)__ `$(".class")`

- __[*选择器](#选择器)__ `$("*")`

```javascript
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

```javascript
$(".red,.green").html("Hello");
$("div,p").html("World");
```

- __[ance desc选择器](http://www.imooc.com/code/86)__ `$("ance desc")` ?!

>其中ance desc是使用空格隔开的两个参数。ance参数（ancestor祖先的简写）表示父元素；desc参数（descendant后代的简写）表示后代元素，即包括子元素、孙元素等等。

```javascript
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

```javascript
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

```javascript
$("#frmTest :checkbox").attr("disabled","true"); 将属性设置为不可用
```

- __[:submit 提交按钮选择器](#表单选择器)__  `例如：$("#frmTest input:submit")`

>通常情况下，一个表单中只允许有一个“type”属性值为“submit”的提交按钮，使用 __*:submit*__ 选择器可获取表单中的这个提交按钮元素。  
>__注意：__ `$("#frmTest input:submit")`中`:submit`前面有`input`

- __[:image 图像域选择器](#表单选择器)__  `例如：$("#frmTest :image")`

>当一个`<input>`元素的“type”属性值设为“image”时，该元素就是一个图像域，使用 __*:image*__ 选择器可以快速获取该类全部元素。  
>使用 __*:image*__ 选择器只能获取`<input>`图像域，而不能获取`<img>`格式的图像元素。

- __[:button 表单按钮选择器](#表单选择器)__  `例如：$("#frmTest :button")`

>表单中包含许多类型的按钮，而使用 __*:button*__ 选择器能获取且只能获取“_type_”属性值为“button”的`<input>`和`<button>`这两类普通按钮元素。

- __[:checked 选中状态选择器](#表单选择器)__  `例如：$("#frmTest :checked")`

>有一些元素存在选中状态，如复选框、单选按钮元素，选中时“checked”属性值为“checked”，调用 __*:checked*__ 可以获取处于选中状态的全部元素。

- __[:selected 选中状态选择器](#表单选择器)__  `例如：$("#frmTest :selected")`

>与 __*:checked*__ 选择器相比，__*:selected*__ 选择器只能获取`<select>`下拉列表框中全部处于选中状态的`<option>`选项元素。
