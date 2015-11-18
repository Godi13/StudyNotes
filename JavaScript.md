# 索引

<!-- MarkdownTOC -->

- [JavaScript](#javascript)
    - [第3章 语法、关键保留字及变量](#第3章-语法、关键保留字及变量)
    - [第4章 数据类型](#第4章-数据类型)
        - [1. `typeof` 操作符](#1-typeof-操作符)
        - [2. `undefined` 类型](#2-undefined-类型)
        - [3. `Null` 类型](#3-null-类型)
        - [4. `Boolean` 类型](#4-boolean-类型)
        - [5. `Number` 类型](#5-number-类型)
        - [6. `String` 类型](#6-string-类型)
        - [7. `Object` 类型](#7-object-类型)
    - [第5章 运算符](#第5章-运算符)
        - [1. 一元运算符](#1-一元运算符)
        - [2. 位运算符](#2-位运算符)
        - [3. 布尔运算符](#3-布尔运算符)
        - [4. 乘性运算符](#4-乘性运算符)
        - [5. 加性运算符](#5-加性运算符)
        - [6. 关系运算符](#6-关系运算符)
        - [7. 相等运算符](#7-相等运算符)
        - [8. 条件运算符](#8-条件运算符)
        - [9. 赋值运算符](#9-赋值运算符)
        - [10. 逗号运算符](#10-逗号运算符)
    - [第6章 流程控制语句](#第6章-流程控制语句)
        - [ 1. `if` 语句](#-1-if-语句)
        - [2. `do-while` 语句](#2-do-while-语句)
        - [3. `while` 语句](#3-while-语句)
        - [4. `for` 语句](#4-for-语句)
        - [5. `for-in` 语句](#5-for-in-语句)
        - [6. `label` 语句](#6-label-语句)
        - [7. `break` 和 `continue` 语句](#7-break-和-continue-语句)
        - [8. `with` 语句](#8-with-语句)
        - [ 9. `switch` 语句](#-9-switch-语句)
    - [第7章 函数](#第7章-函数)
        - [1. 函数声明](#1-函数声明)
        - [2. `return` 返回值](#2-return-返回值)
        - [3. `arguments` 对象](#3-arguments-对象)
    - [第8章 对象和数组](#第8章-对象和数组)
        - [1. `Object` 类型](#1-object-类型)
        - [2. `Array` 类型](#2-array-类型)
        - [3. 对象中的方法](#3-对象中的方法)
    - [第9章 时间与日期](#第9章-时间与日期)
        - [1. `Date` 类型](#1-date-类型)
    - [第10章 正则表达式](#第10章-正则表达式)
        - [1. 什么是正则表达式](#1-什么是正则表达式)
        - [2. 创建正则表达式](#2-创建正则表达式)
        - [3. 获取控制](#3-获取控制)
        - [4. 常用的正则](#4-常用的正则)
    - [第11章 `Function` 类型](#第11章-function-类型)
        - [1. 函数的声明方式](#1-函数的声明方式)
        - [2. 作为值的函数](#2-作为值的函数)
        - [3. 函数内部属性](#3-函数内部属性)
        - [4. 函数属性和方法](#4-函数属性和方法)
    - [第12章 变量、作用域及内存](#第12章-变量、作用域及内存)
        - [1. 变量及作用域](#1-变量及作用域)
        - [2. 内存问题](#2-内存问题)
    - [第13章 基本包装类型](#第13章-基本包装类型)
        - [1. 基本包装类型概述](#1-基本包装类型概述)
        - [2. `Boolean` 类型](#2-boolean-类型)
        - [3. `Number` 类型](#3-number-类型)
        - [4. `String` 类型](#4-string-类型)
    - [第14章 内置对象](#第14章-内置对象)
        - [1. `Global` 对象](#1-global-对象)
        - [2. `Math`对象](#2-math对象)
    - [第15章 面向对象与原型](#第15章-面向对象与原型)
        - [1. 创建对象](#1-创建对象)
        - [2. 原型](#2-原型)
        - [3. 继承](#3-继承)
    - [第16章 匿名函数和闭包](#第16章-匿名函数和闭包)
        - [1. 匿名函数](#1-匿名函数)
        - [2. 闭包](#2-闭包)
        - [3. 内存泄露](#3-内存泄露)
    - [第17章 BOM](#第17章-bom)
        - [1. `window`对象](#1-window对象)
        - [2. `location`对象](#2-location对象)
        - [3. `history`对象](#3-history对象)
    - [第18章 浏览器检测](#第18章-浏览器检测)
        - [1. `navigator`对象](#1-navigator对象)
        - [2. 客户端检测](#2-客户端检测)
    - [第29章 `Cookie`与存储](#第29章-cookie与存储)

<!-- /MarkdownTOC -->

***

<a name="javascript"></a>
# JavaScript

[李炎恢JS视频](http://pan.baidu.com/share/home?uk=4278436023#category/type=0)  
[树形图笔记](https://coggle.it/diagram/VjR7Lm_Q0gtu4Qd0)

***

<a name="第3章-语法、关键保留字及变量"></a>
## 第3章 语法、关键保留字及变量

* 区分大小写： `text` 和 `Text` 是两种不同的标识符
* 标识符组成开头： a（字母）、_ 、 $
* 其他组成： a（字母）、_ 、 $、数字
* 不能把关键字、保留字，如`true` `false` `null`作为标识符
* 关键字 程序中已经开始使用的字符，如`var`

|字面量|示例|
|---|---|
|数字字面量|100|
|字符串字面量|'李'|
|布尔值字面量|`false` `true`|
|正则表达式|`/js/gi`|
|对象字面量|`null`|
|对象字面量表达式|{x:1,y:2}|
|数组字面量表达式|[1,2,3,4,5]|

变量

* `var box` 声明变量
* `var box = 100；` 声明变量并初始化
* `alert(box)` 以弹窗的方式输出`box`的值
* 不需要重复的使用`var`声明一个变量，只不过是一个赋值操作，并不会报错，但没必要这么做，如下：

```js
    var box = 100           var box = 100；
    var box ='LEE'          box = 'LEE';
```

***

<a name="第4章-数据类型"></a>
## 第4章 数据类型

ECMAScript 中有`5`种简单数据类型（也称为基本数据类型）：`Undefined`、`Null`、`Boolean`、`Number`、`String`  
`1`种复杂数据类型——`Object`

<a name="1-typeof-操作符"></a>
#### 1. `typeof` 操作符

`typeof` 操作符是用来检测变量的数据类型。对于值或者变量使用`typeof`运算符会返回如下字符串:

|字符串|描述|
|---|:---:|
| `undefined` |未定义       |
| `boolean`   |布尔值       |
| `string`    |字符串       |
| `number`    |数值        |
| `object`    |对象或`null`|
| `function`  |函数        |


```js
var box；
alert(typeof box);
//box是 Undefined 类型，值是 undefined ，类型返回的字符串是 undefined

var box = true；
alert(typeof box);
//box是 Boolean 类型，值是 true ，类型返回的字符串是 boolean

var box = 'LEE';
alert(typeof box);
//box是 String 类型，值是 'LEE' ，类型返回的字符串是 string

var box = 250;
alert(typeof box);
//box是 Number 类型，值是 250 ，类型返回的字符串是 number

var box = {};
alert(typeof box);
//box是 Object 类型，值是 [object Object] ，类型返回的字符串是 object

var box = new Object();
alert(box);
//box是 Object 类型，值是 [object Object] ，类型返回的字符串是 object

var box = null;
alert(typeof box);
//box是 Null 类型，值是 null ，类型返回的字符串是 object

function box() {

}
alert(typeof box);
//box是 Function 类型，值是 function box() {} ，类型返回的字符串是 function

alert(typeof new Object());
//可以直接使用字面量
```

>空的对象：表示这个对象创建了，里面没有东西  
空对象：表示没有创建，就是一个`null`

<a name="2-undefined-类型"></a>
#### 2. `undefined` 类型

在使用 `var` 声明变量但未对其加以初始化时,
这个变量的值就是 `undefined`

>我们没有必要显式的给一个变量赋值为`undefined`，因为没有赋值的变量会隐式的（自动的）赋值为`undefined`；而`undefined`主要的目的是为了用于比较，_ECMAScript_第3版之前并没有引入这个值，引入之后为了正式区分空对象与未经初始化的变量。  
未初始化的变量与根本不存在的变量（为声明的变量）也是不一样的。

```js
var box;
alert(age);    //age is not defined
alert(typeof box);
alert(typeof age);
```
`typeof box` `typeof age` 都返回的 `undefined`。 从逻辑上思考，他们的值，一个是 `undefined`，一个报错；他们的类型，却都是`undefined`。所以，在定义变量的时候，尽可能的不要只声明，不赋值。

<a name="3-null-类型"></a>
#### 3. `Null` 类型

`undefined` 值是派生自 `null` 值的,因此 ECMA-262 规定对它们的相等性测试要返回 `true` :

    alert(null == undefined);    //true

只要意在保存对象的变量还没有真正保存对象,就应该明确地让该变量保存 `null` 值。这样做不仅可以
体现 `null` 作为空对象指针的惯例,而且也有助于进一步区分 `null` 和 `undefined`

```js
var box = null；
//这个表示，你还没有创建对象，但先声明了对象引用而必须初始化的结果
//还没来得及创建对象，先声明一个对象的变量放在那边，默认初始化为 null

var box = null ;
box = {
  1:1
};
alert(box);

var box = '';
//创建一个字符串变量，一开始不知道初始化什么字符串，可以先给一个空字符串初始化

var box = 0;
//数值初始化，一般用0

var box = false；
//布尔值初始化，一般一开始用 false 或者 true

alert(undefined == null);   //true
alert(undefined === null);  //false
alert(typeof undefined == typeof null);  //false
```

<a name="4-boolean-类型"></a>
#### 4. `Boolean` 类型

`Boolean` 类型是 ECMAScript 中使用得最多的一种类型,该类型只有两个字面值: `true` 和 `false`  
这两个值与数字值不是一回事,因此 `true` 不一定等于 `1`,而 `false` 也不一定等于 `0`  
要将一个值转换为其对应的 `Boolean` 值,可以调用转型函数 `Boolean()` ,如下例所示:

    var message = "Hello world!";
    var messageAsBoolean = Boolean(message);

```js
var box = true;
alert(typeof box == typeof 1);    //true
alert(typeof box === typeof 1);    //false

var box = 'LEE';
alert(Boolean(box));    //true
var box = '';
alert(Boolean(box));    //false
//上面的 Boolean 是一种显示转换，属于强制性转换。

//下面为 隐式转换，在 if 条件语句里面的条件判断，就存在隐式转换
var box = '';
if(box){        //条件语句里的()里必须是布尔值，true或者false
  alert('true');
}else{
  alert('false');
}
```

转换成`Boolean`类型的规则

|数据类型|转换为true的值|转换为false的值|
|----|-----|-----|
|Boolean|true|false|
|String|任何非空字符串|空字符串|
|Number|任何非零数字值（包括无穷大）|0 和 NaN|
|Object|任何对象|null|
|Undefined| |undefined|

<a name="5-number-类型"></a>
#### 5. `Number` 类型

>鉴于 JavaScript 中保存数值的方式,可以保存正零(+0)和负零(-0)，正零和负零被认为相等

除了以十进制表示外,整数还可以通过八进制(以 8 为基数)或十六进制(以 16 为基数)的字面值来表示。其中,八进制字面值的第一位必须是零(0),然后是八进制数字序列(0~7)。如果字面值中的数值超出了范围,那么前导零将被忽略,后面的数值将被当作十进制数值解析。请看下面的例子:

    var octalNum1 = 070;     // 八进制的 56
    var octalNum2 = 079;     // 无效的八进制数值——解析为 79
    var octalNum3 = 08;      // 无效的八进制数值——解析为 8

>八进制字面量在严格模式下是无效的,会导致支持的 JavaScript 引擎抛出错误。

六进制字面值的前两位必须是 0x,后跟任何十六进制数字(0~9 及 A~F)。其中,字母 A~F 可以大写,也可以小写。如下面的例子所示:

    var hexNum1 = 0xA;       // 十六进制的 10
    var hexNum2 = 0x1f;      // 十六进制的 31

>在进行算术计算时,所有以八进制和十六进制表示的数值最终都将被转换成十进制数值。

##### 1. 浮点数值
浮点类型，就是该数值中必须包含一个小数点，并且小数点后面必须至少有一位数字。

由于保存浮点数值需要的内存空间是保存整数值的两倍,因此 _ECMAScript_ 会不失时机地将浮点数值转换为整数值。显然,如果小数点后面没有跟任何数字,那么这个数值就可以作为整数值来保存。同样地,如果浮点数值本身表示的就是一个整数(如 1.0),那么该值也会被转换为整数,如下面的例子所示:

    var floatNum1 = 1.;      // 小数点后面没有数字——解析为 1，自动转换为整型
    var floatNum2 = 10.0;    // 整数——解析为 10

>永远不要测试某个特定的浮点数值

##### 2. 数值范围

```js
var box = 4.12e3;         //科学计数法，即 4120
var box = 0.00000000412   //即 4.12e-9
```

虽然浮点数值的最高精度是17位小数，但算术运算中可能会不精确。由于这个因素，做判断的时候一定要考虑到这个问题（比如使用整型判断），如下：

```js
alert(0.1+0.2);           //0.30000000000000004
```

_ECMAScript_ 能够表示的最小数值保存在 `Number.MIN_VALUE` 中——在大多数浏览器中,这个值是 `5e-324`；能够表示的最大数值保存在 `Number.MAX_VALUE`中——在大多数浏览器中,这个值是 `1.7976931348623157e+308`。

```js
alert(Number.MIN_VALUE);    //最小值，5e-324
alert(Number.MAX_VALUE);    //最大值，1.7976931348623157e+308
```

如果某次计算的结果得到了一个超出 JavaScript 数值范围的值,那么这个数值将被自动转换成特殊的 `Infinity` 值。具体来说,如果这个数值是负数,则会被转换成 `-Infinity` (负无穷),如果这个数值是正数,则会被转换成 `Infinity` (正无穷)。

访问 `Number.NEGATIVE_INFINITY` 和 `Number.POSITIVE_INFINITY` 也可以得到负和正 `Infinity` 的值。可以想见,这两个属性中分别保存着 `-Infinity` 和 `Infinity` 。

```js
alert(Number.POSITIVE_INFINITY);    //Infinity（正无穷）
alert(Number.NEGATIVE_INFINITY);    //-Infinity（负无穷）
```

如果某次计算返回了正或负的 Infinity 值,那么该值将无法继续参与下一次的计算,因为 Infinity 不是能够参与计算的数值。要想确定一个数值是不是有穷的(换句话说,是不是位于最小和最大的数值之间),可以使用 `isFinite()` 函数。这个函数在参数位于最小与最大数值之间时会返回 `true` ,如下面的例子所示:

```js
var result = Number.MAX_VALUE + Number.MAX_VALUE;
alert(isFinite(result));         //false，超过范围
```

##### 3. _NaN_ (Not a Number)

`NaN` ,即非数值(Not a Number)是一个特殊的数值,这个数值用于表示一个本来要返回数值的操作数未返回数值的情况(这样就不会抛出错误了),`NaN` 本身有两个非同寻常的特点：

* 任何涉及 `NaN` 的操作（例如 `NaN/10`）都会返回 `NaN`，这个特点在多步计算中有可能导致问题
* `NaN` 与任何值都不相等，包括 `NaN` 本身，例如：`alert(NaN == NaN); //false `

```js
var box = 0 / 0;         //NaN
var box = 12 / 0;        //Infinity
var box = 12 / 0 * 0;    //NaN

alert(Number.NaN);       //NaN
```

>实际上只有 `0` 除以 `0` 才会返回 `NaN`,正数除以 `0` 返回 `Infinity`,负数除以 `0` 返回`-Infinity。`

针对 `NaN` 的这两个特点, _ECMAScript_ 定义了 `isNaN()` 函数。这个函数接受一个参数,该参数可以是任何类型,而函数会帮我们确定这个参数是否 “__不是数值__”。 `isNaN()` 在接收到一个值之后,会尝试将这个值转换为数值。某些不是数值的值会直接转换为数值,例如字符串 `"10"` 或 `Boolean` 值。而任何不能被转换为数值的值都会导致这个函数返回 `true` 。请看下面的例子:

```js
alert(isNaN(NaN));      //true
alert(isNaN(10));       //false（10是一个数值）
alert(isNaN("10"));     //false（可以被转换成数值10）
alert(isNaN("blue"));   //true（不能转换成数值）
alert(isNaN(true));     //false（可以被转换成数值1）
```

尽管有点儿不可思议,但 `isNaN()` 确实也适用于对象。在基于对象调用 `isNaN()` 函数时,会首先调用对象的 `valueOf()` 方法,然后确定该方法返回的值是否可以转换为数值。如果不能,则基于这个返回值再调用 `toString()` 方法,再测试返回值。而这个过程也是 _ECMAScript_ 中内置函数和运算符的一般执行流程。

```js
var box = {
    toString:function(){
        return 'LEE';
    }
};
alert(isNaN(box));
//如果对象的toString方法能够返回数值，那么就不是NaN
```

##### 4. 数值转换

有 `3` 个函数可以把非数值转换为数值: `Number()` 、 `parseInt()` 和 `parseFloat()`

###### `Number()`函数的转换规则如下：
`Number()`函数是转型函数，可以用于任何__数据类型__

* 如果是 `Boolean` 值, `true` 和 `false` 将分别被转换为 `1` 和 `0`
* 如果是数字值,只是简单的传入和返回
* 如果是 `null` 值,返回 `0`
* 如果是 `undefined` ,返回 `NaN`
* 如果是字符串,遵循下列规则:
    * 如果字符串中只包含数字(包括前面带正号或负号的情况),则将其转换为十进制数值,即 "1"会变成 1, "123" 会变成 123,而 "011" 会变成 11(__注意:__前导的零被忽略了);
    * 如果字符串中包含有效的浮点格式,如 "1.1" ,则将其转换为对应的浮点数值(同样,也会忽略前导零);
    * 如果字符串中包含有效的十六进制格式,例如 "0xf", 则将其转换为相同大小的十进制整数值;
    * 如果字符串是空的(不包含任何字符),则将其转换为 `0`;
    * 如果字符串中包含除上述格式之外的字符,则将其转换为 `NaN`
* 如果是对象,则调用对象的 `valueOf()` 方法,然后依照前面的规则转换返回的值。如果转换的结果是 `NaN` ,则调用对象的 `toString()` 方法,后再次依照前面的规则转换返回的字符
串值

```js
alert(Number(true));        //1，Boolean类型的true和false分别转换成1和0
alert(Number(25));          //25，数值型直接返回
alert(Number(null));        //0，空对象返回0
alert(Number(undefined));   //NaN，undefined返回NaN
```

>一元加运算符的操作与 `Number()` 函数相同

###### `parseInt()` 函数的转换规则如下：
`parseInt()`只能转换字符串  
函数在转换字符串时,更多的是看其是否符合数值模式。它会忽略字符串前面的空格,直至找到第一个非空格字符。

* 如果第一个字符不是数字字符或者负号, `parseInt()` 就会返回 `NaN` ;也就是说,用 `parseInt()` 转换空字符串 `""` 会返回 `NaN` ( `Number()` 对空字符返回 `0`)。
* 如果第一个字符是数字字符, `parseInt()` 会继续解析第二个字符,直到解析完所有后续字符或者遇到了一个非数字字符。例如, "1234blue" 会被转换为 1234,因为 "blue" 会被完全忽略。类似地, "22.5"
会被转换为 22,因为小数点并不是有效的数字字符。
* 如果字符串中的第一个字符是数字字符, `parseInt()` 也能够识别出各种整数格式(即十进制、八进制和十六进制数)。也就是说,如果字符串以 "0x" 开头且后跟数字字符,就会将其当作一个十六进制整数;如果字符串以 "0" 开头且后跟数字字符,则会将其当作一个八进制数来解析。

```js
alert(parseInt('456LEE'));        //456，会返回整数部分
alert(parseInt('LEE456LEE'));     //NaN，如果第一个不是数值，就返回NaN
alert(parseInt('12LEE56LEE'));    //12，从第一数值开始取，到最后一个连续数值结束
alert(parseInt('56.12'));         //56，小数点不是数值，会被去掉
alert(parseInt(''));              //NaN，空返回NaN

//parseInt() 除了能够识别十进制数值，也可以识别八进制和十六进制
alert(parseInt('0xA'));           //10，十六进制
alert(parseInt('070'));           //56，八进制
alert(parseInt('0xALEE'));        //100，十六进制，LEE被自动过滤掉

//ECMAScript 为 parseInt() 提供了第二个参数，用于解决各种进制的转换
alert(parseInt('0xAF'));          //175，十六进制
alert(parseInt('AF',16));         //175，第二参数指定十六进制，可以去掉 0x 前导
alert(parseInt('AF'));            //NaN
alert(parseInt('101010101',2));   //314，二进制转换
alert(parseInt('70',8));          //56，八进制转换
```

>在 ECMAScript 3 JavaScript 引擎中, "070" 被当成八进制字面量,因此转换后的值是十进制的 56。而在 ECMAScript 5 JavaScript 引擎中, `parseInt()` 已经不具有解析八进制值的能力,因此前导的零会被认为无效,从而将这个值当成 "70" ,结果就得到十进制的 70。在 ECMAScript 5 中,即使是在非严格模式下也会如此。  
为了消除在使用 `parseInt()` 函数时可能导致的上述困惑,可以为这个函数提供第二个参数:转换时使用的基数(即多少进制)。如果知道要解析的值是十六进制格式的字符串,那么指定基数 16 作为第二个参数,可以保证得到正确的结果，例如：`parseInt("0xAF,16");` `parseInt("AF,16");`  
不指定基数意味着让 parseInt() 决定如何解析输入的字符串,因此为了避免错误的解析,建议无论在什么情况下都明确指定基数。

###### `parseFloat()` 函数的转换规则如下：
* 与 `parseInt()` 函数类似, `parseFloat()` 也是从第一个字符(位置 `0`)开始解析每个字符。而且也是一直解析到字符串末尾,或者解析到遇见一个无效的浮点数字字符为止。也就是说,字符串中的第一个小数点是有效的,而第二个小数点就是无效的了,因此它后面的字符串将被忽略。举例来说,"22.34.5" 将会被转换为 22.34
* 除了第一个小数点有效之外, `parseFloat()` 与 `parseInt()` 的第二个区别在于它始终都会忽略前导的零。 `parseFloat()` 可以识别前面讨论过的所有浮点数值格式,也包括十进制整数格式。但十六进制格式的字符串则始终会被转换成 `0`。由于 `parseFloat()` 只解析十进制值,因此它没有用第二个参数指定基数的用法。
* 最后还要注意一点:如果字符串包含的是一个可解析为整数的数(没有小数点,或者小数点后都是零), `parseFloat()` 会返回整数。

```js
alert(parseFloat('123LEE'));       //123，去掉不是别的部分
alert(parseFloat('0xA'));          //0，不认十六进制
alert(parseFloat('123.4.5'));      //123.4，只认一个小数点
alert(parseFloat('0123.400'));     //123.4，去掉前后导
alert(parseFloat('1.234e7'));      //12340000，把科学技术法转成普通数值
```

<a name="6-string-类型"></a>
#### 6. `String` 类型

`String` 类型用于表示由零或多个 16 位 `Unicode` 字符组成的字符序列,即字符串。字符串可以由双引号(")或单引号(')表示

##### 1. 字符字面量

`String` 数据类型包含一些特殊的字符字面量,也叫转义序列,用于表示非打印字符,或者具有其他用途的字符。这些字符字面量如下表所示:

|字面量|含义|
|-----|---|
|\n|换行|
|\t|制表|
|\b|空格|
|\r|回车|
|\f|进纸|
|\\\|斜杠|
|\'|单引号，在用单引号表示的字符串中使用。例如: 'He said, \'hey.\''|
|\"|双引号，在用双引号表示的字符串中使用。例如: "He said, \"hey.\""|
|\xnn|以十六进制代码 nn 表示的一个字符(其中 n 为0~F)。例如, \x41 表示 "A"|
|\unnn|以十六进制代码 nnnn 表示的一个Unicode字符(其中 n 为0~F)，例如, \u03a3 表示希腊字符Σ|

>这些字符字面量可以出现在字符串中的任意位置,而且也将被作为__*`1`*__个字符来解析

##### 2. 字符串的特点

_ECMAScript_ 中的字符串是 __不可变的__,也就是说,字符串一旦创建,它们的值就不能改变。要改变某个变量保存的字符串,首先要销毁原来的字符串,然后再用另一个包含新值的字符串填充该变量

##### 3. 转换字符串

数值、布尔值、对象和字符串值(没错,每个字符串也都有一个 `toString()` 方法,该方法返回字符串的一个副本)都有 `toString()` 方法。但 `null` 和 `undefined` 值没有这个方法。  
在调用数值的 `toString()` 方法时,可以传递一个参数: _输出数值的基数_。默认情况下, `toString()` 方法以十进制格式返回数值的字符串表示。而通过传递基数, `toString()` 可以输出以二进制、八进制、十六进制,乃至其他任意有效进制格式表示的字符串值。

```js
var num = 10;
alert(num.toString());        //"10"，默认输出
alert(num.toString(2));       //"1010"，二进制输出
alert(num.toString(8));       //"12"，八进制输出
alert(num.toString(10));      //"10"，十进制输出
alert(num.toString(16));      //"a"，十六进制输出
```

在不知道要转换的值是不是 `null` 或 `undefined` 的情况下,还可以使用转型函数 `String()` ,这个函数能够将任何类型的值转换为字符串。 `String()` 函数遵循下列转换规则:

* 如果值有 `toString()` 方法,则调用该方法(没有参数)并返回相应的结果
* 如果值是 `null` ,则返回 `"null"`
* 如果值是 `undefined` ,则返回 `"undefined"`

下面转换了 4 个值:数值、布尔值、 null 和 undefined 。数值和布尔值的转换结果与调用 `toString()` 方法得到的结果相同。因为 null 和 undefined 没有 `toString()` 方法,所以 `String()` 函数就返回了这两个值的字面量。

```js
var value1 = 10;
alert(String(value1));      //"10"

var value2 = true;
alert(String(value2));      //"true"

var value3 = null;
alert(String(value3));      //"null"

var value4;
alert(String(value4));      //"undefined"
```

<a name="7-object-类型"></a>
#### 7. `Object` 类型

```js
var box = {};          //对象字面量的创建方法
alert(box);            //[object Object]
alert(typeof box);     //object
```

_ECMAScript_ 中的对象其实就是一组数据和功能的集合。对象可以通过执行 `new` 运算符后跟要创建的对象类型的名称来创建。而创建 `Object` 类型的实例并为其添加属性和(或)方法,就可以创建自定义对象。

```js
var box = new Object();

var box = new Object(2),
    age = 100;
alert(box);               //2
alert(typeof box);        //object
alert(box + age);         //102
```

`Object` 的每个实例都具有下列属性和方法：

* `constructor` :保存着用于创建当前对象的函数。对于前面的例子而言,构造函数(`constructor`) 就是 `Object()`
* `hasOwnProperty(propertyName)` :用于检查给定的属性在当前对象实例中(而不是在实例的原型中)是否存在。其中,作为参数的属性名( `propertyName` )必须以字符串形式指定(例如: `o.hasOwnProperty("name")` )
* `isPrototypeOf(object)` :用于检查传入的对象是否是传入对象的原型(第 5 章将讨论原型)
* `propertyIsEnumerable(propertyName)` :用于检查给定的属性是否能够使用 `for-in` 语句来枚举。与 `hasOwnProperty()` 方法一样,作为参数的属性名必须以字符串形式指定
* `toLocaleString()` :返回对象的字符串表示,该字符串与执行环境的地区对应
* `toString()` :返回对象的字符串表示
* `valueOf()` :返回对象的字符串、数值或布尔值表示。通常与 `toString()` 方法的返回值相同

```js
var box = new Number();   //创键一个数值对象
alert(box);               //0
alert(typeof box);        //object类型
```

***

<a name="第5章-运算符"></a>
## 第5章 运算符

_ECMA-262_ 描述了一组用于操作数据值的运算符,包括算术运算符(如加号和减号)、位运算符、关系运算符和相等运算符。_ECMAScript_ 运算符的与众不同之处在于,它们能够适用于很多值,例如字符串、数字值、布尔值,甚至对象。不过,在应用于对象时, 相应的运算符通常都会调用对象的 `valueOf()` 和(或) `toString()` 方法,以便取得可以操作的值。

>单一的字面量和组合字面量的运算符都可称为表达式

<a name="1-一元运算符"></a>
#### 1. 一元运算符

只能操作一个值的运算符叫做一元运算符。

##### 1.递增和递减运算符
递增`++`和递减`--`运算符各有两个版本：__前置型__ 和 __后置型__。

不仅适用于整数,还可以用于字符串、布尔值、浮点数值和对象。在应用于不同的值时,递增和递减运算符遵循下列规则：

* 在应用于一个包含有效数字字符的字符串时,先将其转换为数字值,再执行加减 1 的操作。字符串变量变成数值变量
* 在应用于一个不包含有效数字字符的字符串时,将变量的值设置为 `NaN` 字符串变量变成数值变量
* 在应用于布尔值 `false` 时,先将其转换为 0 再执行加减 1 的操作。布尔值变量变成数值变量。
* 在应用于布尔值 `true` 时,先将其转换为 1 再执行加减 1 的操作。布尔值变量变成数值变量。
* 在应用于浮点数值时,执行加减 1 的操作。
* 在应用于对象时,先调用对象的 `valueOf()`  方法以取得一个可供操作的值。然后对该值应用前述规则。如果结果是 `NaN` ,则在调用 `toString()` 方法后再应用前述规则。对象变量变成数值变量。

```js
var box = '89';
box++;              //90,++对数值字符串，有一个隐含的转型功能
alert(typeof box);

var box = 'ab'; box++;    //NaN,字符串包含非数值转成NaN
var box = false; box++;   //1,false转成数值是0，累加就是1
var box = 2.3; box++;     //3.3,直接加1

var box = {
    toString : function() {
        return 1;
    }
};      box++;            //2,不设置 toString 或 valueOf 即为 NaN
```

<a name="2-一元加和减运算符"></a>
##### 2. 一元加和减运算符
在对非数值应用一元加`+`运算符时,该运算符会像 `Number()` 转型函数一样对这个值执行转换。换句话说,布尔值 `false` 和 `true` 将被转换为 `0` 和 `1`,字符串值会被按照一组特殊的规则进行解析,而对象是先调用它们的 `valueOf()` 和(或) `toString()` 方法,再转换得到的值。  
一元减`-`运算符主要用于表示负数,例如将 `1` 转换成 `-1`。而当应用于非数值时,一元减运算符遵循与一元加运算符相同的规则,最后再将得到的数值转换为负数。

>一元加和减运算符主要用于基本的算术运算,也可以用于转换数据类型。

```js
var box = '89';          //string
alert(typeof +box);      //number， + 自动转型

var box = 'ab'; +box;    //NaN，字符串包含非数值转成NaN
var box = false; +box;   //0, 布尔值转换成相应数值
var box = 2.3; +box;     //2.3, 没有变化

var box = {
    toString : function() {
        return 1;
    }
};           +box;       //1，不设置 toString 或 valueOf 即为 NaN
```

<a name="2-位运算符"></a>
#### 2. 位运算符

位运算符用于在最基本的层次上,即按内存中表示数值的位来操作数值。  
ECMAScript 中的所有数值都以 IEEE-754 64 位格式存储,但位运算符并不直接操作 64 位的值。而是先将 64 位的值转换成 32 位的整数,然后执行操作,最后再将结果转换回 64 位。对于开发人员来说,由于 64 位存储格式是透明的,因此整个过程就像是只存在 32 位的整数一样。

负数同样以二进制码存储,但使用的格式是二进制补码。计算一个数值的二进制补码,需要经过下列 3 个步骤:

    1. 求这个数值绝对值的二进制码
    2. 求二进制反码，即将 0 替换为 1 ，将 1 替换为 0
    3. 得到的二进制反码加 1

>默认情况下,ECMAScript 中的所有整数都是有符号整数。不过,当然也存在无符号整数。对于无符号整数来说,第 32 位不再表示符号,因为无符号整数只能是正数。而且,无符号整数的值可以更大,因为多出的一位不再表示符号,可以用来表示数值。

在 _ECMAScript_ 中,当对数值应用位运算符时,后台会发生如下转换过程:64 位的数值被转换成 32位数值,然后执行位操作,最后再将 32 位的结果转换回 64 位数值。这样,表面上看起来就好像是在操作 32 位数值,就跟在其他语言中以类似方式执行二进制操作一样。但这个转换过程也导致了一个严重的副效应,即在对特殊的 `NaN` 和 `Infinity` 值应用位操作时,这两个值都会被当成 0 来处理。  
如果对非数值应用位运算符,会先使用 `Number()` 函数将该值转换为一个数值(自动完成),然后再应用位操作。得到的结果将是一个数值。

##### 1. 按位非（NOT <kbd>~</kbd>）
按位非运算符由一个波浪线 <kbd>~</kbd> 表示,执行按位非的结果就是返回数值的反码。  
按位非操作的本质:__操作数的负值减 1__。  
由于按位非是在数值表示的最底层执行操作,因此速度更快。

##### 2. 按位与（AND <kbd>&</kbd>）
按位与运算符由一个和号字符 <kbd>&</kbd> 表示,它有两个运算符数。从本质上讲,按位与操作就是将两个数值的每一位对齐,然后根据下表中的规则,对相同位置上的两个数执行 AND 操作:

|第一个数值的位|第二个数值的位|结果|
|:-:|:-:|:-:|
|1|1|1|
|1|0|0|
|0|1|0|
|0|0|0|

##### 3. 按位或（OR <kbd>|</kbd>）
按位或运算符由一个竖线符号 <kbd>|</kbd> 表示,它有两个运算符数。按位或操作遵循下面这个真值表：

|第一个数值的位|第二个数值的位|结果|
|:-:|:-:|:-:|
|1|1|1|
|1|0|1|
|0|1|1|
|0|0|0|

##### 4. 按位异或（XOR <kbd>^</kbd>）
按位异或运算符由一个插入符号 <kbd>^</kbd> 表示,也有两个操作数。以下是按位异或的真值表:

|第一个数值的位|第二个数值的位|结果|
|:-:|:-:|:-:|
|1|1|0|
|1|0|1|
|0|1|1|
|0|0|0|

##### 5. 左移
左移运算符由两个小于号 <kbd><<</kbd> 表示,这个运算符会将数值的所有位向左移动指定的位数。
>左移不会影响操作数的符号位

##### 6. 有符号右移
有符号的右移运算符由两个大于号 <kbd>>></kbd> 表示,这个运算符会将数值向右移动,但保留符号位(即正负号标记)。
>在移位过程中,原数值中也会出现空位。只不过这次的空位出现在原数值的左侧、符号位的右侧。而此时 ECMAScript 会用符号位的值来填充所有空位,以便得到一个完整的值。

##### 7. 无符号右移
无符号右移运算符由 3 个大于号 <kbd>>>></kbd> 表示,这个运算符会将数值的所有 32 位都向右移动。

* 无符号右移是以 0 来填充空位
* 无符号右移运算符会把负数的二进制码当成正数的二进制码。而且,由于负数以其绝对值的二进制补码形式表示,因此就会导致无符号右移后的结果非常之大

<a name="3-布尔运算符"></a>
#### 3. 布尔运算符

布尔运算符一共有 3 个:`非(NOT)` `与(AND)` `或(OR)`

##### 1. 逻辑非(NOT) <kbd>!</kbd>
逻辑非运算符由一个叹号 <kbd>!</kbd> 表示,可以应用于 ECMAScript 中的任何值。逻辑非运算符首先会将它的操作数转换为一个布尔值,然后再
对其求反。逻辑非运算符遵循下列规则:

* 如果操作数是一个对象,返回 false ;
* 如果操作数是一个空字符串,返回 true ;
* 如果操作数是一个非空字符串,返回 false ;
* 如果操作数是数值 0,返回 true ;
* 如果操作数是任意非 0 数值(包括 Infinity ),返回 false ;
* 如果操作数是 null ,返回 true ;
* 如果操作数是 NaN ,返回 true ;
* 如果操作数是 undefined ,返回 true 。

例如：

```js
alert(!false);      //true
alert(!"blue");     //false
alert(!0);          //true
alert(!NaN);        //true
alert(!"");         //true
alert(!12345);      //false
```

逻辑非运算符也可以用于将一个值转换为与其对应的布尔值。而同时使用两个逻辑非运算符,实际上就会模拟 `Boolean()` 转型函数的行为。其中,第一个逻辑非操作会基于无论什么操作数返回一个布尔值,而第二个逻辑非操作则对该布尔值求反,于是就得到了这个值真正对应的布尔值。当然,最终结果与对这个值使用 `Boolean()` 函数相同,如下面的例子所示:

```js
alert(!!"blue");    //true
alert(!!0);         //false
alert(!!NaN);       //false
alert(!!"");        //false
alert(!!12345);     //true

alert(Boolean({}) == !!{});  //true
```

##### 2. 逻辑与(AND) <kbd>&&</kbd>
逻辑与运算符由两个和号 <kbd>&&</kbd> 表示,有两个操作数,真值表如下:

|第一个操作数|第二个操作数|结果|
|:---:|:---:|:---:|
|true |true |true |
|true |false|false|
|false|true |false|
|false|false|false|

逻辑与操作可以应用于任何类型的操作数,而不仅仅是布尔值。在有一个操作数不是布尔值的情况下,逻辑与操作就不一定返回布尔值;此时,它遵循下列规则:

* 如果第一个操作数是对象,则返回第二个操作数;
* 如果第二个操作数是对象,则只有在第一个操作数的求值结果为 true 的情况下才会返回该对象;
* 如果两个操作数都是对象,则返回第二个操作数;
* 如果有一个操作数是 `null` ,则返回 `null` ;
* 如果有一个操作数是 `NaN` ,则返回 `NaN` ;
* 如果有一个操作数是 `undefined` ,则返回 `undefined` 。

逻辑与操作属于__短路__操作,即如果第一个操作数能够决定结果,那么就不会再对第二个操作数求值。

```js
var box = {} && (5 > 3);    //true,如果第一个操作是对象，则返回第二个操作数
var box = (5 > 3) && {};    //[object Object]，第二个操作数是对象，第一个如果是true，则返回第二个对象，否则返回false
var box = (2 > 3) && {};    //false
var box = {} && 5;          //5,如果第一个操作是对象，则返回第二个操作数
var box = 5 && {};          //[object Object]
var box = 0 && {};          //0

短路操作
var box = true && age;      //出错，age未定义
var box = false && age;     //false，不执行age
```

##### 3. 逻辑或(OR) <kbd>||</kbd>
逻辑或运算符由两个竖线符号 <kbd>||</kbd> 表示,有两个操作数,真值表如下:

|第一个操作数|第二个操作数|结果|
|:---:|:---:|:---:|
|true |true |true |
|true |false|true|
|false|true |true|
|false|false|false|

与逻辑与操作相似,如果有一个操作数不是布尔值,逻辑或也不一定返回布尔值;此时,它遵循下列规则:

* 如果第一个操作数是对象,则返回第一个操作数;
* 如果第一个操作数的求值结果为 false ,则返回第二个操作数;
* 如果两个操作数都是对象,则返回第一个操作数;
* 如果两个操作数都是 null ,则返回 null ;
* 如果两个操作数都是 NaN ,则返回 NaN ;
* 如果两个操作数都是 undefined ,则返回 undefined 。

与逻辑与运算符相似,逻辑或运算符也是__短路__运算符。也就是说,如果第一个操作数的求值结果为true ,就不会对第二个操作数求值了。

```js
var box = {} || (5 > 3);    //[object Object]
var box = (5 > 3) || {};    //true

var box = true || age;      //true
var box = false || age;     //出错，age未定义
var box = oneObject || twoObject;     //把其中一个有效变量值赋给box
```

我们可以利用逻辑或的这一行为来避免为变量赋 null 或 undefined 值。例如:

    var myObject = preferredObject || backupObject;

在这个例子中,变量 `myObject` 将被赋予等号后面两个值中的一个。变量 `preferredObject` 中包含优先赋给变量 `myObject` 的值,变量 `backupObject` 负责在 `preferredObject` 中不包含有效值的情况下提供后备值。如果 `preferredObject` 的值不是 `null` ,那么它的值将被赋给 `myObject` ;如果是 `null` ,则将 `backupObject` 的值赋给 `myObject` 。

<a name="4-乘性运算符"></a>
#### 4. 乘性运算符

ECMAScript 定义了 3 个乘性运算符:乘法、除法和求模。  
在操作数为非数值的情况下会执行自动的类型转换。如果参与乘性计算的某个操作数不是数值,后台会先使用 `Number()` 转型函数将其转换为数值。也就是说,空字符串将被当作 `0`,布尔值 `true` 将被当作 `1`。

##### 1. 乘法
乘法运算符由一个星号 <kbd>*</kbd> 表示,用于计算两个数值的乘积。在处理特殊值的情况下,乘法运算符遵循下列特殊的规则：

* 如果操作数都是数值,执行常规的乘法计算,即两个正数或两个负数相乘的结果还是正数,而如果只有一个操作数有符号,那么结果就是负数。如果乘积超过了 _ECMAScript_ 数值的表示范围,则返回 `Infinity` 或 `-Infinity`
* 如果有一个操作数是 `NaN` ,则结果是 `NaN`
* 如果是 `Infinity` 与 0 相乘,则结果是 `NaN`
* 如果是 `Infinity` 与非 0 数值相乘,则结果是 `Infinity` 或 -`Infinity` ,取决于有符号操作数的符
* 如果是 `Infinity` 与 `Infinity` 相乘,则结果是 `Infinity`
* 如果有一个操作数不是数值,则在后台调用 `Number()` 将其转换为数值,然后再应用上面的规则

##### 2. 除法
除法运算符由一个斜线符号 <kbd>/</kbd> 表示,执行第二个操作数除第一个操作数的计算。除法运算符对特殊的值规则：

* 如果操作数都是数值,执行常规的除法计算,即两个正数或两个负数相除的结果还是正数,而如果只有一个操作数有符号,那么结果就是负数。如果商超过了 _ECMAScript_ 数值的表示范围,则返回 `Infinity` 或 `-Infinity` ;
* 如果有一个操作数是 `NaN` ,则结果是 `NaN` ;
* 如果是非零的有限数被零除,则结果是 `Infinity` 或 `-Infinity` ,取决于有符号操作数的符号;
* 如果是 `Infinity` 被任何非零数值除,则结果是 `Infinity` 或 `-Infinity` ,取决于有符号操作数的符号;
* 如果有一个操作数不是数值,则在后台调用 `Number()` 将其转换为数值,然后再应用上面的规则。

```js
var box = Infinity / Infinity;   //NaN
var box = 0 / 0;                 //NaN
var box = 100 / '';              //Infinity, ''转换成了0， 除数不能为0
var box = 100 / null;            //Infinity, null转换成了0， 除数不能为0
var box = 100 / 'LEE';           //NaN
```

##### 3. 求模
求模(余数)运算符由一个百分号 <kbd>%</kbd> 表示，求模运算符会遵循下列特殊规则来处理特殊的值：

* 如果操作数都是数值,执行常规的除法计算,返回除得的余数
* 如果被除数是无穷大值而除数是有限大的数值,则结果是 `NaN`
* 如果被除数是有限大的数值而除数是零,则结果是 `NaN`
* 如果是 `Infinity` 被 `Infinity` 除,则结果是 `NaN`
* 如果被除数是有限大的数值而除数是无穷大的数值,则结果是被除数
* 如果被除数是零,则结果是零
* 如果有一个操作数不是数值,则在后台调用 `Number()` 将其转换为数值,然后再应用上面的规则

```js
var box = Infinity % Infinity;   //NaN
var box = 0 % 0;                 //NaN
var box = 100 % '';              //NaN
var box = 100 % null;            //NaN
var box = 100 % 'LEE';           //NaN
var box = 100 % true;            //0
var box = 100 % false;           //NaN
```

<a name="5-加性运算符"></a>
#### 5. 加性运算符

##### 1. 加法 <kbd>+</kbd>
如果两个运算符都是数值,执行常规的加法计算,然后根据下列规则返回结果:

* 如果有一个操作数是 `NaN` ,则结果是 `NaN`
* 如果是 `Infinity` 加 `Infinity` ,则结果是 `Infinity`
* 如果是 `-Infinity` 加 `-Infinity` ,则结果是 `-Infinity`
* 如果是 `Infinity` 加 `-Infinity` ,则结果是 `NaN`
* 如果是`+0` 加`+0`,则结果是`+0`
* 如果是`-0` 加`-0`,则结果是`-0`
* 如果是`+0` 加`-0`,则结果是`+0`

如果有一个操作数是字符串,那么就要应用如下规则:

* 如果两个操作数都是字符串,则将第二个操作数与第一个操作数拼接起来;
* 如果只有一个操作数是字符串,则将另一个操作数转换为字符串,然后再将两个字符串拼接起来。
* 如果有一个操作数是对象、数值或布尔值,则调用它们的 `toString()` 方法取得相应的字符串值,然后再应用前面关于字符串的规则。对于 `undefined` 和 `null` ,则分别调用 `String()` 函数并取得字符串 "undefined" 和 "null" 。

```js
var box = 100 + '100';        //100100，这个时候的加号就是字符串连接符，而不是加法运算符，只要有一个是字符串，就不是加法
alert(typeof box);            //string

var box = 'age' + 10 + 20;    //age1020
var box = 'age' + (10 + 20);  //age30

var box = 10 + 20 + 'age';    //30age，两个都是数值就按加法计算
alert(typeof box)             //string

var box = 10 + {};            //10[object Object]
alert(typeof box)             //string

var box = 10 + {
    toString : function() {   //如果对象toString返回的是数值，那么就按数值来
        return 20;            //如果返回的是字符串，如'20'，则为1020
    }
};                            //30
alert(typeof box);            //number
```

##### 2. 减法 <kbd>-</kbd>

* 如果两个运算符都是数值,则执行常规的算术减法操作并返回结果
* 如果有一个操作数是 `NaN` ,则结果是 `NaN`
* 如果是 `Infinity` 减 `Infinity` ,则结果是 `NaN`
* 如果是 `-Infinity` 减 `-Infinity` ,则结果是 `NaN`
* 如果是 `Infinity` 减 `-Infinity` ,则结果是 `Infinity`
* 如果是 `-Infinity` 减 `Infinity` ,则结果是 `-Infinity`
* 如果是`+0` 减`+0`,则结果是`+0`
* 如果是`+0` 减`-0`,则结果是`-0`
* 如果是`-0` 减`-0`,则结果是`+0`
* 如果有一个操作数是字符串、布尔值、 null 或 undefined ,则先在后台调用 `Number()` 函数将其转换为数值,然后再根据前面的规则执行减法计算。如果转换的结果是 NaN ,则减法的结果就是 `NaN`
* 如果有一个操作数是对象,则调用对象的 `valueOf()` 方法以取得表示该对象的数值。如果得到的值是 `NaN` ,则减法的结果就是 `NaN` 。如果对象没有 `valueOf()` 方法,则调用其 `toString()`
方法并将得到的字符串转换为数值

```js
var box = 100 - true;         //99, true转成数值为1
var box = 100 - '';           //100, ''转成数值为0
var box = 100 - null;         //100, null转成数值为0
var box = 100 - '70';         //30, '70'转成数值70
var box = 100 - 'LEE';        //NaN, LEE 转成 NaN
```

<a name="6-关系运算符"></a>
#### 6. 关系运算符
小于 <kbd><</kbd>、大于 <kbd>></kbd>、小于等于 <kbd><=</kbd> 和大于等于 <kbd>>=</kbd> 这几个关系运算符用于对两个值进行比较,返回一个__布尔值__。  
当关系运算符的操作数使用了非数值时,也要进行数据转换或完成某些奇怪的操作。以下就是相应的规则:

* 如果两个操作数都是数值,则执行数值比较
* 如果两个操作数都是字符串,则比较两个字符串对应的字符编码值
* 如果一个操作数是数值,则将另一个操作数转换为一个数值,然后执行数值比较
* 如果一个操作数是对象,则调用这个对象的 `valueOf()` 方法,用得到的结果按照前面的规则执行比较。如果对象没有 `valueOf()` 方法,则调用 `toString()` 方法,并用得到的结果根据前面的规则执行比较
* 如果一个操作数是布尔值,则先将其转换为数值,然后再执行比较
* 任何操作数与 `NaN` 进行关系比较，结果都为 `false`

```js
var box = '3' > '22';     //true，如果两个都是数值字符串，那么会比较第一个字符
var box = 'a' > 'B';      //true，如果两个都是字符串，那么会比较字符编码值
var box = 2 > {};         //false
```

<a name="7-相等运算符"></a>
#### 7. 相等运算符

__相等__和__不相等__——先转换再比较  
__全等__和__不全等__——仅比较而不转换

##### 1. 相等和不相等
相等运算符 <kbd>==</kbd> 不相等运算符 <kbd>!=</kbd>  
这两个运算符都会先转换操作数（通常称为__强制转型__），然后比较相等性。

在转换不同的数据类型时,相等和不相等运算符遵循下列基本规则:

* 如果有一个操作数是布尔值,则在比较相等性之前先将其转换为数值——`false` 转换为 `0`,而 `true` 转换为 `1`
* 如果一个操作数是字符串,另一个操作数是数值,在比较相等性之前先将字符串转换为数值
* 如果一个操作数是对象,另一个操作数不是,则调用对象的 `valueOf()` 方法,用得到的基本类型值按照前面的规则进行比较

这两个运算符在进行比较时则要遵循下列规则

* `null` 和 `undefined` 是相等的
* 要比较相等性之前,不能将 `null` 和 `undefined` 转换成其他任何值
* 如果有一个操作数是 `NaN` ,则相等运算符返回 `false` ,而不相等运算符返回 `true` 。__重要提示:__即使两个操作数都是 `NaN` ,相等运算符也返回 `false` ;因为按照规则, `NaN` 不等于 `NaN`
* 如果两个操作数都是对象,则比较它们是不是同一个对象。如果两个操作数都指向同一个对象,则相等运算符返回 `true` ;否则,返回 `false`

```js
var box = {} == {};   //false,比较的是他们的地址，每个新创建对象的引用地址都不同
var box = '' == 0;    //'' 字符串在比较的时候，会自动转换
```

下表列出了一些特殊情况及比较结果:

|表达式| 值 |
|:---:|:--:|
|null == undefined|true|
|"NaN" == NaN|false|
|5 == NaN|false|
|NaN == NaN|false|
|NaN != NaN|true|
|false == 0|true|
|true == 1|true|
|true == 2|false|
|undefined == 0|false|
|null == 0|false|
|"5" == 5|true|

##### 2. 全等和不全等
除了在比较之前不转换操作数之外,全等和不全等运算符与相等和不相等运算符没有什么区别。  
全等运算符由 3 个等于号 <kbd>===</kbd> 表示,它只在两个操作数未经转换就相等的情况下返回 `true`  
不全等运算符由一个叹号后跟两个等于号 <kbd>!==</kbd> 表示,它在两个操作数未经转换就不相等的情况下返回 `true`

>`null == undefined` 会返回 `true` ,因为它们是类似的值；但 `null === undefined` 会返回 `false` ,因为它们是不同类型的值。

由于相等和不相等运算符存在类型转换问题,而为了保持代码中数据类型的完整
性,推荐使用全等和不全等运算符。

<a name="8-条件运算符"></a>
#### 8. 条件运算符

    variable = boolean_expression ? true_value : false_value;

<a name="9-赋值运算符"></a>
#### 9. 赋值运算符

简单的赋值运算符由等于号 <kbd>=</kbd> 表示,其作用就是把右侧的值赋给左侧的变量

<a name="10-逗号运算符"></a>
#### 10. 逗号运算符

逗号运算符多用于声明多个变量;但除此之外,逗号运算符还可以用于赋值。在用于赋值时,逗号运算符总会返回表达式中的最后一项

```js
var num1=1, num2=2, num3=3;
var num = (5, 1, 4, 8, 0);            // num 的值为 0

var box = {
    1 : 2,
    2 : 4,
    3 : 6
};
alert(box[1]);                        //2

var box = 5 > 4 ? 'true' : 'false';   //true
if(5 > 4) {
    box = 'true';
} else {
    box = 'false';
};
```

***

<a name="第6章-流程控制语句"></a>
## 第6章 流程控制语句

```js
var box = 100;    //单行语句
var age = 20;     //另一条单行语句

{ //花括号包含的语句集合，叫做复合语句，单位一个，一般称为代码块
    var height = 200;
    var width = 300;
} //一对花括号，表示一个复合语句，处理时可以当做一条单行语句来对待
```

##### 语句的种类

<table>
    <tr>
        <th>类型</th>
        <th>子类型</th>
        <th>语法</th>
    </tr>
    <tr>
        <td rowspan="2">声明语句</td>
        <td>变量声明语句</td>
        <td>var box = 100;</td>
    </tr>
    <tr>
        <td>标签声明语句</td>
        <td>label : box;</td>
    </tr>
    <tr>
        <td rowspan="4">表达式语句</td>
        <td>变量赋值语句</td>
        <td>box = 100;</td>
    </tr>
    <tr>
        <td>函数调用语句</td>
        <td>box();</td>
    </tr>
    <tr>
        <td>属性赋值语句</td>
        <td>box.property = 100;</td>
    </tr>
    <tr>
        <td>方法调用语句</td>
        <td>box.method();</td>
    </tr>
    <tr>
        <td rowspan="2">分支语句</td>
        <td>条件分支语句</td>
        <td>if () {} else {};</td>
    </tr>
    <tr>
        <td>多重分支语句</td>
        <td>switch () { case n : ...}</td>
    </tr>
    <tr>
        <td rowspan="4">循环语句</td>
        <td>for</td>
        <td>for(;;;) {}</td>
    </tr>
    <tr>
        <td>for ... in</td>
        <td>for (x in x) {}</td>
    </tr>
    <tr>
        <td>while</td>
        <td>while () {};</td>
    </tr>
    <tr>
        <td>do ... while</td>
        <td>do {} while ();</td>
    </tr>
    <tr>
        <td rowspan="5">控制结构</td>
        <td>继续执行子句</td>
        <td>continue;</td>
    </tr>
    <tr>
        <td>终端执行子句</td>
        <td>break;</td>
    </tr>
    <tr>
        <td>函数返回子句</td>
        <td>return;</td>
    </tr>
    <tr>
        <td>异常触发子句</td>
        <td>throw;</td>
    </tr>
    <tr>
        <td>异常捕获与处理</td>
        <td>try {} catch () {} finally {}</td>
    </tr>
    <tr>
        <td rowspan="2">其他</td>
        <td>空语句</td>
        <td>;</td>
    </tr>
    <tr>
        <td>with 语句</td>
        <td>with () {}</td>
    </tr>
</table>

<a name="-1-if-语句"></a>
####  1. `if` 语句

    if (condition) statement1 else statement2
    if (condition1) statement1 else if (condition2) statement2 else statement3

>`if`里面的括号返回的结果转成布尔值是`true`的时候，只会执行后面的一条语句，如果有多条语句，那么必须使用复合语句把多条语句包含在内  
如果返回的`false`，只会不执行后面的一条语句，除非包含在代码块中

<a name="2-do-while-语句"></a>
#### 2. `do-while` 语句
`do-while` 语句是一种后测试循环语句,即只有在循环体中的代码执行之后,才会测试出口条件。换句话说,在对条件表达式求值之前,循环体内的代码至少会被执行一次。

    do {                    //先运行，再判断的循环体
      statement
    } while (expression);   //判断 expression，再运行 statement

<a name="3-while-语句"></a>
#### 3. `while` 语句
`while` 语句属于前测试循环语句,也就是说,在循环体内的代码被执行之前,就会对出口条件求值。因此,循环体内的代码有可能永远不会被执行。

    while(expression) statement

<a name="4-for-语句"></a>
#### 4. `for` 语句
`for` 语句也是一种前测试循环语句,但它具有在执行循环之前初始化变量和定义循环后要执行的代码的能力。

    for (initialization; expression; post-loop-expression) statement

>使用 `while` 循环做不到的,使用 `for` 循环同样也做不到。也就是说, `for` 循环只是把与循环有关的代码集中在了一个位置。

<a name="5-for-in-语句"></a>
#### 5. `for-in` 语句
`for-in` 语句是一种精准的迭代语句,可以用来枚举对象的属性。以下是 `for-in` 语句的语法:

    for (property in expression) statement

```js
var box = {
    'name' : 'LEE',
    'age' : 28,
    'height' : 178
};
for (var p in box){
    alert(p);
}
```

<a name="6-label-语句"></a>
#### 6. `label` 语句
使用 label 语句可以在代码中添加标签,以便将来使用。

    label: statement

加标签的语句一般都要与 for 语句等循环语句配合使用。

<a name="7-break-和-continue-语句"></a>
#### 7. `break` 和 `continue` 语句
break 和 continue 语句都可以与 label 语句联合使用,从而返回代码中特定的位置。这种联合使用的情况多发生在循环嵌套的情况下,如下面的例子所示:

```js
var num = 0;

outermost:
for (var i=0; i < 10; i++) {
  for (var j=0; j < 10; j++) {
    if (i == 5 && j == 5) {
      break outermost;
    }
    num++;
  }
}

alert(num);   //55
```

<a name="8-with-语句"></a>
#### 8. `with` 语句
`with` 语句的作用是将代码的作用域设置到一个特定的对象中。 `with` 语句的语法如下:

    with (expression) statement;

>由于大量使用 with 语句会导致性能下降,同时也会给调试代码造成困难,因此在开发大型应用程序时,不建议使用 with 语句

```js
var box = {
    'name' : 'LEE',
    'age' : 28,
    'height' : 178
};
with (box) {           //with(box) 可以将 box. 给省略掉
    var n = name;      //这里的 name 相当于 box.name
    var a = age;
    var h = height;
}
alert(n+a+h);
```

<a name="-9-switch-语句"></a>
####  9. `switch` 语句

    switch (expression) {      //expression 要比较的变量
      case value: statement    //case value 相当于 if(expression == value)
        break;                 //break 中途退出，防止穿透
      case value: statement
        break;
      case value: statement
        break;
      case value: statement
        break;
          default: statement    //相当于 if 里的 else
        }

`switch` 语句中的每一种情形(`case`)的含义是:“如果表达式等于这个值 (`value`),则执行后面的语句 (`statement`)”

>`switch` 语句在比较值时使用的是全等运算符,因此不会发生类型转换(例如,字符串 "10" 不等于数值 10)。

***

<a name="第7章-函数"></a>
## 第7章 函数

函数是定义一次但却可以调用或执行任意多次的一段JS代码。函数有时会有参数，即函数被调用时指定了值的局部变量。函数常常使用这些参数来计算一个返回值，这个值也成为函数调用表达式的值。

<a name="1-函数声明"></a>
#### 1. 函数声明

函数对任何语言来说都是一个核心的概念。通过函数可以封装任意多条语句，而且可以在任何地方、任何时候调用执行。ECMAScript中的函数使用function关键字来声明，后跟一组参数以及函数体。

```js
function box() {                           //声明没有参数的函数
    alert('只有函数被调用才会被执行');        //函数本身没有运行功能
}
box();                                     //调用函数，可以放在函数前面调用

function box(name, age){                   //带参数的函数
    alert('姓名：' +name+', 年龄：'+age);
}
box('LEE',28);                             //调用函数，并传参
```

<a name="2-return-返回值"></a>
#### 2. `return` 返回值

带参和不带参的函数，都没有定义返回值，而是调用后直接执行的。实际上，任何函数都可以通过return语句跟后面的要返回的值来实现返回值。

```js
function box() {                         //没有参数的函数
    return '返回值';                      //通过 return 把函数的最终值返回
}
alert(box());                            //打印函数调用的返回值

function box(name,age){                  //有参数的函数
    return '姓名：'+name+',年龄：'+age;    //通过 return 把函数的最终值返回
}
alert(box('LEE',28));                    //调用函数得到返回值，然后外面输出

可以把函数的返回值赋给一个变量，然后通过变量进行操作
function box(num1,num2) {
    return num1 * num2;
}
var num = box(10,5);                     //函数得到的返回值赋给变量5
alert(num);

return语句还有一个功能就是退出当前函数，注意和break的区别
function box(num) {
    if(num < 5) return num;              //满足条件，就返回num
    return 100;                          //返回之后，就不执行下面的语句
}
alert(box(10));
```
>break用在循环和switch分支语句里

<a name="3-arguments-对象"></a>
#### 3. `arguments` 对象

ECMAScript函数不介意传递进来多少参数，也不会因为参数不统一而错误。实际上，函数体内可以通过`arguments`对象来接受传递进来的参数。

>* 命名的参数只提供便利,但不是必需的
* 没有传递值的命名参数将自动被赋予 undefined 值

```js
function box() {
    return arguments[0]+'|'+arguments[1];  //得到每次参数的值
}
alert(box(1,2,3,4,5,6));                   //传递参数

arguments 对象的 length 属性可以得到参数的数量
function box() {
    return arguments.length;               //得到6
}
alert(box(1,2,3,4,5,6));

可以利用length这个属性，来只能的判断有多少参数，然后把参数进行合理的应用
比如，要实现一个加法运算，将所有传进来的数字累加，而数字的个数又不确定
function box() {
    var sum = 0;
    if(arguments.length == 0)return sum;         //如果没有参数，退出
    for(var i = 0;i < arguments.length;i++) {    //如果有，就累加
        sum = sum + arguments[i];
    }
    return sum;                                  //返回累加结果
}
alert(box(5,9,12));

ECMAScript中的函数，没有像其他高级语言那种函数重载功能
重载功能：根据不同的参数，选择调用相同的函数名而参数不同的函数
function box(num,a) {
    return num + 100;
}
function box(num) {             //会执行这个函数,第二个函数将第一个函数覆盖，不具备重载功能
    return num + 200;
}
alert(box(50,20))               //返回结果 250
```

***

<a name="第8章-对象和数组"></a>
## 第8章 对象和数组

__对象__，其实就是一种类型，即引用类型。而对象的值就是引用类型的实例。在ECMAScript中引用类型是一种数据结构，用于将数据和功能组织在一起。它也常被称为类，但ECMAscript中却没有这种东西。虽然ECMAScript是一门面向对象的语言，却不具备传统面向对象语言所支持的类和接口等基本结构。

<a name="1-object-类型"></a>
#### 1. `Object` 类型
虽然`Object`的实例不具备多少功能，但对于在应用程序中的 _存储和传输数据_ 而言，它确实是非常理想的选择。  
创建`Object`类型方法有两种：一种是使用new运算符，一种是字面量表示法。  
对象包含的元素：1.属性（字段）；2.方法（函数）；

```js
1.使用new运算符创建Object
var box = new Object();      //new方式
box.name = 'LEE';            //创建属性字段
box.age = 28;                //创建属性字段

2.new关键字可以省略
var box = Object();          //省略了new关键字

3.使用字面量方式创建Object
var box = {                  //字面量方式封装数据
    name : 'LEE',            //创建属性字段
    age : 28
};

4.属性字段也可以使用字符串
var box = {
    'name' : 'LEE',           //也可以用字符串形式
    'age' : 28
}

5.使用字面量及传统赋值方式
var box = {};                 //字面量方式声明空的对象
box.name = 'LEE';             //点符号给属性赋值
box.age = 28;

6.两种属性输出方式
alert(box.age);               //点表示法输出
alert(box['age']);            //中括号表示法输出，注意引号

PS:　在使用字面量声明Object对象时，不会调用Object()构造函数（Firefox除外）

7.给对象创建方法
var box = {
    run : function() {         //对象中的方法,匿名函数
        return '运行';
    }
}
alert(box.run());              //调用对象中的方法（函数），如果不加括号，会打印代码

8.使用delete删除对象属性
delete box.name;               //删除属性

在实际开发过程中，一般更喜欢字面量的声明方式。  
因为它清晰，语法代码少，而且还给人一种封装的感觉。  
字面量也是向函数传递大量可选参数的首选方式。

function box(obj) {            //参数是一个对象
    if (obj.name != undefined) alert(obj.name);
    if (obj.age != undefined) alert(obj.age);
}
box({                          //匿名对象
    name : 'LEE',
    age : 28
});
```

<a name="2-array-类型"></a>
#### 2. `Array` 类型
虽然数组都是有序排列，但ECMAScript中的数组每个元素可以保存任何类型。ECMAScript中数组的大小也是可以调整的。  
创建`Array`类型有两种方式：第一种是`new`运算符，第二种是字面量

```js
1.使用new关键字创建数组
var box = new Array();         //声明一个数组，空数组
alert(typeof box);             //数组属于object类型

var box = new Array(10);       //创建一个包含10个元素的数组，必须是一个数字
var box = new Array('LEE',28); //创建一个数组并分配元素

2.以上三种方法，可以省略new关键字
var box = Array();             //省略了new关键字

3.使用字面量方式创建数组
var box = [];                  //创建一个空的数组
var box = ['LEE',28];          //创建包含元素的数组
var box = [1,2,];              //禁止这么做，额外的逗号会让IE获取到，而参数错误
var box = [,,,,];              //不允许，会造成浏览器不兼容

PS: 和object一样，字面量的写法不会调用Array()构造函数。(Firefox除外)

4.使用索引下标来读取数组的值
alert(box[2]);                 //获取第3个元素
box[2] = 'AGE';                //修改第3个元素
box[4] = 'HI';                 //增加第5个元素

var box = [];
box['name'] = 'LEE';
box['age'] = 28;
alert(box['name']);            //如果是字符串下标，不会体现在数组上，要单独打印
alert(box);                    //空数组

var box = [];
box[0] = 'LEE';
box[1] = 28;
alert(box);                    //如果是索引下标，就会在数组上体现出来

5.使用length属性获取数组元素量
alert(box.length);             //获取元素个数
box.length = 10;               //强制元素个数
box[box.length] = 'AGE';       //通过length给数组增加一个元素

6.创建一个稍微复杂一点的数组
var box = [
    {
        name : 'LEE',         //第一个元素是一个对象
        age : 28,
        run : function() {
            return 'run';
        }
    },
    ['WANG','ZHENG',new Object()],  //第二个元素是数组
    'YANG',                   //第三个元素是字符串
    25+25,                    //第四个元素是数值
    new Array(1,2,3)          //第五个元素是数组
];
alert(box);                   //[object Object],WANG,ZHENG,[object Object],YANG,50,1,2,3
alert(box[0].name);           //LEE
alert(box[0]['name']);        //LEE

PS: 数组最多可包含 4294967295 个元素，超出即会发生异常
```

<a name="3-对象中的方法"></a>
#### 3. 对象中的方法

##### 转换方法
对象或数组都具有`toLocaleString()`、`toString()`和`valueOf()`方法。其中`toString()`和`valueOf()`无论重写了谁，都会返回相同的值。数组会讲每个值进行字符串形式的拼接，以逗号隔开。

```js
var box = ['LEE',28,new Date()];
alert(box);                  //LEE,28,Thu Nov 05 2015 15:18:52 GMT+0800 (CST)
alert(box.toString());       //LEE,28,Thu Nov 05 2015 15:18:52 GMT+0800 (CST)
alert(box.valueOf());        //LEE,28,Thu Nov 05 2015 15:18:52 GMT+0800 (CST)
alert(box.toLocaleString()); //LEE,28,11/5/2015, 3:18:52 PM,本地格式区域字符串
```
默认情况下，数组字符创都会以逗号隔开。如果使用`join()`方法，则可以使用不同的分隔符来构建这个字符串。

```js
var box = ['LEE',28];
alert(box.join('|'));        //LEE|28，方法运行过后返回按|分割的字符串
alert(typeof box.join('|')); //string
alert(typeof box);           //原数组没有任何变化，类型还是object
```

##### 栈方法
ECMAScript数组提供了一种让数组的行为类似于其他数据结构的方法。也就是说，可以让数组像栈一样，可以限制插入和删除项的数据结构。栈是一种数据结构（后进先出），也就是说最新添加的元素最早被移除。而栈中元素的插入（或叫推入）和移除（或叫弹出），只发生在一个位置——栈的顶部。ECMAScript为数组专门提供了`push()`和`pop()`方法。

`push()`方法可以接收任意数量的参数，把它们逐个添加到数组的末尾，并返回修改该后数组的长度。而`pop()`方法则从数组末尾移除最后一个元素，减少数组的`length`值，然后返回移除的元素。

```js
var box = ['LEE',28,'AGE'];   //字面量声明
alert(box.push('NUM',13));    //在数组末尾添加元素，并返回数组的最新长度
alert(box);
alert(box.pop());             //移除数组最后的元素，并且返回移除的元素
alert(box);
```

##### 队列方法
栈方法是后进先出，而队列方法就是先进先出。队列在数组的末端添加元素，从数组的前端移除元素。通过`push()`向数组末端添加一个元素，然后通过`shift()`方法从数组前端移除一个元素。

```js
var box = ['LEE',28,'AGE'];   //字面量声明
alert(box.push('NUM',13));    //在数组末尾添加元素，并返回数组的最新长度
alert(box);
alert(box.shift());           //移除数组开头的一个元素，并且返回这个元素
alert(box);
```

ECMAScript还为数组提供了一个`unshift()`方法，它和`shift()`方法的功能完全相反。`unshift()`方法为数组的前端添加一个元素。

```js
var box = ['LEE',28,'AGE'];   //字面量声明
alert(box.unshift('NUM',13)); //在数组前端添加元素，并返回数组的最新长度
alert(box);

PS: IE浏览器对 unshift() 方法总是返回 undefined 而不是数组的新长度。
```

##### 重排序方法
数组中已经存在两个可以直接用来排序的方法：`reverse()`和`sort()`

```js
reverse() 逆向排序
var box = [1,2,3,4,5];         //数组
alert(box.reverse());          //5,4,3,2,1，逆向排序方法，返回排序后的数组
alert(box);                    //5,4,3,2,1,原数组也被逆向排序了，说明是引用

sort() 从小到大排序
var box = [4,1,7,3,9,2];       //数组
alert(box.sort());             //1,2,3,4,7,9，从小到大排序，返回排序后的数组
alert(box);                    //1,2,3,4,7,9，原数组也被从小到大排序了

sort 方法的默认排序在数字排序上有些问题，因为数字排序和数字字符串排序的算法是一样的。
我们必须修改这一特征，修改的方式，就是给sort(参数)方法传递一个函数参数。

function compare(value1,value2){    //数字排序的函数参数
    if(value1 < value2) {           //小于，返回负数
        return -1;
    }else if(value1 > value2){      //大于，返回正数
        return 1;
    }else{                          //其他，返回0
        return 0;
    }
}
var box = [0,1,5,10,15];            //验证数字字符串，和数字的区别
alert(box.sort(compare));           //传参

PS:如果要反向操作，即从大到小排序，正负颠倒即可。当然，如果要逆序用reverse()更加方便。
```

##### 操作方法
ECMAScript为操作已经包含在数组中的元素提供了很多方法。  
`concat()`方法可以基于当前数组创建一个新数组。

```js
var box = ['LEE',28];         //当前数组
var box2 = box.concat('AGE'); //创键新数组，并添加新元素
alert(box2);                  //LEE,28,AGE，输出新数组
alert(box);                   //当前数组没有任何变化
```
`slice()`方法可以基于当前数组获取指定区域元素并创建一个新数组。  

```js
var box = [1,2,3,4,5,6];      //当前数组
var box1 = box.slice(1);      //从第1个位置取到最后
var box2 = box.slice(1,4);    //从第1个位置取到第3个位置
alert(box1);                  //2,3,4,5,6
alert(box2);                  //2,3,4
```
`splice()`主要用途是向数组的中部插入元素。

```js
splice中的刪除功能
var box = ['LEE',28,'AGE'];   //当前数组
var box2= box.splice(0,2);    //表示从第0个位置截取2个元素，而不是从第0个位置取到第2个位置
alert(box2);                  //LEE,28，返回截取的元素
alert(box);                   //AGE，当前数组被截取的元素被删除

splice中的插入功能
var box = ['LEE',28,'AGE'];   //当前数组
var box2= box.splice(1,0,'HI','A');  //从第1个位置插入元素，0表示不截取任何元素，插入后面的元素
alert(box2);                  //返回空
alert(box);                   //LEE,HI,A,28,AGE

splice中的替换功能
var box = ['LEE',28,'AGE'];   //当前数组
var box2= box.splice(1,1,100);//从第1个位置，截取1个元素，插入后面的元素
alert(box2);                  //28，返回截取的元素
alert(box);                   //LEE,100,AGE
```

***

<a name="第9章-时间与日期"></a>
## 第9章 时间与日期

<a name="1-date-类型"></a>
#### 1. `Date` 类型
创键一个日期对象，使用`new`运算符和`Date`构造方法（构造函数）即可。

```js
var box = new Date();     //创键一个日期对象
```

在调用`Date`构造方法而不传递参数的情况下，新建的对象自动获取当前的时间和日期。

```js
alert(box);               //不同的浏览器显示不同
```

###### 日期/时间组件方法

|方法|说明|
|---|----|
|getTime()            |返回表示日期的毫秒数;与 valueOf() 方法返回的值相同|
|setTime( 毫秒 )        |以毫秒数设置日期,会改变整个日期|
|getFullYear()        |取得4位数的年份(如2007而非仅07)|
|getUTCFullYear()     |返回UTC日期的4位数年份|
|setFullYear( 年 )     |设置日期的年份。传入的年份值必须是4位数字(如2007而非仅07)|
|setUTCFullYear( 年 )  |设置UTC日期的年份。传入的年份值必须是4位数字(如2007而非仅07)|
|getMonth()           |返回日期中的月份,其中0表示一月,11表示十二月|
|getUTCMonth()        |返回UTC日期中的月份,其中0表示一月,11表示十二月|
|setMonth( 月 )        |设置日期的月份。传入的月份值必须大于0,超过11则增加年份|
|setUTCMonth( 月 )     |设置UTC日期的月份。传入的月份值必须大于0,超过11则增加年份|
|getDate()            |返回日期月份中的天数(1到31)|
|getUTCDate()         |返回UTC日期月份中的天数(1到31)|
|setDate( 日 )         |设置日期月份中的天数。如果传入的值超过了该月中应有的天数,则增加月份|
|setUTCDate( 日 )      |设置UTC日期月份中的天数。如果传入的值超过了该月中应有的天数,则增加月份|
|getDay()             |返回日期中星期的星期几(其中0表示星期日,6表示星期六)|
|getUTCDay()          |返回UTC日期中星期的星期几(其中0表示星期日,6表示星期六)|
|getHours()           |返回日期中的小时数(0到23)|
|getUTCHours()        |返回UTC日期中的小时数(0到23)|
|setHours( 时 )        |设置日期中的小时数。传入的值超过了23则增加月份中的天数|
|setUTCHours( 时 )     |设置UTC日期中的小时数。传入的值超过了23则增加月份中的天数|
|getMinutes()         |返回日期中的分钟数(0到59)|
|getUTCMinutes()      |返回UTC日期中的分钟数(0到59)|
|setMinutes( 分 )      |设置日期中的分钟数。传入的值超过59则增加小时数|
|setUTCMinutes( 分 )   |设置UTC日期中的分钟数。传入的值超过59则增加小时数|
|getSeconds()         |返回日期中的秒数(0到59)|
|getUTCSeconds()      |返回UTC日期中的秒数(0到59)|
|setSeconds( 秒 )      |设置日期中的秒数。传入的值超过了59会增加分钟数|
|setUTCSeconds( 秒 )   |设置UTC日期中的秒数。传入的值超过了59会增加分钟数|
|getMilliseconds()    |返回日期中的毫秒数|
|getUTCMilliseconds() |返回UTC日期中的毫秒数|
|setMilliseconds( 毫秒 )|设置日期中的毫秒数|
|setUTCMilliseconds( 毫秒 )|设置UTC日期中的毫秒数|
|getTimezoneOffset()|返回本地时间与UTC时间相差的分钟数。例如,美国东部标准时间返回300。在某地进入夏令时的情况下,这个值会有所变化|

***

<a name="第10章-正则表达式"></a>
## 第10章 正则表达式

假设用户需要在HTML表单中填写姓名、地址、出生日期等，那么在将表单提交到服务器进一步处理前，JavaScript程序会检查表单以确认用户确实输入了信息并且这些信息是符合要求的。

<a name="1-什么是正则表达式"></a>
#### 1. 什么是正则表达式
正则表达式（regular expression）是一个描述字符模式的对象。ECMAScript 的 `RegExp` 类表示正则表达式，而 `String` 和 `RegExp` 都定义了使用正则表达式进行强大的模式匹配和文本检索与替换的函数。  
正则表达式主要用来验证客户端的输入数据。用户填写完表单单击按钮之后，表单就会被发送到服务器，在服务器i通常都会用 PHP、ASP.NET 等服务器脚本对其进行进一步处理，因为客户端验证，可以节约大量的服务器端的系统资源，并且提供更好的用户体验。

<a name="2-创建正则表达式"></a>
#### 2. 创建正则表达式
创建正则表达式和创建字符串类似，创建正则表达式提供了两种方法，一种是采用 new 运算符，另一个是采用字面量方式。

##### 两种创建方式

```js
var box = new RegExp('box');       //必须有一个参数，第一个参数是模式字符串
alert(box);                        // /box/ 两个反斜杠是正则表达式的字面量表示法
var box = new RegExp('box','gi');  //第二个参数为可选，模式修饰符
alert(box);                        // /box/gi
```
模式修饰符的可选参数

|参数|含义|
|:--:|:--:|
|i|忽略大小写|
|g|全局匹配|
|m|多行匹配|

```js
var box = /box/;       //使用字面量的正则表达式
var box = /box/gi;     //使用字面量带修饰符的正则表达式
```

##### 测试正则表达式
`RegExp` 对象包含两个方法:`test()`和`exec()`,功能基本相似，用于测试字符串匹配。`test()`方法在字符串查找是否存在指定的正则表达式并返回布尔值，如果存在则返回`true`，不存在则返回`false`。`exec()`方法也用于在字符串中查找指定正则表达式，如果`ecec()`方法执行成功，则返回包含该查找字符串的相关信息数组。如果执行失败，则返回`null`。

RegExp对象的方法

|方法|功能|
|:-:|:-:|
|test|在字符串中测试模式匹配，返回true或false|
|exec|在字符串中执行匹配搜索，返回结果数组|


```js
使用 new 运算符的 test 方法示例
var pattern = new RegExp('Box');     //模式
var str = 'This is a box';
alert(pattern.test(str));            //false

var pattern = new RegExp('Box','i'); //忽略大小写
var str = 'This is a box';
alert(pattern.test(str));            //true


使用字面量方式的 test 方法示例
var pattern = /Box/i;                //忽略大小写
var str = 'This is a box';
alert(pattern.test(str));            //true


使用一条语句实现正则匹配
alert(/Box/i.test('box'));           //true


使用 exec 返回匹配数组
var pattern = /Box/i;                //忽略大小写
var str = 'This is a box';
alert(pattern.exec(str));            //box，没有就返回null
alert(typeof pattern.exec(str));     //object，返回的是数组
```

##### 使用字符串的正则表达式方法
除了 `test()` 和 `exec()` 方法，`String`对象也提供了4个使用正则表达式的方法。

String对象中的正则表达式方法

|方法|含义|
|:-:|:-:|
|match(pattern)|返回 pattern 中的字串或 null|
|replace(pattern,replacement)|用 replacement 替换 pattern|
|search(pattern)|返回字符串中 pattern 开始位置|
|split(pattern)|返回字符串按指定 pattern 拆分的数组|

```js
使用 match 方法获取匹配的数组
var pattern = /Box/i;
var str = 'This is a box! That is a Box too!';
alert(str.match(pattern));          //box,Box,找不到匹配，返回-1

使用 replace 方法替换匹配数组
var pattern = /Box/i;               //未开全局，匹配一个即停止
var str = 'This is a Box! That is a Box too!';
alert(str.replace(pattern,'Tom'));  //This is a Tom! That is a Box too! 返回替换后的字符串，只限第一个

var pattern = /Box/gi;              //全局，所有匹配都替换
var str = 'This is a Box! That is a Box too!';
alert(str.replace(pattern,'Tom'));  //This is a Tom! That is a Tom too! 返回替换后的字符串

使用 split 拆分成字符串数组
var pattern = /!/gi;                //以！为基准拆分
var str = 'This is a Box! That is a Box too!';
alert(str.split(pattern));          //This is a Tom,That is a Tom too,
alert(str.split(pattern).length);   //数组数量为3个,最后有个空数组
```

RegExp 对象的静态属性

|属性|短名|含义|
|:-:|:-:|:-:|
|input|$_|当前被匹配的字符串|
|lastMatch|$&|最后一个匹配字符串|
|lastParen|$+|最后一对圆括号内的匹配字串|
|leftContext|$`|最后一次匹配前的字串|
|multiline|$*|用于指定是否所有的表达式都用于多行的布尔值|
|rightContext|$'|在上次匹配之后的字串|

```js
使用静态属性
var pattern = /(g)oogle/;
var str = 'This is google!';
pattern.test(str);            //或者exec()，必须执行一下静态属性才有效
alert(RegExp.input);           //This is google!
alert(RegExp.lastMatch);       //google
alert(RegExp.lastParen);       //g
alert(RegExp.leftContext);     //This is
alert(RegExp.multiline);       //false
alert(RegExp.rightContext);    //!

PS: Opera 不支持 input、lastMatch、lastParen 和 multiline属性，IE 不支持 multiline属性。
所有的属性可以使用短名来操作：
RegExp.input 可以改写成 RegExp['$_']，以此类推，但 RegExp.input 比较特殊，还可以写成 RegExp.$_
```

RegExp 对象的实例属性

|属性|含义|
|:-:|:-:|
|global|Boolean值，表示g是否已设置|
|ignoreCase|Boolean值，表示i是否已设置|
|lastIndex|整数，代表下次匹配将从哪里字符位置开始|
|multiline|Boolean值，表示m是否已设置|
|Source|正则表达式的原字符串形式|

```js
var pattern = /google/gi;
alert(pattern.global);          //true
alert(pattern.ignoreCase);      //true
alert(pattern.lastIndex);       //0
alert(pattern.multiline);       //false
alert(pattern.Source)           //google

var pattern = /google/g;
var str = 'google google google!';
pattern.test(str);              //google,匹配第一次
alert(pattern.lastIndex);       //6，第二次匹配的位

PS:以上基本没什么用，并且 lastIndex 在获取下次匹配位置上IE和其他浏览器有偏差，主要表现在非全局匹配上。
lastIndex 还支持手动设置，直接赋值操作。
```

<a name="3-获取控制"></a>
#### 3. 获取控制
正则表达式元字符是包含特殊含义的字符。它们有一些特殊，可以控制匹配模式的方式。反斜杠后的元字符将失去其特殊含义。

##### 字符类：单个字符和数字
|元字符/元符号|匹配情况|
|-----|----|
|.|匹配除换行符外的任意字符|
|[a-z0-9]|匹配括号中的字符集中的任意字符|
|[^a-z0-9]|匹配任意不在括号中的字符集中的字符|
|\d|匹配数字|
|\D|匹配非数字，同[^0-9]相同|
|\w|匹配字母和数字及_|
|\W|匹配非字母和数字及_|

##### 字符类：空白字符
|元字符/元符号|匹配情况|
|-----|----|
|\0|匹配 null 字符|
|\b|匹配空格字符，用于检测是否到达边界|
|\f|匹配进纸字符|
|\n|匹配换行符|
|\r|匹配回车字符|
|\t|匹配制表符|
|\s|匹配空白字符、空格、制表符和换行符|
|\S|匹配非空白字符|

##### 字符类：锚字符
|元字符/元符号|匹配情况|
|-----|----|
|^|行首匹配|
|$|行尾匹配|
|\A|只有匹配字符串开始处|
|\b|匹配单词边界，词在[]内时无效|
|\B|匹配非单词边界|
|\G|匹配当前搜索的开始位置|
|\Z|匹配字符串结束处或行尾|
|\z|只匹配字符串结束处|

##### 字符类：重复字符
|元字符/元符号|匹配情况|
|-----|----|
|x?|匹配0个或1个x|
|x*|匹配0个或任意多个x|
|x+|匹配至少一个x|
|(xyz)+|匹配至少一个(xyz)|
|x{m}|匹配m个x，不能多也不能少|
|x{m,}|匹配m个或以上个x|
|x{m,n}|匹配最少m个、最多n个x|

##### 字符类：替代字符
`this|where|logo` 匹配`this`或`where`或`logo`中任意一个，匹配概念非相等，包含的意思

##### 字符类：记录字符
|元字符/元符号|匹配情况|
|-----|----|
|(string)|用于反向引用的分组|
|\1 或 $1|匹配第一个分组中的内容|
|\2 或 $2|匹配第二个分组中的内容|
|\3 或 $3|匹配第三个分组中的内容|

```js
使用点元字符
var pattern = /g..gle/;           //. 匹配除换行符外的任意字符
var str = 'google';
alert(pattern.test(str));

重复匹配
var pattern = /g.*gle/;           //.* 匹配0个1个或多个.
var str = 'google';               //*,?,+,{n,m}
alert(pattern.test(str));

var pattern = /go{2-4}gle/;       //o{2-4}表示匹配o2-4次，包含2和4
var str = 'google';
alert(pattern.test(str));         //true

使用字符类匹配
var pattern = /g[a-zA-Z_]*gle/;   //[a-zA-Z_]* 表示任意个a-zA-Z_中的字符
var str = 'google';
alert(pattern.test(str));

var pattern = /g[^0-9]*gle/;      //[^0-9]* 表示任意个非0-9中的字符
var str = 'google';
alert(pattern.test(str));

var pattern = /[a-z][A-Z]+/;      //[A-Z]+ 表示 A-Z 一次或多次
var str = 'gOOGLE';
alert(pattern.test(str));

var pattern = /^[0-9]+oogle/;      //^[0-9]+ 行首至少一个[0-9]
var str = '444oogle';
alert(pattern.test(str));

使用元符号匹配
var pattern = /g\w*gle/;           // \w* 匹配任意多个所有字母数字
var str = 'google';
alert(pattern.test(str));

var pattern = /google\d*/;         // \d* 匹配任意多个数字
var str = 'google666';
alert(pattern.test(str));

var pattern = /\D{7,}/;            // \D{7,} 匹配至少7个非数字
var str = 'google8';
alert(pattern.test(str));

使用锚元字符匹配
var pattern = /^google$/;          // ^从开头匹配，$从结尾开始匹配
var str = 'google';
alert(pattern.test(str));

var pattern = /goo\sgle/;          // \s 可以匹配到空格
var str = 'goo gle';
alert(pattern.test(str));

var pattern = /google\b/;          // \b 可以匹配是否到了边界
var str = 'google';
alert(pattern.test(str));

使用或模式匹配
var pattern = /google|baidu|bing/; // 匹配三种其中一种字符串
var str = 'google';
alert(pattern.test(str));

使用分组模式匹配
var pattern = /(google){4,8}/;     // 匹配分组里的字符串 4-8 次
var str = 'googlegooglegooglegoogle';
alert(pattern.test(str));          //true

var pattern = /8(.*)8/;            // 获取 8..8之间的任意字符
var str = 'This is 8google8';
str.match(pattern);                //8google8,google
alert(RegExp.$1);                  //google，RegExp.$1 表示获取模式中第一个分组对应的匹配字符串

var pattern = /8(.*)8/;            // 获取 8..8之间的任意字符
var str = 'This is 8google8';
var　result = str.replace(pattern,'<strong>$1</strong>');  //得到替换的字符串输出，$1表示分组获取字符串匹配到的内容
document.write(result);

var pattern = /(.*)\s(.*)/;
var str = 'google baidu';
var result = str.replace(pattern,'$2 $1');   //将两个分组的值替换输出，等同于交换位置
document.write(result);
```

|贪婪|惰性|
|:-:|:-:|
|+|+?|
|?|??|
|* |*?|
|{n}|{n}?|
|{n,}|{n,}?|
|{n,m}|{n,m}?|

```js
关于贪婪和惰性
var pattern = /[a-z]+/;
var str = 'abcdef';
alert(str.replace(pattern,'1'));  //1

var pattern = /[a-z]+?/;          //使用惰性模式
var str = 'abcdef';
alert(str.replace(pattern,'1'));  //1bcdef，只有第一个字符变成了1

var pattern = /[a-z]+/g;
var str = 'abcdef';
alert(str.replace(pattern,'1'));  //1

var pattern = /[a-z]+?/g;         //开启全局。并且使用惰性模式
var str = 'abcdef';
alert(str.replace(pattern,'1'));  //111111，每一个字母替换成了1

var pattern = /8(.*)8/g;          //贪婪
var str = 'This is 8google8, That is 8google8, There is 8google8';
var result = str.replace(pattern,'<strong>$1</strong>');
//匹配到了 google8, That is 8google8, There is 8google
document.write(result);  //结果： This is <strong>google8, That is 8google8, There is 8google</strong>

var pattern = /8(.+?)8/g;          //使用惰性，开启全局
var str = 'This is 8google8, That is 8google8, There is 8google8';
var result = str.replace(pattern,'<strong>$1</strong>');
document.write(result);

var pattern = /8([^8]*)8/g;        //另一种禁止贪婪，屏蔽了8的匹配，也就是两边包含字符
var str = 'This is 8google8, That is 8google8, There is 8google8';
var result = str.replace(pattern,'<strong>$1</strong>');
document.write(result);

使用exec返回数组
var pattern = /^[a-z]+\s[0-9]{4}$/i;
var str = 'google 2012';
alert(pattern.exec(str));        //返回一个包含字符串的数组

var pattern = /^[a-z]+/i;        //只匹配到字母
var str = 'google 2012';
alert(pattern.exec(str));        //只返回google的字符串数组

var pattern = /^([a-z]+)\s([0-9]{4})$/i;   //使用了分组
var str = 'google 2012';
alert(pattern.exec(str)[0]);     //google 2012,返回匹配到的全部字符串
alert(pattern.exec(str)[1]);     //google，返回匹配到的第一个分组字符串
alert(pattern.exec(str)[2]);     //2012，返回匹配到的第二个分组字符串

捕获性分组和非捕获性分组
var pattern = /(\d+)([a-z])/;    //这个叫做捕获性分组，所有的分组都捕获返回
var str = '123abc';
alert(pattern.exec(str));        //123a，123，a

var pattern = /(\d+)(?:[a-z])/;  //非捕获性分组，只要在不需要捕获返回的分组加上?:
var str = '123abc';
alert(pattern.exec(str));        //123a，123

使用分组嵌套
var pattern = /(A?(B?(C?)))/;    //嵌套分组，从外往内获取
var str = 'ABC';
alert(pattern.exec(str));        //ABC,ABC,BC,C
//第一步：整个匹配到的字符串ABC
//第二步：匹配第一个分组(A?(B?(C?)))，ABC
//第三步：匹配第二个分组(B?(C?))，BC
//第四步：匹配第三个分组(C?)，C

使用前瞻捕获
var pattern = /(goo(?=gle))/;     //goo 后面必须跟着 gle 才能捕获
var str = 'google';
alert(pattern.exec(str));         //goo,goo,没有则返回null

使用特殊字符匹配
var pattern = /\.\[\/b\]/;        //用\符号来转义正则里面的特殊字符，才能匹配
var str = '.[/b]';
alert(pattern.test(str));

使用换行模式
var pattern = /^\d+/gm;           //限定首匹配，并且开启换行模式
var str = '1.baidu\n2.google\n3.bing';
var result = str.replace(pattern,'#');
alert(result);
```

<a name="4-常用的正则"></a>
#### 4. 常用的正则
```js
1.检查邮政编码
var pattern = /[1-9][0-9]{5}/;
var str = '224000';
alert(pattern.test(str));

2.检查文件压缩包
var pattern = /^[\w\-]+\.(zip|rar|gz)$/;    // | 选择符必须用分组符号包含起来
var str = '123.zip';
alert(pattern.exec(str));

3.删除多余空格
var pattern = /\s/g;
var str = '111 222 333';
var result = str.replace(pattern,'');
alert(result);

4.删除首尾空格
var pattern = /^\s+/;
var str = '    goo    gle   ';
var result = str.replace(pattern,'');
pattern = /\s+$/;
result = result.replace(pattern,'');
alert('|'+result+'|');

var pattern = /^\s*(.+?)\s*$/;              //使用非贪婪捕获，即惰性模式
var str = '     google   ';
alert('|'+pattern.exec(str)[1]+'|');

var pattern = /^\s*(.+?)\s*$/;
var str = '      googel    ';
alert('|'+str.replace(pattern,'$1')+'|');   //使用分组获取

5.简单的电子邮件验证
var pattern = /^([a-zA-Z0-9_\.\-]+)@([a-zA-Z0-9_\.\-]+)\.([a-zA-Z]{2,4})$/;
var str = 'yc60.com@gmail.com';
alert(pattern.test(str));

var pattern = /^([\w\.\-]+)@([\w\.\-]+)\.([\w]{2,4})$/;
var str = 'yc60.com@gmail.com';
alert(pattern.test(str));

PS: 以上是简单电子邮件验证，复杂的要比这个复杂很多
```

<a name="第11章-function-类型"></a>
## 第11章 `Function` 类型

在ECMAScript中，`Function`（函数）类型实际上是对象。每个函数都是`Function`类型的实例，而且都与其他引用类型一样具有属性和方法。由于函数是对象，因此函数名实际上也是一个指向函数对象的指针。

<a name="1-函数的声明方式"></a>
#### 1. 函数的声明方式

```js
普通的函数声明
function box(num1,num2) {
    return num1 + num2;
}

使用变量初始化函数
var box = function(num1,num2) {
    return num1 + num2;
}

构造函数声明
var box = new Function('num1','num2','return num1 + num2');
alert(typeof box);    //function

PS: 第三种方式我们不推荐，因为这种语法会导致解析两次代码，从而影响性能。
（第一次解析常规ECMAScript代码，第二次是解析传入构造函数中的字符串）
但我们可以通过这种语法来理解“函数是对象，函数名是指针”的概念
```

<a name="2-作为值的函数"></a>
#### 2. 作为值的函数
ECMAScript中的函数名本身就是变量，所以函数也可以作为值来使用。也就是说，不仅可以像传递参数一样把一个函数传递给另一个函数，而且可以将一个函数作为另一个函数的结果返回。

```js
下面的例子很普通，不是作为函数来传递的，而是作为函数的返回值来传递的
function box(sum,num) {
    return sum + num;
}
function sum(num) {
    return num + 10;
}
var result = box(sum(10),10);  //sum(10)这里传递的是函数的返回值，和普通的变量一样，没区别
alert(result);                 //30

要把函数本身作为参数传递，而不是函数的结果
function box(sum,num) {
    return sum(num);
}
function sum(num) {
    return num + 10;
}
var result = box(sum,10);      //这里sum是一个函数，当做参数传递到另外一个函数里，而不是函数的返回值
alert(result);                 //20
```

<a name="3-函数内部属性"></a>
#### 3. 函数内部属性
在函数内部，有两个特殊的对象：`arguments`和`this`。`arguments`是一个类数组对象，包含着传入函数中的所有参数，主要用途是保存函数参数。但这个对象还有一个名叫`callee`的属性，该属性是一个指针，指向拥有这个`arguments`对象的函数。

```js
function box(num) {
    if (num <= 1) {
        return 1;
    } else {
        return num * box(num - 1);         //一个简单的递归
    }
}
```
对于阶乘函数一般要用递归算法，所以函数内部一定会调用自身；如果函数名不改变是没有问题的，但一旦改变函数名，内部的自身调用需要逐一修改。为了解决这个问题，我们可以使用`arguments.callee`来代替。

```js
function box(num) {
    if(num <= 1) {
        return 1;
    } else {
        return num * arguments.callee(num-1); //使用callee来执行自身
    }
}
```
函数内部另一个特殊对象是`this`，其行为与Java和C#中的`this`大致相似。换句话说，`this`引用的是函数以执行操作的对象，或者说函数调用语句所处的那个作用域。__PS:__ 当在全局作用域中调用函数时，`this`对象引用的就是`window`。`window`是JS里面最外围最大的对象。

```js
alert(typeof window);       //window是对象，类型是对象，表示全局
alert(this);                //[object Window] 因为在window的范围下，this目前表示的是window
alert(typeof this);         //和window一模一样，所以this就是window

var color = 'red';          //这里color就是全局变量，而这个变量又是window的属性
alert(window.color);        //red

window.color = '红色的';     //相当于 var color = '红色的'，全局的
alert(this.color);          //打印全局的 color


var box = {
    color : '蓝色的',        //局部的 color
    sayColor : function() {
        alert(this.color);  //此时的 this 只能 box 里的 color
    }
};
box.sayColor();             //打印局部的 color
alert(this.color);          //还是全局的

window.color = '红色的';
function sayColor() {
    alert(this.color);      //这里执行的时候是动态的，第一在window下，第二次在box下
}
sayColor();                 //这里调用sayColor，其实范围还是在window下
var box = {
    color : '蓝色的'
};
box.sayColor = sayColor;    //这端代码相当于 sayColor : function() { alert(this.color);  }
box.sayColor();             //这里执行的是box里面的this.color
```

<a name="4-函数属性和方法"></a>
#### 4. 函数属性和方法
ECMAScript中的函数是对象，因此函数也有属性和方法。每个函数都包含两个属性：`length`和`prototype`。其中，`length`属性表示函数希望接收的命名参数的个数。

```js
function box (name, age) {
    alert(name + age);
}
alert(box.length);           //2
```
PS:对于`prototype`属性，它是保存所有实例方法的真正所在，也就是原型。这个属性，我们将在面向对象一章详细介绍。而`prototype`下两个方法：`apply()`和`call()`，每个函数都包含这两个非继承而来的方法。这两个方法的用途都在特定的作用域中调用函数，实际上等于设置函数体内`this`对象的值。

```js
function box (num1, num2) {
    return num1 + num2;
}
function sayBox (num1, num2) {
    return box.apply(this,[num1,num2]);  //apply和call可以冒充另外一个函数
}   //this 表示 window 作用域，[]表示传递的参数
function sayBox2(num1,num2) {
    return box.apply(this,arguments);
}
alert(sayBox(10,10));         //20
alert(sayBox2(10,10));        //20
```
`call()`方法于`apply()`方法相同，他们的区别仅仅在于接收参数的方式不同。对于`call()`方法而言，第一个参数是作用域，没有变化，变化只是其余的参数都是直接传递给函数的。

```js
function box(num1, num2) {
    return num1 +num2;
}
function callBox(num1, num2) {
    return box.call(this,num1,num2);  //和 apply 区别在于后面的传参
}
alert(callBox(10,10));
```
事实上，传递参数并不是`apply()`和`call()`方法正真的用武之地；它们经常使用的地方是能够扩展函数赖以运行的作用域。

```js
var color = '红色的';        //或者 window.color = '红色的';也行
var box = {
    color : '蓝色的'
};
function sayColor() {
    alert(this.color);
}
sayColor();                 //作用域在window
//用call来实现对象冒充，冒充box下，冒充window下
sayColor.call(this);        //作用域在window
sayColor.call(window);      //作用域在window
sayColor.call(box);         //蓝色的，作用域在box,对象冒充
```
这个例子是之前作用域理解的例子修改而成，我们可以发现当我们使用`call(box)`方法的时候，`sayColor()`方法的运行环境已经变成了`box`对象里了。  
使用`call()`或者`apply()`来扩充作用域的最大好处，就是对象不需要与方法发生任何耦合关系（耦合，就是互相关联的意思，扩展和维护会发生连锁反应）。也就是说，`box`对象和`sayColor`方法之间不会有多余的关联操作，比如 `box.sayColor = sayColor;`

***

<a name="第12章-变量、作用域及内存"></a>
## 第12章 变量、作用域及内存

JavaScript的变量与其他语言的变量有很大的区别。JavaScript变量是松散型的（不强制类型）本质，决定了它只是在特定时间用于保存特定值的一个名字而已。由于不存在定义某个变量必须要保存何种数据类型值的规则，变量的值及其数据类型可以在脚本的生命周期内改变。

<a name="1-变量及作用域"></a>
#### 1. 变量及作用域
##### 基本类型和引用类型的值
ECMAScript变量可能包含两种不同的数据类型的值：基本类型值和引用类型值。基本类型值指的是那些保存在栈内存中的简单数据段，即这种值完全保存在内存中的一个位置，而引用类型值则是指那些保存在堆内存中的对象，意思是变量中保存的实际上只是一个指针，这个指针指向内存中的另一个位置，该位置保存对象。  
将一个值赋给变量时，解析器必须确定这个值是基本类型值，还是引用类型至。基本类型值有一下几种：`Undefined`、`Null`、`Boolean`、`Number`、`String`。这些类型在内存中分别占有固定大小的空间，他们的值保存在栈空间，我们通过按值来访问的。  
PS: 在某些语言中，字符串以对象的形式来表示，因此被认为是引用类型。ECMAScript放弃这一传统。  
如果赋值的是引用类型的值，则必须在堆内存中为这个值分配空间。由于这种值的大小不固定，因此不能把它们保存到栈内存中。但内存地址大小是固定的，因此可以将内存地址保存在栈内存中。这样，当查询引用类型的变量时，先从栈中读取内存地址，然后再通过地址找到堆中的值。对于这种，我们把它叫做按__引用访问__。

##### 动态属性
定义基本类型值和引用类型值的方式是相似的：创建一个变量并为该变量赋值。但是，当这个值保存到变量中该以后，对不同类型值可以执行的操作则大相径庭。

```js
var box = new Object();      //创建引用类型
box.name = 'LEE';            //新增一个属性
alert(box.name);             //输出
```
如果是基本类型的值添加属性的话，就会出现问题了。

```js
var box = 'LEE';             //创建一个基本类型
box.age = 27;                //给基本类型添加属性
alert(box.age);              //undefined，不是引用类型，无法输出
```

##### 复制变量值
在变量复制方面，基本类型和引用类型也有所不同。基本类型复制的是值本身，而引用类型复制的是地址。

```js
var box = 'LEE';             //在栈内存生成一个box'LEE'
var box2 = box;              //在栈内存再生成一个box2 'LEE'
```
`box2`虽然是`box1`的一个副本。但从图示可以看出，它是完全独立的。也就是说，两个变量分别操作时胡不影响。

```js
var box = new Object();       //创建一个引用类型
box.name = 'LEE';             //新增一个属性
var box2 = box;               //把引用地址赋值给box2
```
在引用类型中，`box2`其实就是`box`，因为他们指向的是同一个对象。如果这个对象中的`name`属性被修改了，`box2.name`和`box.name`输出的值都会被相应修改掉了。

##### 传递参数
ECMAScript中所有函数的参数都是按值传递的，言下之意就是说，参数不会按引用传递，虽然变量有基本类型和引用类型之分。

```js
function box(num) {           //按值传递
    num += 10;
    return num;
}
var num = 50;
var result = box(num);
alert(result);                //60
alert(num);                   //50，如果是按引用传递，那么函数里的num会称为类似全局变量，最后输出60
```
PS: 以上的代码中，传递的参数是一个基本类型的值。而函数里的`num`是一个局部变量，和外面的`num`没有任何联系。

下面给出一个参数作为引用类型的例子。

```js
function box(obj) {            //按值传递，传递的参数是引用类型，但不是按引用传递
    obj.name = 'LEE';
    var obj = new Object();    //所以，JS没有引用传参的功能，切记，不能把传递引用参数当做按引用传参
    obj.name = 'kkk';
}
var obj = new Object();
box(obj);
alert(obj.name);
```
PS: 如果存在按引用传递的话，那么函数里的那个变量将会是全局变量，在外部也可以访问。比如PHP中，必须在参数前面加上&符号表示按引用传递。而ECMAScript没有这些，只能是局部变量。可以在PHP中了解一下。  
PS: 所以按引用传递和传递引用类型是两个不同的概念。

```js
function box(obj) {
    obj.name = 'LEE';
    var obj = new Object();     //函数内部又创建了一个对象
    obj.name = 'Mr.';           //并没有替换掉原来的obj
}
```
最后得出结论，ECMAScript的函数参数都将是局部变量，也就是说，__没有按引用传递__。

##### 检测类型
要检测一个变量的类型，我们可以通过`typeof`运算符来判别。诸如：

```js
var box = 'LEE';
alert(typeof box);               //string
```
虽然`typeof`运算符在检查基本数据类型的时候非常好用，但检测引用类型的时候，它就不是那么好用了。通常，我们并不想知道它是不是对象，而是想知道他到底是什么类型的对象。因为数组也是`object`，`null`也是`Object`等等。  
这时我们应该采用`instanceof`运算符来查看。

```js
var box1 = [1,2,3];
alert(box1 instanceof Array);     //是否是数组
var box2 = {};
alert(box2 instanceof Object);    //是否是对象
var box3 = /g/;
alert(box3 instanceof RegExp);    //是否是正则表达式
var box4 = new String('LEE');
alert(box4 instanceof String);    //是否是字符串对象
```
PS: 当使用`instanceof`检查基本类型的值时，它会返回`false`

##### 执行环境及作用域
执行环境是HavaScript中最为重要的一个概念。执行环境定义了变量或函数有权访问的其他数据，决定了它们各自的行为。  
全局执行环境是最外围的执行环境。在 Web 浏览器中，全局执行环境被认为是`window`对象。因此所有的全局变量和函数都是作为`window`对象的属性和方法创建的。

```js
var box = 'blue';       //声明一个全局变量
function setBox() {
    alert(box);         //全局变量可以在函数里访问
}
setBox();               //执行函数
```
全局的变量和函数，都是`window`对象的属性和方法。

```js
var box = 'blue';
function setBox() {
    alert(window.box);  //全局变量即window的属性
}
window.setBox();        //全局函数即window的方法
```
PS: 当执行环境中的所有代码执行完毕后，该环境被销毁，保存在其中的所有变量和函数定义也随之销毁。如果是全局环境下，需要程序执行完毕，或者网页被关闭才会销毁。  
PS: 每个执行环境（作用域）都有一个与之关联的变量对象，就好比全局的`window`可以调用变量和属性一样。局部的环境也有一个类似`window`的变量对象，环境中的定义的所有变量和函数都保存在这个对象中。（我们无法访问这个变量对象，但解析器会处理数据时后台使用它）

函数里的局部作用域里的变量替换全局变量，但作用域仅限在函数体内这个局部环境。

```js
var box = 'blue';
function setBox() {
    var box = 'red';     //这个是局部变量，它的范围在setBox()里，出来就不认识了，去掉 var 就变成全局变量了
    alert(box);
}
setBox();                //red
alert(box);              //blue

```
通过传参，可以替换函数体内的局部变量，但作用域仅限在函数体内这个局部环境。

```js
var box = 'blue';
function setBox(box) {   //通过传参，也是局部变量，作用域在setBox()范围下
    alert(box);
}
setBox('red');           //red
alert(box);              //blue
```
函数体内还包含着函数，只有这个函数才可以访问内一层的函数。

```js
var box = 'blue';
function setBox() {
    function setColor() {  //setColor()方法的作用域在setBox()内
        return 123;
    }
    return setColor();     //setColor()的执行环境在setBox()内
}
setBox();

var box = 'blue';
function setBox() {
    function setColor() {  //setColor()方法的作用域在setBox()内
        var b = 'orange';  //b 的作用域在setColor()内
        alert(box);
        alert(b);
    }
    setColor();            //setColor()的执行环境在setBox()内
}
setBox();
```
PS: 每个函数被调用时都会创建自己的执行环境。当执行到这个函数时，函数的环境就会被推到环境栈中去执行，而执行后又在环境栈中弹出（退出），把控制权交给上一级的执行环境。  
PS: 当代码在一个环境中执行时，就会形成一种叫做作用域链的东西。它的用途就是保证对执行环境中有访问权限的变量和函数进行有序访问。作用域链的前端，就是执行环境的变量对象。

##### 没有块级作用域
块级作用域表示诸如`if`语句等有花括号封闭的代码块，所以，支持条件判断来定义变量。

```js
if(true) {                      //if语句代码块没有局部作用域
    var box = 'LEE';
}
alert(box);
```
`for`循环语句也是如此

```js
for (var i = 0;i < 10;i++) {    //没有局部作用域
    var box = 'LEE';
}
alert(i);
alert(box);
```
`var`关键字在函数里的区别

```js
function box(num1, num2) {
    var sum = num1 + num2;       //如果去掉 var 就是全局变量
    return sum;
}
alert(box(10,10));
alert(sum);                      //报错
```
PS:非常不建议不使用`var`就初始化变量，因为这种方法会导致各种意外发生。所以初始化变量的时候一定要加上`var`。

一般确定变量都是通过搜索来确定该标识符实际代表什么。

```js
var box = 'blue';
function getBox() {
    return box;                   //代表全局 box
}                                 //如果加上函数体内加上 var box = 'red'
alert(getBox());                  //那么最后返回值就是 red
```
PS: 变量查询中，访问局部变量要比全局变量更快，因为不需要向上搜索作用域链。

<a name="2-内存问题"></a>
#### 2. 内存问题
JavaScript 具有自动垃圾收集机制，也就是说，执行环境会负责管理代码执行过程中使用的内存。其他语言比如 C 和 C++ ，必须手工跟踪内存使用情况，适时的释放，否则会造成很多问题。而 JavaScript 则不需要这样，它会自行管理内存分配及无用内存回收。  
JavaScript 最常用的垃圾收集方式是__标记清除__。垃圾收集器会在运行的时候给存储在内存中的变量加上标记。然后它会去掉环境中正在使用变量的标记，而没有被去掉标记的变量将被视为准备删除的变量。最后，垃圾收集器完成内存清理工作，销毁那些带标记的值并回收他们所占用的内存空间。  
垃圾收集器是周期性运行的，这样会导致整个程序的性能问题。比如IE7以前的版本，它的垃圾收集器是根据内存分配量运行的，比如 256 个变量就开始运行垃圾收集器，这样就不得不频繁地运行，从而降低了性能。  
一般来说，确保占用最少的内存可以让页面获得更好的性能。那么优化内存的最佳方案，就是一旦数据不再有用，那么就将其设置为`null`来释放引用，这个做法叫做解除引用。这以做法适用于大多数全局变量和全局对象。

```js
var o = {
    name : 'LEE'
};
o = null;                  //解除对象引用，等待垃圾收集器回收
```

***

<a name="第13章-基本包装类型"></a>
## 第13章 基本包装类型

为了便于惭怍基本类型值，ECMAScript提供了3个特殊的引用类型：`Boolean`、`Number`、`String`。这些类型与其他引用类型相似，但同时也具有与各自的基本类型相应的特殊行为。实际上，每当读取一个基本类型值的时候，后台就会创键一个对应的基本包装类型的对象，从而能够调用一些方法来操作这些数据。

<a name="1-基本包装类型概述"></a>
#### 1. 基本包装类型概述

```js
var box = 'Mr. LEE';          //定义一个字符串，基本类型
var box2 = box.substring(2);  //截掉字符串前两位，索引0开始，从第2个位置开始截取到末尾的字符串输出
//对象.方法（参数），这种写法明显是引用类型的写法，调用系统内置的方法，称为基本包装类型
alert(box2);                  //输出新字符串
```
变量`box`是一个字符串类型，而`box.substring(2)`
又说明它是一个对象（PS: 只有对象才会调用方法），最后把处理结果赋值给`box2`.`Mr. LEE`是一个字符串类型的值，按道理它不应该是对象，不应该会有自己的方法，比如：

```js
alert('Mr. LEE'.substring(2)); //直接通过值来调用方法
```

```js
字面量写法
var box = 'Mr. LEE';            //字面量
box.name = 'LEE';               //无效属性，给基本类型加属性
box.age = function() {          //无效方法，给基本类型加方法
    return 100;
};
alert(box);                     //Mr.LEE
alert(box.substring(2));        // .LEE
alert(typeof box);              //string
alert(box.name);                //undefined，打印不出来
alert(box.age());               //错误
//基本类型是无法给自己创建属性和方法的，但是可以调用系统内置的属性和方法

new 运算符写法
var box = new String('Mr. LEE');//new 运算符，String的引用类型
box.name = 'LEE';               //有效属性
box.age = function() {          //有效方法操作
    return 100;
};
alert(box);                     //Mr. LEE
alert(box.substring(2));        // .LEE
alert(typeof box);              //object
alert(box.name);                //LEE，自定义属性有效
alert(box.age());               //100，自定义方法有效
```
以上字面量声明和`new`运算符声明很好的展示了他们之间的区别。但有一点还是可以肯定的，那就是不管字面量形式还是`new`运算符形式，都可以使用它的内置方法。并且`Boolean`和`Number`特性与`String`相同，三种类型可以称为基本包装类型。  
PS: 在使用`new`运算符创建以上三种类型的对象时，可以给自己添加属性和方法，但建议不要这样使用，因为这样会导致根本分不清到底是基本类型值还是引用类型值。

<a name="2-boolean-类型"></a>
#### 2. `Boolean` 类型
`Boolean`类型没有特定的属性或者方法。

<a name="3-number-类型"></a>
#### 3. `Number` 类型
`Number`类型有一些静态属性（直接通过`Number`调用的属性，而无须`new`运算符）和方法。

`Number`静态属性

|属性|描述|
|:-:|:-:|
|MAX_VALUE|表示最大数|
|MIN_VALUE|表示最小值|
|NaN|非数值|
|NEGATIVE_INFINITY|负无穷大，溢出返回该值|
|POSITIVE_INFINITY|无穷大，溢出返回该值|
|prototype|原型，用于增加新属性和方法|

`Number`对象的方法

|方法|描述|
|:-:|:-:|
|toString()|将数值转化为字符串，并且可以转换进制|
|toLocaleString()|根据本地数字格式转换为字符串|
|toFixed()|将数字保留小数点后指定位数并转化为字符串，四舍五入|
|toExponential()|将数字以指数形式表示，保留小数点后指定位数并转化为字符串|
|toPrecision()|根据传参来决定指数形式或点形式表述数，保留小数点后面指定位数并转化为字符串|

<a name="4-string-类型"></a>
#### 4. `String` 类型

`String`类型包含了三个属性和大量的可用的内置方法。

String 对象属性

|属性|描述|
|:-:|:-:|
|length|返回字符串的字符长度|
|constructor|返回创建String对象的函数|
|prototype|通过添加属性和方法扩展字符串定义|

`String`也包含对象的通用方法，比如`valueOf()`、`toLocaleString()`和`toString()`方法，但这些方法都返回字符串的基本值。

##### 字符方法
|方法|描述|
|:-:|:-:|
|charAt(n)|返回指定索引位置的字符|
|charCodeAt(n)|以 Unicode 编码形式返回指定索引位置的字符|

```js
var box = 'Mr. LEE';
alert(box.charAt(1));           //r
alert(box.charCodeAt(1));       //114
alert(box[1]);                  //r，通过数组方式截取
```
PS: `box[1]`在IE浏览器会显示`undefined`，所以使用时要慎重。

##### 字符串操作方法
|方法|描述|
|:-:|:-:|
|concat(str1...str2)|将字符串参数串联到调用该方法的字符串|
|slice(n,m)|返回字符串n到m之间位置的字符串|
|substring(n,m)|同上|
|substr(n,m)|返回字符串n开始的m个字符串|

```js
var box = 'Mr.LEE';
alert(box.concat(' is',' Teacher','!'));  //Mr. LEE is Teacher!
alert(box.slice(3));                      //LEE
alert(box.slice(3,5));                    //L
alert(box.substring(3));                  //LEE
alert(box.substring(3,5));                //L
alert(box.substr(3));                     //LEE
alert(box.substr(3,2));                   //L

var box = 'Mr.LEE';
alert(box.slice(-3));                     //LEE，6+(-3)=4 位开始
alert(box.substring(-3));                 //Mr. LEE，负数返回全部字符串
alert(box.substr(-3));                     //LEE，6+(-3)=4 位开始

var box = 'Mr.LEE';
alert(box.slice(3,-1));                   //LE，6+(-1)=5,(3,5)
alert(box.substring(3,-1));               //Mr.，第二参为负，直接转 0，并且方法会把较小的数字提前，(0,3)
alert(box.substr(3,-1));                  //空，第二参数为负，直接转0，(3,0)
```
PS: IE的JavaScript实现在处理向`substr()`方法传递负值的情况下存在问题，它会返回原始字符串，使用时要切记。

##### 字符串位置方法
|方法|描述|
|:-:|:-:|
|indexOf(str,n)|从n开始搜索的第一个str，并将搜索的索引值返回|
|lastIndexOf(str,n)|从n开始搜索的最后一个str，并将搜索的索引值返回|

```js
var box = 'Mr.LEE is LEE';
alert(box.indexOf('L'));             //3
alert(box.indexOf('L',5));           //10
alert(box.lastIndexOf('L'));         //10
alert(box.lastIndexOf('L',5));       //3

PS: 如果没有找到想要的字符串，则返回-1

示例：找出全部的L

var box = 'Mr.LEE is LEE';            //包含两个 L 的字符串
var boxarr = [];                      //存放 L 位置的数组
var pos = box.indexOf('L');           //先获取第一个 L 的位置
while(pos > -1) {                     //如果位置大于 -1，说明还存在 L
    boxarr.push(pos);                 //添加到数组
    pos = box.indexOf('L',pos + 1);   //从新赋值 pos 目前的位置
}
alert(boxarr);                        //输出
```
##### 大小写转换方法
|方法|描述|
|:-:|:-:|
|toLowerCase(str)|将字符串全部转换为小写|
|toUpperCase(str)|将字符串全部转换为大写|
|toLocaleLowerCase(str)|将字符串全部转换为小写，并且本地化|
|toLocaleUpperCase(str)|将字符串全部转换为大写，比且本地化|

```js
var box = 'Mr.Lee is Lee';
alert(box.toLowerCase());
alert(box.toUpperCase());
alert(box.toLocaleLowerCase());
alert(box.toLocaleUpperCase());

PS: 只用几种语言（如土耳其语）具有地方特有的大小写本地性，一般来说，是否本地化效果都是一致的。
```
##### 字符串的模式匹配方法
|方法|描述|
|:-:|:-:|
|match(pattern)|返回pattern中子串或null|
|replace(pattern,replacement)|用replacement替换pattern|
|search(pattern)|返回字符串中pattern开始位置|
|split(pattern)|返回字符串按指定pattern拆分的数组|

正则表达式在字符串中的应用，在前面的章节已经描述探讨过，这里就不再赘述了。  
以上中`match()`、`replace()`、`search()`、`split()`在普通字符串中也可以使用。

```js
var box = 'Mr.Lee is Lee';
alert(box.match('L'));          //L，找到返回L，否则返回null
alert(box.search('L'));         //3,找到L的位置，和indexOf类型
alert(box.replace('L','Q'));    //Mr.Qee is Lee，把L替换成Q
alert(box.split(' '));          //Mr.Lee，is，Lee，以空格分割成字符串
```
##### 其他方法
|方法|描述|
|:-:|:-:|
|fromCharCode(ascii)|静态方法，输出Ascii码对应值|
|localeCompare(str1,str2)|比较两个字符串，并返回相应的值|

    alert(String.fromCharCode(76));    //L，输出Ascii码对应值

localeCompare(str1,str2)方法详解：比较两个字符串并放回一下值中的一个：  
1. 如果字符串在字母表中应该排在字符串参数之前，则返回一个负数。（多数为-1）  
2. 如果字符串等于字符串参数，则返回0  
3. 如果字符串在自附表中应该排在字符串参数之后，则返回一个整数。（多数1）

```js
var box = 'LEE';
alert(box.localeCompare('apple'));    //1，a在l之前
alert(box.localeCompare('LEE'));      //0,一样返回0
alert(box.localeCompare('zoo'));      //-1，z在l之后
```
##### `HTML`方法

|方法|描述|
|:-:|:-:|
|anchor(name)|`<a name="name">str</a>`|
|big()|`<big>str</big>`|
|blink()|`<blink>str</blink>`|
|bold()|`<b>Str</b>`|
|fixed()|`<tt>Str</tt>`|
|fontcolor(color)|`<font color="color">str</font>`|
|fontsize(size)|`<font size="size">str</font>`|
|link(URL)|`<a href="URL">str</a>`|
|small()|`<small>str</small>`|
|strike()|`<strike>str</strike>`|
|italics()|`<i>italics</i>`|
|sub()|`<sub>str</sub>`|
|sup()|`<sup>str</sup>`|

以上是通过JS生成一个html标签，根据经验，没什么太大用处，做个了解。

```js
var box = 'LEE';
alert(box.link('http://'));
```

<a name="第14章-内置对象"></a>
## 第14章 内置对象
ECMAScript对内置对象的定义是：“有ECMAScript实现提供、不依赖宿主环境的对象，这些对象在ECMAScript程序执行之前就已经存在了。”意思就是说，开发人员不必显示地实例化内置对象；因为它们已经实例化了。ECMA-262只定义了两个内置对象：`Global`和`Math`

<a name="1-global-对象"></a>
#### 1. `Global` 对象
`Global`（全局）对象是ECMAScript中一个特别的对象，因为这个对象是不存在的。在ECMAScript中不属于任何其他对象的属性和方法，都属于它的属性和方法。所以，事实上，并不存在全局变量和全局函数；所有在全局作用域定义的变量和函数，都是`Global`对象的属性和方法。  
PS: 因为ECMAScript没有定义怎么调用`Global`对象，所以，`Global.属性`或者`Global.方法()`都是无效的。（Web浏览器将`Global`作为`window`对象的一部分加以实现）

##### `Global`对象有一些内置的属性和方法：
1.`URI`编码方法

`URI`编码可以对链接进行编码，以便发送给浏览器。它们采用特殊的`UTF-8`编码替换所有无效字符，从而让浏览器能够接受和理解。  
`encodeURI()`不会对本身属于`URI`的特殊字符进行编码，例如冒号、正斜杠、问号和#号；而`encodeURIComponent()`则会对它发现的任何非标准字符进行编码

```js
var box = '//Lee 李';
alert(encodeURI(box));            //只编码中文

var box = '//Lee 李';
alert(encodeURIComponent(box));   //特殊字符和中文编码
```
PS: 因为`encodeURIComponent()`编码比`encodeURI()`编码来的更加彻底，一般来说`encodeURIComponent()`使用频率要高一些。

使用了`URI`编码过后，还可以进行编码，通过`decodeURI()`和`decodeURIComponent()`来进行编码

```js
var box = '//Lee 李';
alert(decodeURI(encodeURI(box)));                    //还原
alert(decodeURIComponent(encodeURIComponent(box)));  //还原
```
PS: `URI`方法如上所述的四种，用于代替已经被ECMA-262第3版废弃的`escape()`和`unescape()`方法。`URI`方法能够编码所有的`Unicode`字符，而原来的只能正确地编码`ASCII`字符。所以建议不要再使用`escape()`和`unescape()`方法。

2.`eval()`方法

`eval()`方法主要担当一个字符串解析器的作用，他只接受一个参数，而这个参数就是要执行的JavaScript代码的字符串

```js
eval('var box = 100');        //解析了字符串代码
alert(box);
eval('alert(100)');
eval('function box() {return 123}');
alert(box());
```
`eval()`方法的功能非常强大，但也非常危险。因此使用的时候必须极为谨慎。特别是在用户输入数据的情况下，非常有可能导致程序的安全性，比如代码注入等等。

3.`Global`对象属性

`Global`对象包含了一些属性：`undefined`、`NaN`、`Object`、`Array`、`Function`等等。

```js
alert(Array);                 //返回构造函数
```

4.`window`对象

之前已经说明，`Global`没有办法直接访问，而Web浏览器可以只用`window`对象来实现全局访问。

```js
alert(window.Array);          //返回构造函数
```

<a name="2-math对象"></a>
#### 2. `Math`对象
ECMAScript为保存数学公式和信息提供了一个对象，即`Math`对象。与我们在JavaScript直接编写计算功能相比，`Math`对象提供的计算功能执行起来要快得多。

1.`Math`对象的属性

`Math`对象包含的属性大都是数学计算中可能会用到的一些特殊值。

|方法|描述|
|:-:|:-:|
|Math.E|自然对数的底数，即常量e的值|
|Math.LN10|10的自然对数|
|Math.LN2|2的自然对数|
|Math.LOG2E|以2为底e的对数|
|Math.LOG10E|以10为底e的对数|
|Math.PI|圆周率|
|Math.SQRT1_2|1/2的平方根|
|Math.SQRT2|2的平方根|

2.`min()`和`max()`方法

`Math.min()`用于确定一组数值中的最小值。`Math.max()`用于确定一组数值中的最大值。

```js
alert(Math.min(2,4,3,6,5,8,0,1,3));    //0
alert(Math.max(2,4,3,6,5,8,0,1,3));    //8
```

3.舍入方法

`Math.ceil()`执行向上舍入，即它总是将数值向上舍入为最接近的整数；  
`Math.floor()`执行向下舍入，即它总是将数值向下舍入为最接近的整数；  
`Math.round()`执行标准舍入，即它总是将数值四舍五入为最接近的整数；

4.`random()`方法

`Math.random()`方法返回介于0到1之间随机数，不包括0和1，如果想大于这个范围的话，可以套用一下公式：  
`值 = Math.floor(Math.random() * 总数 + 第一个值)`

```js
alert(Math.floor(Math.random() * 10 + 1));    //随机产生1-10之间的任意数

for (var i = 0;i < 10;i++) {
    document.write(Math.floor(Math.random() * 6 + 5));  //5-10(6+5-1=10)
    document.write('<br />');
}

为了更加方便的传递想要范围，可以写成函数：
function selectFrom(lower,upper) {
    var sum = upper - lower + 1;         //总数=第二个数-第一个数+1
    return Math.floor(Math.random() * sum + lower);
}
```

5.其他方法

|方法|说明|
|:-:|:-:|
|Math.abs(num)|返回num的绝对值|
|Math.exp(num)|返回Math.E的num次幂|
|Math.log(num)|返回num的自然对数|
|Math.pow(num,power)|返回num的power次幂|
|Math.sqrt(num)|返回num的平方根|
|Math.acos(x)|返回x的反余弦值|
|Math.asin(x)|返回x的正余弦值|
|Math.atan(x)|返回x的反正切值|
|Math.atan2(y,x)|返回y/x的反正切值|
|Math.cos(x)|返回x的余弦值|
|Math.sin(x)|返回x的正弦值|
|Math.tan(x)|返回x的正切值|

***

<a name="第15章-面向对象与原型"></a>
## 第15章 面向对象与原型

ECMAScript有两种开发模式：1.函数式（过程化），2.面向对象（OOP）。面向对象的语言有一个标志，那就是类的概念，而通过类可以创建任意多个具有相同属性的方法和对象。但是，ECMAScript没有类的概念，因此它的对象也与基于类的语言中的对象有所不同。

<a name="1-创建对象"></a>
#### 1. 创建对象
```js
var box = new Object();
box.name = 'Lee';
box.age = 100;
box.run = function() {
    return this.name + this.age + 'running...';
};  //this表示当前作用域下的对象，new Object()实例化出来的那个对象
//this要放在一个作用域下，比如box.run(){}，这个box作用域下的方法，方可用this，来表示box本身
alert(box.run());
```
上面创建了一个对象，并且创键属性和方法，在`run()`方法里的`this`，就是代表`box`对象本身。这种是JavaScript创建对象最基本的方法，但有个缺点，想创建一个类似的对象，就会产生大量的代码。  
为了解决多个类似对象声明的问题，我们可以使用一种叫做工厂模式的方法，这种方法就是为了解决实例化对象产生大量重复的问题。

```js
function createObject(name,age) {      //集中实例化的函数
    var obj = new Object();            //创建对象
    obj.name = name;                   //添加属性
    obj.age = age;
    obj.run = function() {             //添加方法
        return this.name + this.age + 'running...';
    };
    return obj;                        //返回对象引用
}
var box1 = createObject('Lee',100);    //创建第一个对象
var box2 = createObject('Tom',200);    //创建第二个对象
alert(box1.run());                     //打印第一个对象实例的run()方法
alert(box2.run());                     //打印第二个对象实例的run()方法
```
工厂模式解决了重复实例化的问题，但还有一个问题，那就是识别问题，因为根本无法搞清楚它们到底是哪个对象的实例。

ECMAScript中可以采用构造函数（构造方法）可用来创建特定的对象。类型于`Object`对象。

```js
function Box(name,age) {               //构造函数模式
    this.name = name;                  //实例属性
    this.age = age;
    this.run = function() {            //实例方法
        return this.name + this.age + 'running...';
    };
};
var box1 = new Box('Lee',100);         //实例化
var box2 = new Box('Tom',200);         //实例化
alert(box1.run());
alert(box2.run());
//1.构造函数没有new Object，但它后台会自动 var obj = new Object()
//2.this 就相当于 obj
//3.构造函数不需要返回对象引用，它是后台自动返回的
alert(box1 instanceof Box);            //true
alert(box2 instanceof Box);            //true
```

使用构造函数的方法，即解决了重复实例化的问题，又解决了对象识别的问题，但问题是，这里并没有`new Object()`，为什么可以实例化`Box()`，这个又是哪里来的呢？  
使用构造函数的方法，和使用工程模式的方法，不同之处如下：

    1.构造函数方法没有显示的创建对象（new Object()）
    2.直接将属性和方法赋给 this 对象
    3.没有 return 语句

构造函数的方法有一些规范：

    1.函数名和实例化构造名相同且大写，（PS: 非强制，但这么写有助于区分构造函数和普通函数）
    2.通过构造函数创建对象，必须使用 new 运算符

既然通过构造函数可以创建对象，那么这个对象是哪里来的，`new Object()`在什么地方执行了？执行的过程如下：

    1.当使用了构造函数，并且 new 构造函数()，那么就后台执行了 new Object()
    2.将构造函数的作用域给新对象，（即 new Object() 创建出的对象），而函数体内的 this 就代表 new Object() 出来的对象
    3.执行构造函数内的代码
    4.返回新对象（后台直接返回）

关于`this`的使用，`this`其实就是代表当前作用域对象的引用。如果在全局范围`this`就代表`window`对象，如果在构造函数体内，就代表当前的构造函数所声明的对象。

>全局变量尽量不用`name`变量名，容易出现问题。

构造函数和普通函数的唯一区别，就是它们调用的方式不同。只不过，构造函数也是函数，必须用`new`运算符来调用，否则就是普通函数。

```js
var box = new Box('Lee',100);    //构造模式调用
alert(box.run());

Box('Lee',20);                   //普通模式调用，无效

var o = new Object();
Box.call(o,'Jack',200);          //对象冒充调用
alert(o,run());
```
探讨构造函数内部的方法（或函数）的问题，首先看下两个实例化后的属性或方法是否相等。

```js
var box1 = new Box('Lee',100);   //实例化后地址为1
var box2 = new Box('Lee',100);   //实例化后地址为2
alert(box1.name == box2.name);   //true，属性的值相等
alert(box1.run == box2.run);     //false，比较的是引用地址
alert(box1.run() == box2.run()); //true，方法的值相等，因为传参一致
```
可以把构造函数里的方法（或函数）用`new Function()`方法来代替，得到一样的效果，更加证明，它们最终判断的是引用地址，唯一性

```js
function Box(name,age) {
    this.name = name;
    this.age = age;
    this.run = new Function(
        "return this.name + this.age + 'running...'"
        );
};
```
我们可以通过构造函数外面绑定同一个函数的方法来保证引用地址的一致性，但这种做法没什么必要，只是加深学习了解：

```js
function Box(name,age) {
    this.name = name;
    this.age = age;
    this.run = run;
};
function run() {     //把构造函数内部的方法通过全局调用，实现引用地址一致
    return this.name + this.age + 'running...'
}
```
虽然使用了全局的函数`run()`来解决了保证引用地址一致的问题，但这种方式又带来了一个新的问题，全局中的`this`在对象调用的时候是`Box`本身，而当做普通函数调用的时候，`this`又代表`window`

<a name="2-原型"></a>
#### 2. 原型
我们创建的每个函数都有一个`prototype`（原型）属性，这个属性是一个对象，它的用途是包含可以特定类型的所有实例共享的属性和方法。逻辑上可以这么理解：`prototype`通过调用构造函数而创建的那个对象的原型对象。使用原型的好处可以让所有对象实例共享它所包含的属性和方法。也就是说，不必在构造函数中定义对象信息，而是可以直接将这些信息添加到原型中。

```js
function Box() {}                  //声明一个构造函数

Box.prototype.name = 'Lee';        //在原型中添加属性
Box.prototype.age = 100;           //原型属性
Box.prototype.run = function() {   //在原型里添加方法
    return this.name + this.age + 'running...';
};
//如果是实例方法，不同的实例化，它们的方法地址是不一样的，是唯一的
//如果是原型方法，那么它们地址是共享的，大家都一样
var box1 = new Box();
var box2 = new Box();
alert(box1.run == box2.run);        //true
```
在原型模式声明中，多了两个属性，这两个属性都是创建对象时自动生成的。  
`__proto__`属性是实例指向原型对象的一个指针，它的作用就是指向构造函数的原型属性`constructor`。通过这两个属性，就可以访问到原型里的属性和方法了。  
PS: IE浏览器在脚本访问`__proto__`会不能识别，火狐和谷歌浏览器及其他某些浏览器均能识别。虽然可以输出，但无法获取内部信息。

```js
alert(box1.prototype);   //这个属性是一个对象，访问不到
alert(box1.__proto__);   //[object Object],这个属性是一个指针指向prototype原型对象
alert(Box.prototype);    //[object Object],使用构造函数名（对象名）访问prototype
alert(box1.constructor); //构造属性，可以获取构造函数本身，
//作用是被原型指针定位，然后得到构造函数本身，其实就对象实例对应的原型对象的作用
```
判断一个对象是否指向了该构造函数的原型对象，可以使用`isPrototypeOf()`方法来测试：

    alert(Box.prototype.isPrototypeOf(box));  //只要实例化对象，即都会指向

原型模式的执行流程：

    1.先查找构造函数实例里的属性或方法，如果有，立刻返回；
    2.如果构造函数实例里没有，则去它的原型对象里找，如果有，就返回；
虽然我们可以通过对象实例访问保存在原型中的值，但却不能访问通过对象实例重写原型中的值。

```js
var box1 = new Box();
alert(box1.name);           //Lee，原型里的值
box1.name = 'Jack';         //实例属性，并没有重写原型属性
alert(box1.name);           //Jack，就近原则

var box2 = new Box();
alert(box2.name);           //Lee，原型里的值，没有被box1修改，实例属性不会共享
```
如果向要`box1`也能在后面继续访问到原型里的值，可以把构造函数里的属性删除即可，具体如下：

```js
delete box1.name;            //删除实例中的属性
alert(box1.name);            //Lee
delete Box.prototype.name;   //删除原型中的属性
Box.prototype.name = 'Tom';  //覆盖原型中的属性
```
如何判断属性是在构造函数的实例里，还是在原型里？可以使用`hasOwnProperty()`函数来判断实例中是否存在指定属性：

    alert(box.hasOwnProperty('name'));  //实例里有返回true，否则返回false

`in`操作符会在通过对象能够访问给定属性时返回`true`，无论该属性存在于实例中还是原型中。

    alert('name' in box);    //true，存在实例中或原型中

我们可以通过`hasOwnProperty()`方法检测属性是否存在实例中，也可以通过`in`来判断实例或原型中存在属性。那么结合两种方法，可以判断原型中是否存在属性。

```js
function isProperty(object,property) {
    return !object.hasOwnProperty(property) && (property in object);
}
var box = new Box();
alert(isProperty(box,'name'));     //true，如果原型有
```
为了让属性和方法更好的体现封装的效果，并且减少不必要的输入，原型的创建可以使用字面量的方式：

```js
function Person() {};    //使用字面量的方式创建原型对象，这里{}就是对象
Person.prototype = {     //是Object，new Object就相当于{}
    name : 'Lee',
    age : 100,
    run : function() {
        return this.name + this.age + 'running...';
    }
};
```
使用构造函数创建原型对象和使用字面量创建对象在使用上基本相同，但还是有一些区别，字面量创建的方式使用`constructor`属性不会指向实例，而会指向`Object`，构造函数创建的方式则相反。

```js
var box = new Box();
alert(box instanceof Box);         //true
alert(box instanceof Object);      //true
alert(box.constructor == Box);     //字面量方式，返回false，否则，true
alert(box.constructor == Object);  //字面量方式，返回true，否则，false
```
如果想让字面量方式的`constructor`指向实例对象，那么可以这么做：

```js
Box.prototype = {
    constructor : Box,             //直接强制指向即可
};
```
PS: 字面量方式为什么`constructor`会指向`Object`？因为`Box.prototype={};`这种写法其实就是创建一个新对象。而每创建一个函数，就会同时创建它的`prototype`，这个对象也会自动获取`constructor`属性。所以，新对象的`constructor`重写了`Box`原来的`constructor`，因此会指向新对象，那个新对象没有指定构造函数，那么就默认为`Object`

原型的声明是有先后顺序的，所以，重写的原型会切断之前的原型

```js
function Box() {};
Box.prototype = {               //原型被重写了
    constructor : Box,
    name : 'Lee',
    age : 100,
    run : function() {
        return this.name + this.age + 'running...';
    }
};
Box.prototype = {
    age : 200       //这里不会保留之前原型的任何信息，把原来的原型对象和构造函数对象实例之间的关系切断了
}
var box = new Box();
alert(box.run());   //run被切断消失了
```
原型对象不仅仅可以在自定义对象的情况下使用，而ECMAScript内置的引用类型都可以使用这种方式，并且内置的引用类型本身也使用了原型。

```js
alert(Array.prototype.sort);              //sort 是Array 类型的原型方法
alert(String.prototype.substring);        //substring 是 String 类型的方法
//内置引用类型的功能扩展
String.prototype.addstring = function() { //给String 类型添加一个方法
    return this + ',被添加了！';           //this 代表调用的字符串
};
alert('Lee'.addstring());                 //使用这个方法
```
PS: 尽管给原生的内置引用类型添加方法使用起来特别方便，但不推荐使用这种方法，因为它可能会导致命名冲突，不利于代码维护

原型模式创建对象也有自己的缺点，它省略了构造函数传参初始化这一过程，带来的缺点就是初始化的值都是一致的。而原型最大的缺点就是它最大的优点，那就是共享。  
原型中所有属性是被很多实例共享的，共享对于函数非常合适，对于包含基本值的属性也还可以。但如果属性包含引用类型，就存在一定问题：

```js
function Box() {};
Box.prototype = {
    constructor : Box,
    name : 'Lee',
    age : 100,
    family : ['father','mother','sister'], //添加一个数组属性
    run : function() {
        return this.name + this.age + this.family;
    }
}
var box1 = new Box();
box1.family.push('brother');               //在实力中添加'brother''
alert(box1.run());

var box2 = new Box();
alert(box2.run());                         //共享带来的麻烦，也有'brother'了
```
PS: 数据共享的缘故导致很多开发者放弃使用原型，因为每次实例化出的数据需要保留自己的特征，而不能共享。

为了解决构造传参和共享问题，可以组合构造函数+原型模式：

```js
function Box(name,age) {        //不共享的使用构造函数
    this.name = name;
    this.age = age;
    this.family = ['father','mother','sister'];
};
Box.prototype = {
    constructor : Box,
    run : function() {          //共享的使用原型模式
        return this.name + this.age + this.family;
    }
};
```
PS: 这种混合模式很好的解决了传参和引用共享的大难题。是创建对象比较好的方法。

原型模式，不管你是否调用了原型中的共享方法，它都会初始化原型中的方法，并且在声明一个对象时，构造函数+原型部分让人感觉又很怪异，最好就是把构造函数和原型封装到一起。为了解决这个问题，我们可以使用__动态原型模式__。

```js
function Box(name,age) {                  //将所有信息封装到函数体内
    this.name = name;
    this.age = age;
    //原型的初始化，只要第一次初始化，
    if(typeof this.run != 'function') {   //仅在第一次调用的初始化
        Box.prototype.run = function() {
            return this.name + this.age + 'running...',
        };
    }
}
var box = new Box('Lee',100);
alert(box.run());
```
当第一次调用构造函数时，`run()`方法发现不存在，然后初始化原型。当第二次调用，就不会初始化，并且第二次创建新对象，原型也不会再初始化了。这样及得到了封装，又实现了原型方法共享，并且属性都保持独立。

PS: 使用动态原型模式，要注意一点，不可以再使用字面量的方式重写原型，因为会切断实例和新原型之间的联系。

以上讲解了各种方式对象创建的方法，如果这几种方式都不能满足需求，可以使用一开始那种模式：寄生构造函数。

```js
function Box(name,age) {
    var obj = new Object();
    obj.name = name;
    obj.age = age;
    obj.run = function() {
        return this.name + this.age + 'running...';
    };
    return obj;
}
```
寄生构造函数，其实就是工厂模式+构造函数模式。这种模式比较通用，但不能确定对象关系，所以，在可以使用之前所说的模式时，不建议使用此模式。

在什么情况下使用寄生构造函数比较合适呢？假设要创建一个具有额外方法的引用类型。由于之前说明不建议直接`String.prototype.addstring`，可以通过寄生构造的方式添加。

```js
function myString(string) {
    var str = new String(string);
    str.addstring = function() {
        return this + '，被添加了！';
    };
    return str;
}
var box = new myString('Lee');      //比直接在引用原型添加要繁琐好多
alert(box.addstring());
```
在一些安全的环境中，比如禁止使用`this`和`new`，这里的`this`是构造函数里不使用`this`，这里的`new`是在外部实例化构造函数时不使用`new`。这种创建方式叫做__稳妥构造函数__。

```js
function Box(name,age) {
    var obj = new Object();
    obj.run = function() {
        return name + age + 'running...';   //直接打印参数即可
    };
    return obj;
}
var box = Box('Lee',100);                    //直接调用函数
alert(box.run());
```
PS: 稳定构造函数和寄生类似。

<a name="3-继承"></a>
#### 3. 继承
继承是面对对象中一个比较核心的概念。其他正统面对对象语言都会用两种方式实现继承：一个是接口实现，一个是继承。而ECMAScript只支持继承，不支持借口实现，而实现继承的方法依靠原型链完成。

```js
function Box() {            //Box 构造，被继承的函数叫做超类型（父类，基类）
    this.name = 'Lee';
}

function Desk() {           //Desk 构造，继承的函数交过子类型（子类，派生类）
    this.age = 100;
}
//通过原型链继承，超类型实例化后的对象实例，赋值给子类型的原型属性
//new Box() 会将 Box 构造里的信息和原型里的信息都交给 Desk
//Desk 的原型得到的是 Box的构造+原型里面的信息
Desk.prototype = new Box(); //Desc 继承了 Box，通过原型，形成链条

var desk = new Desk();
alert(desk.age);
alert(desk.name);           //得到被继承的属性

function Table() {          //Table 构造
    this.level = 'AAAAA';
}

Table.prototype = new Desk();  //继续原型链继承

var table = new Table();
alert(table.name);          //继承了 Box 和 Desk
```
如果要实例化`table`，那么`Desk`实例中有`age = 100`，原型中增加相同的属性`age = 200`，最后结果是多少呢？

```js
Desk.prototype.age = 200;   //实例和原型中均包含age
alert(table.age);           //100,就近原则，实例里有，就返回，没有就去查找原型
```
PS: 以上原型链继承还缺少一环，那就是`Object`，所有的构造函数都继承自`Object`。而继承`Object`是自动完成，并不需要程序程序员手动继承。

经过继承后的实例，它们的从属会怎样呢？

```js
alert(table instanceof Object);    //true，子类型从属于自己或者它的超类型
alert(desk instanceof Tbale);      //false，desk 是 table 的超类
alert(table instanceof Desk);      //true
alert(table instanceof Box);       //true
```
在JavaScript里，被继承的函数称为超类型（父类，基类也行，其他语言叫法），继承的函数称为子类型（子类，派生类）。继承也有之前问题，比如字面量重写原型会中断关系，使用引用类型的原型，并且子类型还无法给超类型传递参数。
为了解决引用共享的超类型无法传参的问题，我们采用一种叫__借用构造函数__的技术，或者称为对象冒充（伪造对象、经典继承）的技术来解决这两种问题。

```js
function Box(age) {
    this.name = ['Lee','Jack','Hello'];   //引用类型，放在构造里就不会被共享
    this.age = age;
}
function Desk(age) {
    Box.call(this,age);             //对象冒充，给超类型传参
}                                   //对象冒充只能继承构造里的信息
var desk = new Desk(200);
alert(desk.age);
alert(desk.name);
desk.name.push('AAA');              //添加的新数据，只给desk
alert(desk.name);
```
借用构造函数虽然解决了刚才两种问题，但没有原型，复用则无从谈起。所以，我们需要原型链+借用构造函数的模式，这种模式称为__组合继承__。

```js
function Box(age) {
    this.name = ['Lee','Jack','Hello'];
    this.age = age;
}

//构造函数里的方法，放在构造里，每次实例化，都会分配一个内存地址，浪费，所以最好放在原型里，保证多次实例化，只有一个地址
Box.prototype.run = function() {
    return this.name + this.age;
}

function Desk(age) {
    Box.call(this,age);          //对象冒充
}

Desk.prototype = new Box();      //原型链继承

var desk = new Desk(100);
alert(desk.run());
```
还有一种继承模式叫做：__原型式继承__：这种继承借助原型并基于已有的对象创建新对象，同时还不必因此创建自定义类型。

```js
//临时中转函数，o 表示将要传递进入的一个对象
function obj(o) {               //传递一个字面量函数
    function F() {}             //创建一个构造函数，F 构造是一个临时新建的对象，用来存储传递过来的对象
    F.prototype = o;            //把 o 对象实例赋值给 F 构造函数的原型
    return new F();             //最终返回这个得到传递过来对象的对象实例
}
//F.prototype = o 其实就相当于 Desk.prototype = new Box();

var box = {                     //字面量的声明方式，相当于 var box = new Box()
    name : 'Lee',
    arr : ['brother','sister','father']
};

var box1 = obj(box);            //传递，box1就等于new F()
alert(box1.arr);
box1.arr.push('mother');
alert(box1.arr);

var box2 = obj(box);
alert(box2.arr);                //引用类型的属性共享了
```
__寄生式继承__把原型式+工厂模式结合而来，目的是为了封装创建对象的过程。

```js
//临时中转函数
function obj(o) {
    function F() {}
    F.prototype = o;
    return new F();
}
//寄生函数
function create(o) {            //封装创建过程
    var f = obj(o);
    f.run = function() {
        return this.arr;        //同样，会共享引用
    };
    return f;
}

var box = {
    name : 'Lee',
    age : 100,
    arr : ['brother','sister','father']
};

var box1 = create(box);
alert(box1.run());
```
__组合式继承__是JavaScript最常用的继承模式；但，组合式继承也有一点小问题，就是超类型在使用工程中会被调用两次：一次是创建子类型的时候，另一次是在子类型构造函数的内部。

```js
function Box(name) {
    this.name = name;
    this.arr = ['brother','sister','parents'];
}

Box.prototype.run = function() {
    return this.name;
};

function Desk(name,age) {
    Box.call(this,name);        //第二次调用Box
    this.age = age;
}

Desk.prototype = new Box();     //第一次调用Box
```
以上代码是之前的组合继承，那么__寄生组合继承__，解决了两次调用的问题。

```js
//临时中转函数
function obj(o) {
    function F() {}
    F.prototype = o;
    return new F();
}
//寄生函数
function create(box,desk) {
    var f = obj(box.prototype);
    f.constructor = desk;          //调整原型构造指针
    desk.prototype = f;
}

function Box(name,age) {
    this.name = name;
    this.age = age;
}

Box.prototype.run = function() {
    return this.name + this.age + 'running...';
}

function Desk(name,age) {
    Box.call(this,name,age);      //对象冒充
}

//通过寄生组合继承来实现继承
create(Box,Desk);                 //这句话用来替代Desk.prototype = new Box();

var desk = new Desk('Lee',100);
alert(desk.run());
alert(desk.constructor);
```

***

<a name="第16章-匿名函数和闭包"></a>
## 第16章 匿名函数和闭包

匿名函数就是没有名字的函数，闭包是可访问一个函数作用域里变量的函数。

<a name="1-匿名函数"></a>
#### 1. 匿名函数

```js
//普通函数
function box() {                   //函数名是box
    return 'Lee';
}

//匿名函数
function () {                      //单独的匿名函数，会报错，无法运行
    return 'Lee';                  //就算能运行，也无法调用，因为没有名称
}

//通过表达式自我执行
(function box() {                  //封装表达式，(匿名函数)()，第一个圆括号放匿名函数，第二个圆括号执行
    alert('Lee');
})();                              //()表达执行函数，并且传参

//把匿名函数赋值给变量
var box = function() {             //将匿名函数赋给变量
    return 'Lee';
};
alert(box());                      //调用方式和函数调用相似

//函数里的匿名函数
function box() {
    return function(){             //函数里的匿名函数，产生闭包
        return 'Lee';
    }
}
alert(box()());                    //调用匿名函数
var b =box();
alert(b());
```

<a name="2-闭包"></a>
#### 2. 闭包
闭包是指有权访问另一个函数作用域中的变量的函数，创建闭包的常见的方式，就是在一个函数内部创建另一个函数，通过另一个函数访问这个函数的局部变量。

```js
//通过闭包可以返回局部变量
function box() {
    var user = 'Lee';
    return function () {           //通过匿名函数返回box()局部变量
        return user;
    };
}
alert(box()());                    //通过box()()来直接调用匿名函数返回值

var b = box();
alert(b());                        //另一种调用匿名函数返回值
```
使用闭包有一个优点，也是它的缺点：就是可以把局部变量主流在内存中，可以避免使用全局变量。（全局变量污染导致应用程序不可预测性，每个模块都可调用必将引来灾难，所以推荐使用私有的，封装的局部变量）。

```js
//通过全局变量来累加
var age = 100;                    //全局变量
function box() {
    age ++;                       //模块级可以调用全局变量，进行累加
}
box();                            //执行函数，累加了
alert(age);                       //输出全局变量

//通过局部变量无法实现累加
function box() {
    var age = 100;
    age ++;                       //累加
    return age;
}
alert(box());                     //101
alert(box());                     //101，无法实现，因为又被初始化了

//使用匿名函数实现局部变量驻留内存中从而累加
function box() {
    var age = 100;
    return function () {
        age++;
        return age;
    };
}
var b = box();
alert(b());                        //101
alert(b());                        //102
b = null;                          //解除引用，等待垃圾回收
```
PS：由于闭包作用域返回的局部变量资源不会立刻销毁回收，所以可能会占用更多的内存。过度使用闭包会导致性能下降，讲义在肥城有必要的时候才使用闭包。

作用域链的机制导致一个问题，在循环中里的匿名函数取得的任何变量都是最后一个值。

```js
//循环里包含匿名函数的取值问题
function box() {
    var arr = [];
    for (var i = 0;i < 5;i++) {
        arr[i] = function() {
            return i;
        };
    }
    return arr;
}
var b = box();                     //得到函数数组
alert(b.length);                   //得到函数集合长度
for(var i = 0;i < b.length;i++) {
    alert(b[i]());                 //输出每个函数的值，都是最后一个值
}
```
上面的例子输出的结果都是5.也就是循环后得到的最大的i值。因为`box()`最终返回`arr`匿名函数数组，`b[0]-b[4]`表示5个循环返回的函数，本以为会按照`0，1，2，3，4`的返回，但结果都是5。而`b[0]-b[4]`的作用域在`box()`内，所以最终得到的i是循环之后的5。

```js
function box() {
    var arr = [];
    for (var i = 0;i < 5;i++) {
        arr[i] = (function(num) {  //自我执行
            return num;
        })(i);                     //并且传参
    }
    return arr;
}
var b = box();
for(var i = 0;i < b.length;i++) {
    alert(b[i]);                   //这里返回的是数组，直接打印即可
}
```
上例中，我们让匿名函数进行自我执行，导致最终返回值给`a[i]`的是数组而不是函数了。最终导致`b[0]-b[4]`中保留了`0,1,2,3，4`的值。

```js
function box() {
    var arr = [];
    for (var i = 0;i < 5;i++) {
        arr[i] = (function(num) {  //闭包可以将变量驻留在内存中
            return function() {
                return num;
            }
        })(i);
    }
    return arr;
}
var b = box();
for (var i = 0;i < b.length;i++) {
    alert(b[i]());
}

//匿名函数去掉括号
function box() {
    var arr = [];
    for (var i = 0;i < 5;i++) {
        arr[i] = function(num) {
            return function() {
                return num;
            }
        }(i);                       //括号中赋值即可去掉之前的括号
    }
    return arr;
}
var b = box();
for (var i = 0;i < b.length;i++) {
    alert(b[i]());
}
```
在上面的例子中，我们通过匿名函数自我执行，立即把结果复制给`a[i]`。每一个`i`，是调用方通过按值传递的，所以最终返回的都是指定的递增的`i`。而不是`box()`函数里的`i`。

关于`this`对象
在闭包中使用`this`对象也可能会导致一些问题，`this`对象是在运行时基于函数的执行环境绑定的，如果`this`在全局范围就是`window`，如果在对象内部就指向这个对象。而闭包却在运行时指向`window`的，因为闭包并不属于这个对象的属性或方法。

```js
var user = 'The Window';

var obj = {
    user : 'The Object',
    getUserFunction : function() {
        return function() {         //闭包不属于obj，里面的this指向window
            return this.user;
        };
    }
};
alert(obj.getUserFunction()());

//对象冒充
alert(obj.getUserFunction().call(obj));

var user = 'The Window';
var obj = {
    user : 'The Object',
    getUserFunction : function() {
        //这里的this作用域是obj
        var that = this;
        return function() {
            //这里的this作用域是window
            return that.user;
        };
    }
};
alert(obj.getUserFunction()());
```

<a name="3-内存泄露"></a>
#### 3. 内存泄露
由于IE的JScript对象和DOM对象使用不同的垃圾收集方式，因此闭包在IE中会导致一些问题。就是内存泄露的问题，也就是无法销毁驻留在内存中的元素。

```js
function box() {
    var oDiv = document.getElementById('oDiv'); //oDiv用完之后一直驻留在内存
    oDiv.onclick = function() {
        alert(oDiv.innerHTML);   //这里用 oDiv 导致内存泄露
    };
}
box();
```
那么在最后应该将oDiv解除引用来避免内存泄露。

```js
function box() {
    var oDiv = document.getElementById('oDiv');
    var test = oDiv.innerHTML;
    oDiv.onclick = function() {
        alert(text);
    };
    oDiv = null;                 //解除引用，等待垃圾回收
}

PS: 如果并没有使用解除引用，那么需要等到浏览器关闭才得以释放。
```

模仿块级作用域
JavaScript没有块级作用域的概念。

```js
function box(count) {
    for (var i = 0;i < count;i++) {}
    alert(i);                    //i不会因为离开了for块就失效
}
box(2);

function box(count) {
    for (var i = 0;i < count;i++) {}
    var i;                       //就算重新声明，也不会影响前面的值
    alert(i);
}
box(2);
```
以上两个例子，说明JavaScript没有块级语句的作用域，`if(){} for(){}`等没有作用域，如果有，出了这个范围i就应该销毁了。就算重新声明同一个变量也不会改变它的值。


JavaScript不会提醒你是否多次声明了同一个变量：遇到这种情况，它只会对后续的声明视而不见（如果初始化了，当然还会执行的）。使用模仿块级作用域可避免这个问题。

```js
//模仿块级作用域（私有作用域）
(function() {
    //这里是块级作用域
})();

//使用块级作用域（私有作用域）改写
function box(count) {
    (function() {                //包含自我执行的匿名函数，就可以实现私有作用域
        for (var i = 0;i < count;i++) {}
    })();                        //出了私有作用域，变量立即被销毁
    alert(i);                    //报错，无法访问
}
box(2);
```
使用了块级作用域（私有作用域）后，匿名函数中定义的任何变量，都会在执行结束时被销毁。这种技术经常在全局作用域中被用在函数外部，从而限制向全局作用域中添加过多的变量和函数。一般来说，我们都应该尽可能少向全局作用域中添加变量和函数。在大型项目中，多人开发的时候，过多的全局变量和函数很容易导致命名冲突，引起灾难性的后果。如果采用块级作用域（私有作用域），每个开发者既可以使用自己的变量，又不必担心搞乱全局作用域。

```js
(function() {
    var box = [1,2,3,4];
    alert(box);                  //box 出来就不认识了
})();
```
在全局作用域中使用块级作用域可以减少闭包占用的内存问题，因为没有指向匿名函数的引用。只要函数执行完毕，就可以立即销毁其作用域链了。

私有变量
JavaScript没有私有属性的概念；所有的对象属性都有公有的。不过，却有一个私有变量的概念。任何在函数中定义的变量，都可以认为是私有变量，因为不能在函数的外部访问这些变量。

```js
function box() {
    var age = 100;              //私有变量，外部无法访问
}
```
而通过函数内部创建一个闭包，那么闭包通过自己的作用域链也可以访问这些变量。而利用这一点，可以创建用于访问私有变量的公有方法。

```js
function Box() {
    var age = 100;              //私有变量
    function run() {            //私有函数
        return 'running...';
    }
    this.get = function() {     //对外公共的特权方法
        return age + run();
    };
}
var box = new Box();
alert(box.get());
```
可以通过构造方法传参来访问私有变量。

```js
function Person(value) {
    var user = value;           //这句其实可以省略
    this.getUser = function() {
        return user;
    };
    this.setUser = function(value) {
        user = value;
    };
}
```
但是对象的方法，在多次调用的时候，会多次创建。可以使用静态私有变量来避免这个问题。

静态私有变量
通过块级作用域（私有作用域）中定义私有变量或函数，同样可以创建对公共的特权方法。

```js
(function() {
    var age = 100;
    function run() {
        return 'running...';
    }
    Box = function() {}                    //构造方法
    Box.prototype.go = function() {        //原型方法
        return age + run();
    };
})();

var box = new Box();
alert(box.go());
```
上面的对象声明，采用的是`Box = function() {}`而不是`function Box() {}`因为如果用后面这种，就变成私有函数了，无法在全局访问到了，所以使用了前面这种。

```js
(function() {
    var user = '';
    Person = function(value) {          //全局构造函数
        user = value;
    };
    Person.prototype.getUser = function() {
        return user;
    };
    Person.prototype.setUser = function(value) {
        user = value;
    }
})();
```
使用了`prototype`导致方法共享了，而`user`也就变成了静态属性了。（所谓静态属性，即共享于不同对象中的属性）。

模块模式
之前采用的都是构造函数的方式来创建私有变量的特权方法。那么对象字面量方式就采用模块模式来创建。

```js
var box = {                         //字面量对象，也是单例对象，单例就是永远只实例化一次
    age : 100,                      //这是公有属性，将要改成私有
    run : function() {              //这是公有函数，将要改成私有
        return 'running...';
    };
};

私有化变量和函数：
var box = function() {
    var age = 100;
    function run() {
        return 'running...';
    }
    return {                        //直接返回对象
        go : function() {
            return age + run();
        }
    };
}();

上面的直接返回对象的例子，也可以这么写：
var box = function() {
    var age = 100;
    function run() {
        return 'running...';
    }
    var obj = {                     //创建字面量对象
        go : function() {
            return age + run();
        }
    };
    return obj;
}();
```
字面量的对象声明，其实在设计模式中可以看做是一种单例模式，所谓单例模式，就是永远保持对象的一个实例。  
增强的模块模式，这种模式适合返回自定义对象，也就是构造函数。

```js
function Desk() {};
var box = function() {
    var age = 100;
    function run() {
        return 'running...';
    }
    var desk = new Desk();         //可以实例化特定的对象
    desk.go = function() {
        return age + run();
    };
    return desk;
}();
alert(box.go());
```

<a name="第17章-bom"></a>
## 第17章 BOM

<a name="1-window对象"></a>
#### 1. `window`对象
* `window`对象是最顶层的对象
* `window`对象有六大属性，这六大属性本身也是对象
* `window`对象旗下的`document`属性，也是对象，并且`document`对象旗下有五大属性
* `document`对象旗下有五大属性又是对象，总结，都是对象

##### 对象的属性和方法
`window`对象有一系列的属性，这些属性本身也是对象

|属性|含义|
|:-:|:-:|
|closed|当窗口关闭时为真|
|defaultStatus|窗口底部状态栏显示的默认状态消息|
|document|窗口中当前显示的文档对象|
|frames|窗口中的框架对象数组|
|history|保存有窗口最近加载的URL|
|length|窗口中的框架数|
|location|当前窗口的URL|
|name|窗口名|
|offscreenBuffering|用于绘制新窗口内容并在完成后赋值已存在的内容，控制屏幕更新|
|opener|打开当前窗口的窗口|
|parent|指向包含另一个窗口的窗口（由框架使用）|
|screen|显示屏幕相关信息，如高度、宽度（以像素为单位）|
|self|指示当前窗口|
|status|描述由用户交互导致的状态栏的临时消息|
|top|包含特定窗口的最顶层窗口（由框架使用）|
|window|指示当前窗口，与self等效|

window对象的方法

|方法|功能|
|:-:|:-:|
|alert(text)|创建一个警告对话框，显示一条信息|
|blur()|将焦点从窗口移除|
|clearInterval(interbal)|清楚之前设置的定时器间隔|
|clearTimeOut(timer)|清楚之前设置的超时|
|close()|关闭窗口|
|confirm()|创建一个需要用户确认的对话框|
|focus()|将焦点移至窗口|
|open(url,name,[options])|打开一个新窗口并返回新window对象|
|prompt(text,defaultInput)|创建一个对话框要求用户输入信息|
|scroll(x,y)|在窗口中滚动到一个像素点的位置|
|setInterval(expression,milliseconds)|经过指定时间间隔计算一个表达式|
|setInterval(function,milliseconds,[arguments])|经过指定时间间隔后调用一个函数|
|setTimeout(expression,milliseconds)|在定时器超过后计算一个表达式|
|setTimeout(expression,milliseconds,[arguments])|在定时器超过后计算一个函数|
|print()|调出打印对话框|
|find()|调出查找对话框|

`window`的属性和方法的调用：`window.属性`，`window.方法()`，也可以直接`属性`，`方法()`  
如果是某个浏览器独有的属性或者方法，那么在其他浏览器可能会不识别，当做普通变量或者当做普通函数

    closed = '123';               //如果有浏览器不认识，就当做变量了
    强制性的操作
    window.closed;                //强制性

##### 系统对话框
浏览器通过`alert()`、`confirm()`、和`prompt()`方法可以调用系统对话框向用户显示信息。系统对话框与浏览器中显示的网页没有关系，也不包含HTML。

```js
//弹出警告
alert('Lee');                        //直接弹出警告

//确定和取消
confirm('请确定或者取消');             //这里按哪个都无效
if(confirm('请确定或者取消')){         //confirm本身有返回值
    alert('您按了确定！');             //按确定返回true
}else{
    alert('您按了取消！');             //按取消返回false
}

//输入提示框
var num = prompt('请输入一个数字',0);  //两个参数，一个提示，一个值，返回输入的值
alert(num);                          //返回值可以得到

//调出打印及查找对话框
print();                             //打印
find();                              //查找

defaultStatus = '状态栏默认文本';      //浏览器底部状态栏初始默认值
status = '状态栏文本';                //浏览器底部状态栏设置值
```

##### 新建窗口
使用`window.open()`方法可以导航到一个特定的URL，也可以打开一个新的浏览器窗口，它可以接受四个参数：1.要加载的URL；2.窗口的名称或窗口目标；3.一个特性字符串；4.一个表示新页面是否取代浏览器记录中当前加载页面的布尔值。

```js
open('https://www.baidu.com/');            //新建页面并打开百度
open('https://www.baidu.com/','baidu');    //新建页面并命名窗口，打开百度
open('https://www.baidu.com/','_parent');  //在本页窗口打开百度，_blank是新建
```
PS: 不命名会每次打开新窗口，命名的第一次打开新窗口，之后在这个窗口中加载。窗口目标是提供页面的打开的方式，比如本页面，还是新建。

第三字符串参数

|设置|值|说明|
|:-:|:-:|:-:|
|width|数值|新窗口的宽度，不能小于100|
|height|数值|新窗口的高度，不能小于100|
|top|数值|新窗口的Y坐标，不能是负值|
|left|数值|新窗口的X坐标，不能是负值|
|location|yes或no|是否在浏览器窗口中显示地址栏，不同浏览器默认值不同|
|menubar|yes或no|是否在浏览器窗口显示菜单栏，默认为no|
|resizable|yes或no|是否可以通过拖动浏览器窗口的边框改变大小，默认为no|
|scrollbars|yes或no|如果内容在页面中显示不下，是否允许滚动，默认为no|
|status|yes或no|是否在浏览器窗口显示状态栏，默认为no|
|toolbar|yes或no|是否在浏览器窗口显示工具栏，默认为no|
|fullscreen|yes或no|浏览器窗口是否最大化，仅限IE|

```js
//第三参数字符串
open('https://www.baidu.com/','baidu','width=400,height=400,top=200,left=200,toolbar=yes');

//open本身返回window对象
var box = open();
box.alert('');              //可以指定弹出的窗口执行alert();

//子窗口操作父窗口
document.onclick = function() {
    opener.document.write('子窗口让我输出的！');
}
```

##### 窗口的位置和大小
```js
//跨浏览器的方法
var leftX = (typeof screenLeft == 'number') ? screenLeft : screenX;
var topY = (typeof screenTop == 'number') ? screenTop : screenY;

alert(innerWidth);         //页面长度
alert(innerHeight);        //页面高度
alert(outerWidth);         //页面长度+边框
alert(outerHeight);        //页面高度+边框

PS: 在 Chrome 中，innerWidth = outerWidth、innerHeight = outerHeight;
```

##### 间歇调用和超时调用
JavaScript是单线程语言，但它允许通过设置超时值和间歇时间值来调度代码在特定的时刻执行。前者在指定的时间过后执行代码，而后者则是每隔指定的时间就执行一次代码。  
超时调用需要使用`window`对象的`setTimeout()`方法，它接受两个参数：要执行的代码和毫秒数的超时时间。

```js
//setTimeout第一个参数可以是字符串，而里面可以是代码块，因为它有解析功能，所以引号里面还是可以执行
setTimeout("alert('Lee')",1000);        //不建议直接使用字符串

function box() {
    alert('Lee');
}
setTimeout(box,1000);                   //直接传入函数名即可

setTimeout(function() {                 //推荐做法
    alert('Lee');
},1000);

PS: 直接使用函数传入的方法，扩展性好，性能更佳。
```
调用`setTimeout()`之后，该方法会返回一个数值ID，表示超时调用。这个超时调用的ID是计划执行代码的唯一标识符，可以通过它来取消超时调用。  
要取消尚未执行的超时调用计划，可以调用`clearTimeOut()`方法并将相应的超时调用ID作为参数传递给它。

```js
var box = setTimeout(function() {       //把超时调用的ID复制给box
    alert('Lee');
},1000);

clearTimeout(box);                      //把ID传入，取消超时调用
```
间歇调用与超时调用类似，只不过它会按照指定的时间间隔重复执行代码，直至间歇调用被取消或者页面被卸载。设置间歇调用的方法是`setInterval()`，它接受的参数与`setTimeout()`相同：要执行的代码和每次执行之前需要等待的毫秒数。

```js
setInterval(function() {                //间歇调用，重复不停执行
    alert('Lee');
},1000);
```
取消间歇调用方法和取消超时调用类似，使用`clearInterval()`方法。但取消间歇调用的重要性要远远高于取消超时调用，因为在不加干涉的情况下，间歇调用将会一直执行到页面关闭。

```js
var box = setInterval(function() {      //获取间歇调用的ID
    alert('Lee');
},1000);

clearInterval(box);                     //取消间歇调用
```
但上面的代码是没有意义的，我们需要一个能设置5秒的定时器，需要如下代码：

```js
var num = 0;                    //设置起始秒
var max = 5;                    //设置最终秒
var id = null;

function box() {                //间歇调用
    num++;                      //递增num
    if(num == max) {            //如果得到5秒
        clearInterval(id);      //取消间歇调用
        alert('5秒后弹窗！');
    }
}

id = setInterval(box,1000);
```
一般认为，使用超时调用来模拟间歇调用是一种最佳模式。在开发环境下，很少使用真正的间歇调用，因为需要根据情况来取消ID，并且可能造成同步的一些问题，我们建议不使用间歇调用，而去使用超时调用。

```js
var num = 0;
var max = 5;
function box() {
    num++;
    if(num == max) {
        alert('5秒后结束!');
    }else{
        setTimeout(box,1000);
    }
}
setTimeout(box,1000);         //执行定时器
```
PS: 在使用超时调用时，没必要跟踪超时调用ID，因为每次执行代码之后，如果不再设置另一次超时调用，调用就会自行停止。

<a name="2-location对象"></a>
#### 2. `location`对象
`location`是BOM对象之一，它提供了与当前窗口中加载的文档有关的信息，还提供了一些导航功能。事实上，`location`对象是`window`对象的属性，也是`document`对象的属性；所以`window.location`和`document.location`等效。

    alert(location);        //获取当前页面URL

|属性|描述的URL内容|
|:-:|:-:|
|hash|如果该部分存在，表示锚点部分|
|host|主机名：端口号|
|hostname|主机名|
|href|整个URL|
|pathname|路径名|
|port|端口号|
|protocol|协议部分|
|search|查询字符串|

location对象的方法

|方法|功能|
|:-:|:-:|
|assign()|跳转到指定页面，与href等效|
|reload()|重载当前URL|
|replace()|用新的URL替换当前页面|

```js
location.hash = '#1';               //设置#后的字符串，并跳转
alert(location.hash);               //获取#后的字符串

location.port = 8888;               //设置端口号，并跳转
alert(location.port);               //获取当前端口号

location.hostname = 'Lee';          //设置主机名，并跳转
alert(location.hostname);           //获取当前主机名

location.pathname = 'Lee';          //设置当前路径，并跳转
alert(location.pathname);           //获取当前路径

location.protocol = 'ftp';          //设置协议，并跳转
alert(location.protocol);           //获取当前协议

location.search = '?id=5';          //设置?后的字符串，并跳转，死循环
alert(location.search);             //获取?后的字符串

location.href = 'http://www.baidu.com';    //设置跳转的URL，并跳转
alert(location.href);               //获取当前的URL

在WEB开发中，我们经常需要获取诸如 ?id=5&search=ok 这种类型的URL的键值对，那么通过location，我们可以写一个函数，来一一获取。

function getArgs() {
    //创建一个存放键值对的数组
    var args = [];
    //去除?号
    var qs = location.search.length > 0?location.search.substring(1):'';
    //按&字符串拆分数组
    var items = qs.split('&');
    var item = null,name = null,value = null;
    //遍历
    for(var i = 0;i < items.length;i++) {
        item = items[i].split('=');
        name = item[0];
        value = item[1];
        //把键值对存放到数组中去
        args[name] = value;
    }
    return args;
}
var args = getArgs();
alert(args['id']);
alert(args['search']);

location.assign('http://www.baidu.com');  //跳转到指定的URL

location.reload();                        //最有效的重新加载，有可能从缓存加载
location.reload(true);                    //强制加载，从服务器源头重新加载

location.replace('http://www.baidu.com'); //可以避免产生跳转前的历史记录
```

<a name="3-history对象"></a>
#### 3. `history`对象
`history`对象是`window`对象的属性，它保存着用户上网的记录，从窗口被打开的那一刻算起。

`history`对象的属性

|属性|描述URL中的哪部分|
|:-:|:-:|
|length|history对象中记录数|

`history`对象的方法

|属性|描述URL中的哪部分|
|:-:|:-:|
|back()|前往浏览器历史目前一个URL，类似后退|
|forward()|前往浏览器历史目下一个URL，类似前进|
|go(num)|浏览器在history对象中向前或向后|

***

<a name="第18章-浏览器检测"></a>
## 第18章 浏览器检测

<a name="1-navigator对象"></a>
#### 1. `navigator`对象
`navigator`对象的属性或方法

##### 浏览器及版本号
不同的浏览器支持的功能、属性和方法各有不同。

```js
alert('浏览器名称：'+ navigator.appName);         //不能精确的取到浏览器名称
alert('浏览器版本：'+ navigator.appVersion);
alert('浏览器用户代理字符串：'+ navigator.userAgent);  //表示浏览器信息
alert('浏览器所在的系统：'+ navigator.platform);
```

##### 浏览器嗅探器
##### 检测插件
插件是一类特殊的程序，它可以扩展浏览器的功能，通过下载安装完成。比如，在线音乐、视频动画等等插件。  
`navigator`对象的`plugins`属性，这是一个数组。存储在浏览器已安装插件的完整列表。

```js
for(var i = 0;i < navigator.plugins.length;i++) {
    document.write('插件名： ' + navigator.plugins[i].name + '<br />');
    document.write('文件名： ' + navigator.plugins[i].filename + '<br />');
    document.write('描述： ' + navigator.plugins[i].description + '<br />');
    document.write('br /');
}
```
##### `ActiveX`
```js
function hasIEPlugins(name) {
    try {         //这里叫做尝试着去执行一段代码，如果有误，就去执行catch
        new ActiveXObject(name)     //这里的name必须是空间的唯一标识符ID
        return true;        //如果new成功了，没有产生错误，那么就不去执行catch
    }catch(e){
        return false;       //如果new失败了，就执行catch里面的语句
    }
}
```

<a name="2-客户端检测"></a>
#### 2. 客户端检测
客户端检测一共分为三种，分别为：能力检测、怪癖检测和用户代理检测，通过这三种检测方案，我们可以充分的链接当前浏览器所处系统、所支持的语法、所具有的特殊性能。


<a name="第29章-cookie与存储"></a>
## 第29章 `Cookie`与存储

```js
//向本地磁盘写入cookie
ducument.cookie = 'user = Godi13';
alert(document.cookie);

//PS: 本地不存在域名，所以域就为空

//编码
document.cookie = 'user=' + encodeURIComponent('Godi13');
alert(decodeURIComponent(document.cookie));

//完整形式
documeng.cookie = 'user=值; [expires=失效时间; path=路径访问; domain=域名访问; secure=安全的https限制通信]'

//手动删除cookie的方法：设置当前时间为之前的时间，即可
var date = new Date();
date.setDate(date.getDate() - 1);  //真正的删除
document.cookie = 'user=' + encodeURIComponent('Godi13') + ';expires =' + date;

//另一种删除的方法
document.cookie = 'user=' + encodeURIComponent('Godi13') + ';expires =' + new Date(0);

PS: 设置域名，必须在当前域名绑定的服务器上设置，如果在服务器上随意设置其他域名，则会无法创建cookie
```
