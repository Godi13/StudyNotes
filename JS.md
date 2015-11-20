# JavaScript 常用指令

<kbd>ctrl</kbd>+<kbd>shift</kbd>+<kbd>j</kbd> chrome 中打开 console 快捷键

### 严格模式

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

### Brower

```js
confirm();            //选择true/false
pormpt(str1,str2);    //用户

window.open([URL],[窗口名称],[参数字符串])；    //menubar  toolbar
window.open('http://www.imooc.com','_blank','width=600,height=200,top=100,left=0');
window.close();

setInterval(function,time);
clearInterval(setInterval());
setTimeout(function,time);                   //延迟执行
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
```

### 数据

```js
//数据的类型
parseInt(650.55);                //650,可将字符串类型转成整型
parseFloat(650.55);              //650.55
```

### 文本

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

### Array

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
join(分隔符)                       //指定分隔符连接数组
reverse()
slice(startnum,endnum)            //选择指定范围间元素
sort()                            //排序
```

### 循环

```js
//switch
switch (expression) {
  case expression:
    alert(anything);
    break;
  default:
    alert(otherthing);
}

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

### DOM

```js
//DOM
document.getElementById('id');
document.getElementsByTagName('tag');

document.querySelectorAll('selector');
document.querySelector('selector');          //返回找到的第一个结果

getAttribute()
setAttribute(属性，值)

.childNodes
.firstChild
.lastChild
.parentNode
.nextSibling                //兄弟节点，某个节点之后
.previousSibling            //兄弟节点，某个节点之前

.appendChild(newnode)       //插入节点
.insertBefore(newnode,node) //在node前插入newnode
.removeChild(node)
.replace(newnode,oldnew)

document.createElement()
document.createTextNode()




//属性
object.innerHTML
object.style.backgroundColor
object.style.display = 'none'/'block'
object.className
```

### 事件

```js
触发onload事件，事件写在<body>标签内

//事件监听器
xxx.addEventListener('字符串（事件的类型或名称）','调用的函数'，'false（默认值，事件的捕获）')
```

### 日期

```js
time = new Date();
time.getFullYear();
time.getDate();                      //Day
time.getDay();                       //WEEK
time.getTime() / setTime();
```

### Math

```js
Math.ceil(num);           //向上取整
Math.floor(num);          //向下取整
Math.round(num);          //四舍五入
Math.random();            //随机数
```
