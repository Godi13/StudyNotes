# jQuery 学习笔记

<!-- MarkdownTOC -->

- [引入jQuery文件库](#引入jquery文件库)
- [选择器](#选择器)
- [过滤选择器](#过滤选择器)

<!-- /MarkdownTOC -->


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

- __[#id选择器]()__ `$("#my_id")`
```javascript
<div id="divtest">div的内容</div>
<div id="default"></div>
<script type="text/javascript">
  $("#default").html($("#divtest").html());
</script>
```

- __[element选择器]()__ `$("element")`
```javascript
<button id="btntest">点我</button>
<script type="text/javascript">
  $("button").attr("disabled","true");
</script>
```

- __[.class选择器]()__ `$(".class")`

- __[*选择器]()__ `$("*")`
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

- __[sele1,sele2,seleN选择器]()__ `$("sele1,sele2,seleN")`
```javascript
$(".red,.green").html("Hello");
$("div,p").html("World");
```

- __[ance desc选择器](http://www.imooc.com/code/86)__ `$("ance desc")`
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

- __[parent > child选择器](http://www.imooc.com/code/95)__ `$("parent > child")`
>获取子辈元素，不包括孙辈元素

- __[prev + next选择器]()__ `$("prev + next")`
>“prev”元素最紧邻的下一个元素由“next”选择器返回的并且只返回唯的一个元素。

- __[prev ～ siblings选择器]()__ `$("prev ～ siblings")`
>获取prev元素后面全部相邻的元素,不包含不属于同辈的元素

***

<a name="过滤选择器"></a>
## 过滤选择器
