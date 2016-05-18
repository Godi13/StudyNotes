
JS中的顶层对象是window，NodeJS中的顶层对象是global，没有window对象

一个文件就是一个模块，每个模块都有自己的作用域，使用`var`声明一个变量，并不是全局的，而是属于当前模块下，定义全局范围内的变量如下例所示：

```js
var a = 1;
console.log(a);     //1
global.a = 100;
console.log(a);     //1
console.log(global.a);  //100
```

* 模块加载系统: require('模块');
* 模块加载机制: 相对路径/绝对路径
  1. 首先按照加载的模块的文件名进行查找；
  2. 如果没有找到，则在模块文件名后加上`.js`的后缀再进行查找
  3. 如果没有找到，则在模块文件名后加上`.json`的后缀再进行查找
  3. 如果没有找到，则在模块文件名后加上`.node`的后缀再进行查找

>加载相对路径前必须加入`./`,否则将加载node中的核心模块,或者是node_modules

* module: 保存提供和当前模块有关的一些信息
* `require`的返回值就是被加载模块中的`module.exports`
* `module.exports === exports`  为 `true`  
* `module.exports = [1,2,3]` 或 `exports = [1,2,3]` 都将断开`exports`与`module.exports`的指向关系


`__filename`: 返回当前模块文件被解析以后的绝对路径，该属性并非全局的，而是模块作用域下的  
`__dirname`: 返回当前模块文件所在目录被解析以后的绝对路径，该属性并非全局的，而是模块作用域下的

```js
默认情况下，输入流是关闭的，要监听处理输入流数据，首先要开启输入流
process.stdin.resume();
process.stdin.on('data',function(chunk) {
  console.log('用户输入了：' + chunk);
});

var a;
var b;
process.stdout.write('请输入a的值');
process.stdin.on('data',function(chunk) {
  if(!a) {
    a = Number(chunk);
    process.stdout.write('请输入b的值');
  } else {
    b = Number(chunk);
    process.stdout.write('结果是：' + (a + b));
  }
});
```

Buffer类：用于操作二进制数据流
new Buffer(size); size[Number]创建一个Buffer对象，并未这个对象分配一个大小，其长度将固定，不能改变
