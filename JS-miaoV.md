```
document.title = 123;    //title后面可以直接接文字
document.body.innerHTML
style.cssText   //类似于innnerHTML，会替换之前的cssText
window.getComputedStyle(element[, pseudoElt])   //IE9以下版本会出现兼容性问题
Element.currentStyle.attr  //支持IE
```

```js
function getStyle( obj, attr ) {
  return obj.currentStyle ? obj.currentStyle[attr] : getComputedStyle( obj )[attr];
}
```

>函数改写成传递参数进来时，要注意将`.`写成`[]`形式；  
>background : url() red ……  //复合样式（不要获取）；  
>backgroundColor  //单一样式（不要用做判断）；  
>输入的属性值前不要有空格：会变成undefined；  
>不要获取未设置后的样式：会不兼容；

不要拿来做判断的几个点：
* 所有的相对路径
* 颜色值
* innerHTML

希望把某个元素移除视线的方法：

```css
1. display: none;       //显示为无，不占地方,在JS中如果要得到高度需要借助其他手段
2. visibility: hidden;  //隐藏，但是占地方,在JS中依然可以达到其高度
3. width / height
4. 透明度
5. left / top
6. 用白色的div覆盖
7. margin负值
......
```

```css
IE(styleFloat) 非IE(cssFloat)
可以用class回避兼容性问题
.left { float: left };
.right { float: right };

filter: alpha(opacity:90);  兼容IE
```

JS数据类型包括：数字（NAN）、字符串、布尔值、函数、对象（obj、[]、{}、null）、未定义（undefined）

隐式类型转换:
```  
+        变字符串  
- * / %  字符串变数字
++ --    字符串变数字
> <      ('10' > 9)   true  字符串转为数字比较
         ('10' > '9') false 按字符串编码排序比较
!        把右边的数据类型转为布尔值
```
NaN
* NaN 是数字类型
* 一旦写程序出现了：NaN 肯定进行了非法的运算操作
* NaN 是 false
* NaN 和自己都不相等

isNaN() 用于判断某些值是不是数字，如果参数能转换为数字则返回false

>从HTML中拿到的内容，数据类型都是字符串

重用代码：  
1. 尽量保证HTML代码一致，可以通过父级来选取子元素
2. 把核心主程序实现，用函数包起来
3. 把每组里不同的值找出来，通过传参实现

JS解析器工作方式：  
1. 预解析：var function 参数  
  * 所有的变量，在正式运行代码之前，都提前赋了一个值：未定义;
  * 所有的函数，在正式运行代码之前，都是整个函数块;
  * 预解析的过程中，遇到重名的只留一个，变量和函数重名了，只留下函数;

2. 逐行解读代码：  
  * 所有能改变值的都称为**表达式**，比如 = + - ! Number() 参数 ……;
  * 表达式可以修改预解析的值;
  * 函数调用：预解析，逐行解读代码

>从子集作用域返回父级作用域，称之为作用域链  
>不要在if或for等{}中定义函数，因为firefox浏览器无法进行预解析，会出现兼容性问题  
>for循环中的function中不要直接使用i，如需使用可以再嵌套一个for循环

真：非0数字、非空字符串、true、函数、能找到的元素、[]、{}  
假：0、NaN、空字符串''、false、不能找到的元素、null、undefined

>所有函数默认返回值为`undefined`  
>当函数的参数个数无法确定的时候使用`arguments`
