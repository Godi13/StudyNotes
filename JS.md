<!-- MarkdownTOC -->

- [JS 相关总结](#js-相关总结)
  - [JavaScript 知识点](#javascript-知识点)
    - [变量提升](#变量提升)
    - [严格模式](#严格模式)
    - [闭包](#闭包)
    - [函数声明与表达式](#函数声明与表达式)
  - [JavaScript 常用指令](#javascript-常用指令)
    - [Brower](#brower)
    - [数据](#数据)
    - [文本](#文本)
    - [Array](#array)
    - [循环](#循环)
    - [DOM](#dom)
    - [事件](#事件)
    - [日期](#日期)
    - [Math](#math)

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

<a name="brower"></a>
#### Brower


```js
confirm();            //选择true/false
pormpt(str1,str2);    //用户

window.open([URL],[窗口名称],[参数字符串])；    //menubar  toolbar
window.open('http://www.imooc.com','_blank','width=600,height=200,top=100,left=0');
window.close();

setInterval(function,time);
clearInterval(setInterval());
setTimeout('function',interval);                   //延迟执行
clearTimeout(setTimeout());

window.history.back();
window.history.go(-1);                       //等同于back
window.history.forward();

navigator.appVersion;                        //浏览器版本

screen.width;                                //屏幕宽度
screen.availWidth;                           //屏幕可用宽度
screen.availHeight;                          //屏幕可用宽度

//浏览器窗口可视区域大小
window.innerHeight;
window.innerWidth;
var w=document.documentElement.clientWidth||document.body.clientWidth;
var h=document.documentElement.clientHeight||document.body.clientHeight;
//网页内用高度和宽度
var w=document.documentElement.scrollWidth||document.body.scrollWidth;
var h=document.documentElement.scrollHeight||document.body.scrollHeight;
//获取网页内容高度和宽度（包括滚动条等边线，会随窗口的显示大小改变）
//offsetHeight = clientHeight + 滚动条 + 边框
var w= document.documentElement.offsetWidth||document.body.offsetWidth;
var h= document.documentElement.offsetHeight||document.body.offsetHeight;

//获取当前网页地址并判断是否包含指定字符串
if (window.location.href.indexOf('字符串') != -1)
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
words.indexOf('o');              //4
words.lastIndexOf('o');          //7
words.substring(0,5);            //"Hello"
words.replace('Hello','Hi');     //"Hi World"

var words = 'Hello,world';
words.split(',');                //["Hello", "world"],可以加参数限定分割长度
var newWords = words.split(',');
newWords[0];                     //"Hello"

substring(num,num);              //提取两个指定下标之间的字符串
substr(num,num);                 //提取从第一个数开始指定数目的字符
```

<a name="array"></a>
#### Array

```js
//Array
var trackCD1 = [1,2];
trackCD1.push(3,4);              //4,返回长度值
trackCD1                         //[1,2,3,4]
trackCD1.pop();                  //4,删除最后一个元素，返回删除值
trackCD1.shift();                //1,删除第一个元素，返回删除值
delete trackCD1[1];              //[2, undefined × 1],不会影响数组的数量
trackCD1.splice(1);              //[undefined × 1],彻底删除
trackCD1;                        //[2]

trackCD2 = [3,4,5];
var tracks = trackCD1.concat(trackCD2);    //[2,3,4,5]

split()                           //分割
concat()                          //数组连接
join(分隔符)                        //指定分隔符连接数组
reverse()
slice(startnum,endnum)            //选择指定范围间元素
sort()                            //排序
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

.childNodes  .firstChild  .lastChild
.parentNode
.nextSibling                //兄弟节点，某个节点之后
.previousSibling            //兄弟节点，某个节点之前

.appendChild(newnode)       //插入节点
.insertBefore(newnode,node) //在node前插入newnode
.removeChild(node)
.replace(newnode,oldnode)

document.createElement()
document.createTextNode()

//属性
.nodeValue
object.innerHTML
object.style.backgroundColor
object.style.display = 'none'/'block'
object.className

```

<a name="事件"></a>
#### 事件

```js
触发onload事件，事件写在<body>标签内

//事件监听器
xxx.addEventListener('字符串（事件的类型或名称）','调用的函数'，'false（默认值，事件的捕获）')
```

<a name="日期"></a>
#### 日期

```js
time = new Date();
time.getFullYear();
time.getDate();                      //Day
time.getDay();                       //WEEK
time.getTime() / setTime();
```

<a name="math"></a>
#### Math

```js
Math.ceil(num);           //向上取整
Math.floor(num);          //向下取整
Math.round(num);          //四舍五入
Math.random();            //随机数
```

***
