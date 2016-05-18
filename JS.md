<!-- MarkdownTOC -->

- [JS 相关总结](#js-相关总结)
  - [JavaScript 知识点](#javascript-知识点)
    - [变量提升](#变量提升)
    - [严格模式](#严格模式)
    - [闭包](#闭包)
    - [函数声明与表达式](#函数声明与表达式)
  - [JavaScript 常用指令](#javascript-常用指令)
    - [BOM](#bom)
    - [数据](#数据)
    - [文本](#文本)
    - [Array](#array)
    - [循环](#循环)
    - [DOM](#dom)
    - [事件](#事件)
    - [日期](#日期)
    - [Math](#math)
    - [Cookie](#cookie)

<!-- /MarkdownTOC -->


<a name="js-相关总结"></a>
# JS 相关总结
__阮一峰__ [JavaScript 标准参考教程（alpha）](http://javascript.ruanyifeng.com/)

***

<a name="javascript-知识点"></a>
## JavaScript 知识点

<kbd>ctrl</kbd>+<kbd>shift</kbd>+<kbd>j</kbd> chrome 中打开 console 快捷键  
<kbd>command</kbd>+<kbd>option</kbd>+<kbd>i</kbd> chrome 中打开 console 快捷键

<a name="变量提升"></a>
#### 变量提升

JavaScript引擎的工作方式是，先解析代码，获取所有被声明的变量，然后再一行一行地运行。这造成的结果，就是所有的变量的声明语句，都会被提升到代码的头部，这就叫做变量提升（hoisting）

```js
console.log(a);
var a = 1;
```

上面代码首先使用console.log方法，在控制台（console）显示变量a的值。这时变量a还没有声明和赋值，所以这是一种错误的做法，但是实际上不会报错。因为存在变量提升，真正运行的是下面的代码：

```js
var a;
console.log(a);
a = 1;
```
最后的结果是显示undefined，表示变量a已声明，但还未赋值。  

请注意，变量提升只对`var`命令声明的变量有效，如果一个变量不是用`var`命令声明的，就不会发生变量提升。

```js
console.log(b);
b = 1;
```

上面的语句将会报错，提示“ReferenceError: b is not defined”，即变量b未声明，这是因为b不是用var命令声明的，JavaScript引擎不会将其提升，而只是视为对顶层对象的b属性的赋值。


<a name="严格模式"></a>
#### 严格模式

严格模式是一种特殊的运行模式，它修复了部分语言上的不足，提供更强的错误检查，并增强安全性  
`use strict` 在文件开头或函数中添加，启用严格模式

* 严格模式不允许使用`with`语句
* 不允许未声明的变量被赋值
* `arguments`变为参数的静态副本，如下

```js
!function(a) {         !function(a){           !function(a) {}
  argument[0] = 100;     'use strict';           'use strict';
  console.log(a);         arguments[0] = 100;     arguments[0].x = 100;
}(1);                   }(1);                     console.log(a.x);
                                                }({x:1});
//100                    //1                   //100
```

* `delete`参数、函数名报错
* `delete`不可配置的属性报错
* 对象字谜昂量重复属性名报错
* 禁止八进制字面量
* `eval` `arguments` 变为关键字，不能作为变量、函数名
* `eval` 独立作用域

<a name="闭包"></a>
#### 闭包

1. 闭包的特点
    * 函数嵌套函数
    * 内部函数可以引用外部函数的参数和变量
    * 参数和变量不会被垃圾回收机制回收

2. 闭包的优点
    * 让变量长期驻扎在内存当中
    * 避免全局变量的污染
    * 私有成员的存在

3. 闭包的用法
    * 模块化代码
    * 在循环中直接找到对应元素的索引号

4. 闭包需要注意的地方
    * 在IE下容易引发内存泄露  
      使用`onunload`事件将变量设为`null`

<a name="函数声明与表达式"></a>
#### 函数声明与表达式
1. 函数表达式可以直接后面加括号执行，而函数声明是不可以的
2. 函数声明可以被提前解析出来的，尽量使用函数表达式

***

<a name="javascript-常用指令"></a>
## JavaScript 常用指令

<a name="bom"></a>
#### BOM


```js
confirm();            //选择true/false
pormpt(str1,str2);    //用户

window.open([URL],[窗口名称],[参数字符串])；    //menubar  toolbar
//如果url为空，则默认打开一个空白页面
//如果打开方式为空，则默认用新窗口方式
//返回值为新打开的window
window.open('http://www.imooc.com','_blank','width=600,height=200,top=100,left=0');
window.close();  //ff：无法关闭  chrome：直接关闭  ie：询问用户
//可以关闭在本窗口中通过js代码打开的新窗口

window.navigator.userAgent  //浏览器信息

if (window.location.href.indexOf('字符串') != -1)
//获取当前网页地址并判断是否包含指定字符
window.location.href    //返回值与window.location相同
window.location.search  //返回url？后面的内容,包含？
window.location.hash    //返回url#后面的内容，包含#

window.history.back();
window.history.go(-1);                       //等同于back
window.history.forward();

screen.width;                                //屏幕宽度
screen.availWidth;                           //屏幕可用宽度
screen.availHeight;                          //屏幕可用宽度

window.innerHeight;
window.innerWidth;
//浏览器窗口可视区域大小
var w=document.documentElement.clientWidth||document.body.clientWidth;
var h=document.documentElement.clientHeight||document.body.clientHeight;
//网页滚动的高度和宽度
var w=document.documentElement.scrollTop||document.body.scrollTop;
var h=document.documentElement.scrollLeft||document.body.scrollLeft;
//获取网页内容高度和宽度（包括滚动条等边线，会随窗口的显示大小改变）
var w=document.documentElement.scrollWidth||document.body.scrollWidth;
var h=document.documentElement.scrollHeight||document.body.scrollHeight;
//获取内容的高 offsetHeight = clientHeight + 滚动条 + 边框
var w= document.documentElement.offsetWidth||document.body.offsetWidth;
var h= document.documentElement.offsetHeight||document.body.offsetHeight;
```

<a name="数据"></a>
#### 数据

```js
//数值判断
isNaN()
isFinite()                       //检测是否为正常值

//数据的类型
parseInt(650.55);                //650,可将字符串类型转成整型，还可以去除空格
parseFloat(650.55);              //650.55
```

<a name="文本"></a>
#### 文本

```js
//文本字符串的处理
var words = 'Hello World';
words.length;                    //11
words.charAt(0);                 //"H"
words.charAt(words.length - 1);  //"d"

words.charCodeAt(0);             //查找字符串编码
String.fromCharCode(22937);      //输入字符串编码，返回‘妙’
String.fromCharCode(22937,21619);//妙味

words.indexOf('o');              //4
words.indexOf('ll');             //2
words.indexOf('o',5);            //7
words.indexOf('O');              //找不到，返回 -1
words.lastIndexOf('o');          //7
words.substring(0,5);            //"Hello"
words.replace('Hello','Hi');     //"Hi World"

var words = 'Hello,world';
words.split(',');                //["Hello", "world"],可以加参数限定分割长度
words.split(',',1);   //Hello
var newWords = words.split(',');
newWords[0];          //"Hello"

substring(num,num);              //提取两个指定下标之间的字符串
//如果后面的数小，则与前面的数交换位置
//如果有负数则自动处理为0
slice(num,num);
//如果后面的数小则返回空值
//如果有负数则倒着截取字符串
substr(num,num);                 //提取从第一个数开始指定数目o的字符

toLowerCase()
toUpperCase()

```

<a name="array"></a>
#### Array

```js
//Array
var trackCD1 = [1,2];
trackCD1.push(3,4);              //4,返回数组长度值,在数组最后插入指定数字
trackCD1                         //[1,2,3,4]
trackCD1.unshift(0);             //5,返回值为数组长度,在数组最前面插入指定内容,IE6、7不支持
trackCD1.pop();                  //4,删除最后一个元素，返回删除值
trackCD1.shift();                //0,删除第一个元素，返回删除值
delete trackCD1[1];              //[1, undefined × 1,3],不会影响数组的数量
trackCD1.splice(1);              //[undefined × 1,3],彻底删除
trackCD1;                        //[1]

trackCD2 = [3,4,5];
var tracks = trackCD1.concat(trackCD2);    //[2,3,4,5]

split()                           //分割
concat()                          //数组连接
join(分隔符)                       //指定分隔符连接数组
join()   //用于将数组中元素连接为字符串，如扩号中为空，连接的字符中包含`,`
reverse()
splice(startnum,endnum,'obj')    //选择指定范围间元素,替换为指定的元素
sort()                           //排序
sort(function(a,b){
  return a - b;       //如果为正数，则交换，如果为负数，不交换位置
})
```

<a name="循环"></a>
#### 循环

```js
//switch
switch (expression) {
  case expression:
    alert(anything);
    break;
  default:
    alert(otherthing);
}
需要注意的是，switch语句后面的表达式与case语句后面的表示式，在比较运行结果时，
采用的是严格相等运算符（===），而不是相等运算符（==），这意味着比较时不会发生类型转换。


//while
var i = 0;
while (i < 10) {
  i++;
  if (i % 2 === 0) {
    continue;
  }
  console.log(i);
}
```

<a name="dom"></a>
#### DOM

```js
//DOM
document.getElementById('id');
document.getElementsByTagName('tag');

document.querySelectorAll('selector');
document.querySelector('selector');          //返回找到的第一个结果

getAttribute()
setAttribute(属性，值)
removeAttribute()
//用.和[]无法操作标准浏览器下的自定义属性

.appendChild(newnode)       //插入节点
.insertBefore(newnode,node) //在node前插入newnode
.replace(newnode,oldnode)
.removeChild(node)

document.createElement()
document.createTextNode()

.nodeValue
.nodeType    //1元素节点 2属性节点 3文本节点
.childNodes  //只包含一级子节点，不包含后备孙级以下的节点
//标准下包含文本、元素类型的节点，也会包含非法嵌套的子节点
//非标准下只包含元素类型的节点,IE7以下不会包含非法嵌套子节点
.children    //与childNodes的不同在于只包含元素类型的节点
//属性
.firstChild  //标准下包含文本、元素节点  非标准下只包含元素节点
.firstElementChild  //标准下获取第一个元素类型的子节点,非标准下为undefined
.lastChild
.lastElementChild
.nextSibling
.nextElementSibling
.previousSibling
.previousElementSibling

.parentNode
.offsetParent    //离当前元素最近的有定位属性的父节点
//IE7以下，如果当前元素没有定位默认是body，如果有定位则是html
//IE7以下，如果当前元素的某个父级触发了layout，那么offsetParent就会被指向到这个触发了layout特性的父节点上
.offsetLeft[Top] //当前元素到定位父级的距离（偏移值）
//如果没有定位父级，offsetParent指向body，offsetLeft指向html
//IE7以下，如果当前元素没有定位，那么offsetLeft[Top]是到body的距离
//IE7以下，如果当前元素有定位，那么就是到定位父级的距离

.style.width : 样式宽
.clientWidth : 可视区宽：样式宽 + padding
.offsetWidth : 占位宽： 样式宽 + padding + border

```

<a name="事件"></a>
#### 事件

```js
event: 事件对象，当一个事件发生的时候，和当前这个事件发生的这个事件有关的一些详细信息都会被临时保存到一个指定的地方——event对象，供我们在需要的地方调用
事件对象必须在一个事件调用的函数中使用才有内容，一个函数是不是事件函数，不在定义的时候决定，而是取决于调用的时候
IE/chrome: event是一个内置全局对象
ff/标准: 事件对象是通过事件函数的第一个参数传入的，如果一个函数是被事件调用，那么这个函数定义的第一个参数就是事件对象
function fn(ev) { var ev = ev || event };

clientX[Y]  //当一个事件发生的时候，鼠标到页面可视区的距离,超出范围可以加上scrollTop

事件冒泡：当一个元素接收到事件的时候，会把他接收到的所有传播给他的父级，一直到顶层window
组织冒泡：在当前要阻止冒泡的事件函数中调用 event.cancelBubble = true;

事件绑定的第二种方式：
IE: obj.attachEvent(事件名称，事件函数);
document.attachEvent('onclick',fn);
//区别：1.没有捕获  2.事件名称有on  3.事件函数执行的顺序：标准ie正序，非标准ie倒序  4.this指向window
标准: obj.addEventListener(事件名称，事件函数，是否捕获);
document.addEventListener('click',fn,false); //false:冒泡,true:捕获
//事件监听器
xxx.addEventListener('字符串（事件的类型或名称）','调用的函数'，'false（默认值，事件的捕获）')

call 函数下的一个方法，第一个参数可以改变函数执行过程中内部this的指向,第二个参数开始就是原来函数的参数列表，如果第一个参数为null，则不改变内部this的指向
function bind(obj, evname, fn) {
  if (obj.addEventListener) {
    obj.addEventListener(evname, fn, false);
  } else {
    obj.attachEvent('on' + evname, function() {
      fn.call(obj);
    });
  }
}

事件取消绑定：
IE: obj.detachEvent(事件名称，事件函数);
标准: obj.removeEventListener(事件名称，事件函数，是否捕获);

//触发onload事件，事件写在<body>标签内

.onmouseenter .onmouseleave (子级不会影响到父级)

.onchange
//text:当光标离开时如果内容有变化便触发
//radio/checkbox:标准下点击时只要值变化就会触发，非标准下焦点离开时如果值变化则触发
.onsubmit  //当表单提交时触发
.onreset   //当表单重置时触发

setInterval(function,time);
clearInterval(setInterval());
setTimeout('function',interval);                   //延迟执行
clearTimeout(setTimeout());

onscroll: 当滚动条滚动的时候触发
onresize: 当窗口大小发生改变的时候触发
//上面两个都是按时间间隔来计算触发次数，与改变程度无关

onfocus
obj.focus()  //给指定的元素设置焦点
//不是所有的元素都能够接收焦点，能够响应用户操作的元素才有焦点
onblur
obj.blur()   //取消指定元素的焦点
obj.select() //选择指定元素里面用户可以输入的的文本内容

onkeydown: 当键盘按下时触发
onkeyup: 当键盘抬起时触发
event.keyCode: 数字类型，键盘按键的值，键值
document.onkeydown = function (ev) {
  var ev = ev || event;
  alert(ev.keyCode);
}
ctrlKey,altKey,shiftKey 布尔值
当一个事件发生的时候，如果ctrl||alt||shift是按下的状态，返回true，否则返回false

事件默认行为: 当一个事件发生的时候浏览器自己会默认做的事情
阻止方式: 当前这个行为是什么事件触发的，然后在这份事件处理函数中使用return false
//return false 阻止的是 obj.on事件名称=fn 所触发的默认行为
//addEventListener绑定的事件需要通过event下面的preventDefault()
oncontextmenu: 右键菜单事件

setCapture()  //设置全局捕获，这个元素会监听后续发生的所有事件，当有事件发生时，就会被当前设置了全局捕获的元素所触发
//ie: 有且有效  ff: 有，但没效果 chrome:没有
releaseCapture();

ie/chrome: onmousewheel
  event.wheelDelta //滚动方向，上:120，下:-120
ff: DOMMouseScroll //必须使用addEventListener
  event.detail  //上:-3,下:3
if (obj.addEventListener) {
  obj.addEventListener('DOMMouseScroll',fn,false);
}
```

<a name="日期"></a>
#### 日期

```js
time = new Date();
newTime = new Date(2015,10,1,21,30,30);       //设定指定日期
newTime = new Date('June 10,2015 12:12:12');  //设定指定日期
time.getFullYear();
time.getMonth();                     //0代表1月份
time.getDate();                      //Day
time.getDay();                       //WEEK
time.getHours();
time.getMinutes();
time.getSeconds();
time.getTime() / setTime();   //时间戳

天： Math.floor(t/86400)
时： Math.floor(t%86400/3600)
分： Math.floor(t%86400%3600/60)
秒： t%60
```

<a name="math"></a>
#### Math

```js
Math.ceil(num);           //向上取整
Math.floor(num);          //向下取整
Math.round(num);          //四舍五入
Math.random();            //随机数
Math.round(Math.random()*(y-x) + x);    //x ~ y随机值

Math.pow(a,b);    //a的b次方
Math.pow(a,1/b);  //a的开b次方
Math.sqrt(a);     //a的开方
```

<a name="cookie"></a>
#### Cookie

```js
1.不同的浏览器存放cookie的位置不同；
2.cookie的存储是以域名形式进行区分的；
3.cookie的数据可以设置名字
4.一个域名下存放的cookie的个数是有限制的，不同的浏览器存放的个数不同；
5.每个cookie的存储大小也是有限制的，不同的浏览器存放的大小也不一样；

document.cookie = 'username=Godi13';

当我们使用document.cookie来获取当前网站下的cookie的时候，得到的字符串形式的值，他包含了当前网站下的所有cookie，他会把所有的cookie通过分号+空格的形式串联起来

如果我们想长时间存放一个cookie，需要在设置这个cookie的时候同时给他设置一个过期的时间
cookie默认值是临时存储的，当浏览器关闭进程的时候自动销毁
document.cookie = '名称=值；expires=' + 字符串格式的时间；
var oDate = new Date();
oDate.setDate(oDate.getDate() + 5);
document.cookie = 'username=Godi13; expires=' + oDate.toGMTString();

内容最好编码存放，encodeURI('中文') / decodeURI('编码')
document.cookie = 'username=' + encodeURI('Godi13/n帅哥') + ';expires=' + oDate.toGMTString();

function setCookie(key, value, t) {
  var oDate = new Date();
  oDate.setDate( oDate.getDate() + t );
  document.cookie = key + '=' + value + ';expires=' + oDate.toGMTString();
}

function removeCookie(key) {
  setCookie(key,'',-1);
}

function getCookie(key) {
  var arr1 = document.cookie.split('; ');
  for (var i = 0; i < arr1.length; i++) {
    var arr2 = arr1[i].split('=');
    if (arr2[0] == key) {
      return decodeURI(arr2[1]);
    }
  }
}
```

#### AJAX

```js
var xhr = null;

//创建一个ajax对象：ie6以下 new ActiveXObject('Microsoft.XMLHTTP');

// if (window.XMLHttpRequest) {
//   xhr = new XMLHttpRequest();
// } else {
//   xhr = new ActiveXObject('Microsoft.XMLHTTP');
// }

try {
  xhr = new XMLHttpRequest();
} catch (e) {
  xhr = new ActiveXObject('Microsoft.XMLHTTP');
}

//在地址栏输入地址
xhr.open('post','url',true);
// open方法参数：打开方式'post','get'、url地址、是否异步
// 异步：阻塞模式，前面的代码不会影响后面代码的执行
// 同步：非阻塞模式，前面的代码会影响后面代码的执行
//get方式避免缓存方式： 在url？后面连接一个随机数或时间戳，例如 '2.get.php?username=Godi13&' + new Date().getTime()
//get方式传输中文需要用 encodeURI() 编码在传递
xhr.setRequestHeader('content-type','application/x-www-form-urlencoded');
//使用post方式的时候，需要设置发送请求头，申明数据的发送类型
//post没有缓存和编码的问题

//提交 发送请求
xhr.send('username=Godi13&age=27');
//post方法,数据要放在send()方法里面作为参数传递

//等待服务器返回内容
xhr.onreadystatechange = function () {
//on readystate change: 当 readyState 改变的时候触发

  if (xhr.readyState == 4) {
    //readyState: ajax工作状态
    //0 (初始化)还没有调用open方法
    //1 (载入)已调用send方法，正在发送请求
    //2 (载入完成)send方法完成，已收到全部响应内容
    //3 (解析)正在响应解析内容
    //4 (完成)响应内容解析完成，可以在客户端调用

    if (xhr.status == 200) {
    //status: 服务器状态,http状态码
      alert(xhr.responseText);
      //ajax请求的内容就被存放在responseText属性下面
      //responseText: 返回以文本形式存放的内容
      //responseXML: 返回XML形式的内容
    } else {
      alert('出错了，Err：' + xhr.status);
    }
  }

}
```

```js
try {
  //代码尝试执行这个块中的内容，如果有错误，则会执行catch{}，并且传入错误信息
  throw new Error('错了错了');   //手动抛错
} catch (e){
  alert(e);
}
```

表单：数据的提交
* action: 数据提交的地址，默认为当前页面；
* method: 数据提交的方式，默认为`get`方式；
  1. get: 把数据名称和数据用`=`连接，如果有多个的话，那么他会把多个数据组合用`&`进行连接，然后把数据放到`url?`后面传到指定页面
    * 由于使用url传递，信息可能会被缓存在浏览器地址栏里
    * 由于url长度限制，我们无法用get方式传递过多的数据
  2. post
  通过请求头发送，不会被缓存，理论上无传输大小限制
* enctype: 提交的数据的格式，默认为application/x-www-form-urlencoded；
`<form enctype="application/x-www-form-urlencoded"></form>`

```html
<form action="1.post.php" method="post">
  <input type="text" name="username" />
  <input type="text" name="age" />
  <input type="submit" value="提交" />
</form>
```

#### JSON

```js
var arr = [1,2,3];
JSON.stringify(arr); //把一个对象转换成对应字符串,typeof类型为字符串

var s1 = '[1,2,3]';
JSON.parse(s1);      //把字符串转成对应对象
var s2 = '{"left":100}';   //注意名称必须用双引号
var a2 = JSON.parse(s2);
alert(a2.left);      //如果s2的名称没用双引号包围，此处将报错
```

#### 正则表达式

正则：也叫做规则，让计算机能够读懂人类的规则，是用来操作字符串的

正则默认：
  * 正则匹配区分大小写，如果需要不区分大小写匹配，添加标示 `i`  
  * 正则匹配成功就会结束，不会继续匹配，如果需要全局匹配，添加标示 `g`

`\s`: 空格 `\S`: 非空格  
`\d`: 数字 `\D`: 非数字  
`\w`: 字符 `\W`: 非字符 (字符包括：字母、数字、下划线_)  
`\b`: 独立的部分 `\B`: 非独立的部分 (独立的部分包括：起始、结束、空格)  
`.`: 任意字符  

量词：匹配不确定的位数  
`+`: 至少出现一次 {1,}  
`?`: 0次或者1次 {0,1}  
`*`: 至少出现0次 {0,}  
`{min,max}`: 最少出现min次，最多出现max次  
`{min,}`: 最少出现min次  
`{num}`: 正好出现出现num次  
`|`: 或
`()`: 分组、子项 `$0` 父 `$1` 第一个    
`[]`: 字符类，一组相似的元素，整体代表一个字符，里面的字符都为或的关系    
`^`：如果 `^` 写在[]里面代表排除的意思, 如果放在正则最前面代表开始
`$`: 放在正则最后面代表结束
`\1`: 重复的第一个子项  例如: `/\w\w/`可以匹配任意字符如`c9`  `/(\w)\1/`只可以匹配两个一样的如`cc`  
`\2`: 重复的第二个子项  
(?=): 前向声明  (?!):反前向声明

```js
var re = /a/i;
var re = new RegExp('a','i');  //当正则需要传参的时候，一定要用全称写法，并且注意要双'\\'

test: 正则去匹配字符串，如果匹配成功就返回真，如果匹配失败就返回假
test的写法: 正则.test(字符串);

var str = 'abcdef';
var re = /b/;
alert(re.test(str));    //true

search: 正则去匹配字符串，如果匹配成功，就返回匹配成功的位置，如果匹配失败，则返回-1
search的写法: 字符串.search(正则);

var str = 'abcdef';
var re = /b/;
alert(str.search(re));  //1

match: 正则去匹配字符串，如果匹配成功，就返回匹配成功的数组，如果匹配失败，则返回null
match的写法: 字符串.match(正则);

var str = 'abc';
var re = /(a)(b)(c)/;
alert(str.match(re));   //[abc,a,b,c] 当match不加g时才能获得子项的集合

replace: 正则去匹配字符串，匹配成功的字符替换成新的字符串
replace的写法: 字符串.replace(正则,新的字符串);
replace第二个参数可以是字符串，也可以是回调函数，该函数的第一个参数就是匹配成功的字符
```


#### 面向对象编程

对象下面的变量：叫做对象的属性
对象下面的函数：叫做对象的方法
当new去调用一个函数，这个时候函数中的`this`就是创建出来的对象，而且函数的返回值直接就是`this`(隐式返回),new后面调用的函数叫做构造函数

基本类型：赋值的时候只是值的复制，比较时值相同就行  
对象类型：赋值不仅是值的复制，而且也是引用的传递，比较时值和引用都相同才行

原型：去改写对象下面公用的方法或属性，让公用的方法或属性在内存中存在一份（提高性能）  
prototype：要写在构造函数的下面  
普通方法的优先级要比原型的优先级要高  

```js
function 构造函数() {
  this.属性;
}
构造函数.原型.方法 = function() {};

var 对象1 = new 构造函数();
对象1.方法();
```

将普通方法变为面向对象方法：
* 普通方法变型
  * 尽量不要出现函数嵌套函数
  * 可以有全局变量
  * 把onload中不是赋值的语句放到单独函数中
* 改为面向对象  
  * 全局变量就是属性
  * 函数就是方法
  * onload中创建对象
  * 改this的指向问题：事件或者定时器容易出问题，尽量让面向对象中的`this`指向对象

##### 包装对象

基本类型都有自己对应的包装对象： `String` `Number` `Boolean`

```js
var str = 'hello';
str.charAt(0);  //基本类型会找到对应的包装对象类型，然后包装对象把所有的属性和方法给了基本类型，然后包装对象消失
```

##### 原型链

实例对象与原型之间的链接，叫做原型链，__proto__(隐式链接)   
原型链最外层：Object.prototype

##### 面向对象的一些属性和方法

* hasOwnProperty(): 看是不是对象自身下面的属性

```js
var arr = [];
arr.num = 10;
Array.prototype.num2 = 20;
alert( arr.hasOwnProperty('num') );   //true
alert( arr.hasOwnProperty('num2') );  //false
//在最外层的Object.prototype上
alert( a.hasOwnProperty == Object.prototype.hasOwnProperty ) //true
```

* constructor: 查看对象的构造函数

```js
function Fn() {};
//Fn.prototype.constructor = Fn; 每一个函数都会有，程序自动生成，可手动修改，但没有必要
//用字面量形式书写时需要手动添加constructor
//for in 找不到系统自带的属性，比如constructor
var a = new Fn();
alert( a.constructor );    //Fn
var arr = [];
alert( arr.constructor == Array );  //true
```

* instanceof: 运算符，对象与构造函数在原型链上是否有关系

```js
function Fn() {};
var a = new Fn();
alert( a instanceof Fn );  //true
alert( a instanceof Object );  //true
```

* toString(): 系统对象下面都是自带的，自己写的对象都是通过原型链找Object下面的

```js
var arr = [];
alert( Object.prototype.toString.call(arr) == '[object Array]' );  //true
//推荐使用该方法来判断变量类型，见下面这个特殊例子

window.onload = function () {
  var oF = document.createElement('iframe');
  document.body.appendChild(oF);
  var ifArray = window.iframe[0].Array;
  var arr = new ifArray();

  alert( arr.constructor == Array );   //false
  alert( arr instanceof Array );       //false
  alert( Object.prototype.toString.call(arr) == '[object Array]' );  //true
}
```

##### 继承

属性的继承：调用父类的构造函数 `call` 父类.call(this,arguments...);
方法的继承：
  * 拷贝继承：通用型，有new或无new的时候都可以
  * 类式继承：new构造函数
  * 原型继承：无new的对象

```js
//拷贝继承 for in
extend(子类.prototype, 父类.prototype);
function extend(obj1,obj2) {
  for (var attr in obj2) {
    obj1[attr] = obj2[attr];
  }
};

//类式继承
//属性和方法继承的时候，要分开继承
function Aaa() {     //父类
  this.name = 'Tom';
}
Aaa.prototype.showName = function () {
  alert(this.name);
}
function Bbb() {   //子类
  Aaa.call(this);  //这里继承属性
};

var F = function() {};   //只继承方法
F.prototype = Aaa.prototype;
Bbb.prototype = new Aaa();
Bbb.prototype.constructor = Bbb;  //修正指向问题

var b = new Bbb();
b.showName();     //Tom
alert(b.name);    //Tom

//原型继承
var a = {
  name : 'Tom'
};
var b = cloneObj(a);
alert( b.name );

function cloneObj(obj) {
  var F = function() {};
  F.prototype = obj;
  return new F();
}
```

##### 自定义事件

自定义事件主要是跟函数有关系，就是让函数能够具备事件的某些特性,需要主动触发









***
