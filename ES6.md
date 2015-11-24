<!-- MarkdownTOC -->

- [ECMAScript2015](#ecmascript2015)
  - [作用域](#作用域)
    - [`let` 块作用域](#let-块作用域)
    - [`const` 恒量](#const-恒量)
  - [解构](#解构)
    - [`Array Destructuring` 解构数组](#array-destructuring-解构数组)
    - [`Object Destructuring` 解构对象](#object-destructuring-解构对象)
  - [字符串模板](#字符串模板)
    - [`Template Sreings` 模板字符串](#template-sreings-模板字符串)
    - [`Tagged Templates` 带标签的模板字符串](#tagged-templates-带标签的模板字符串)
    - [判断字符串里是否包含其他的字符串](#判断字符串里是否包含其他的字符串)
  - [函数](#函数)
    - [`Default Parameter Values` 默认参数](#default-parameter-values-默认参数)
    - [`Spread` 展开操作符](#spread-展开操作符)
    - [`Rest` 剩余操作符](#rest-剩余操作符)
    - [`Destructured Parameters` 解构参数](#destructured-parameters-解构参数)
    - [`name` 函数的名字](#name-函数的名字)
    - [`Arrow Functions` 箭头函数](#arrow-functions-箭头函数)
  - [对象](#对象)
    - [对象表达式](#对象表达式)
    - [对象属性名](#对象属性名)
    - [`Object.is()` 对比两个值是否相等](#objectis-对比两个值是否相等)
    - [`Object.assign()` 把对象的值复制到另一个对象里](#objectassign-把对象的值复制到另一个对象里)
    - [`Object.setPrototypeOf()` 设置对象的 prototype](#objectsetprototypeof-设置对象的-prototype)
    - [`__proto__`](#__proto__)
    - [`super`](#super)
  - [生成器与迭代器](#生成器与迭代器)
    - [`Iterators` 迭代器](#iterators-迭代器)
    - [`Generators` 生成器](#generators-生成器)
  - [类](#类)
    - [`Classes` 类](#classes-类)
    - [`get` 与 `set`](#get-与-set)
    - [`static` 静态方法](#static-静态方法)
    - [`extends` 继承](#extends-继承)
  - [集合](#集合)
    - [`Set`](#set)
    - [`Map`](#map)
  - [模块](#模块)
    - [`Modules` 模块](#modules-模块)
    - [重命名到处与导入的东西](#重命名到处与导入的东西)
    - [导出与导入默认](#导出与导入默认)

<!-- /MarkdownTOC -->

<a name="ecmascript2015"></a>
# ECMAScript2015

***

<a name="作用域"></a>
## 作用域
<a name="let-块作用域"></a>
#### `let` 块作用域

```js
if (true) {
  let fruit = 'apple';
}
console.log(fruit);        //无法访问
```

<a name="const-恒量"></a>
#### `const` 恒量

```js
const fruit = 'apple';
console.log(fruit);       //'apple'
const fruit = 'banana';
console.log(fruit);       //error

const fruit = [];
fruit.push('apple');
fruit.push('banana');
console.log(fruit);       //['apple','banana']
fruit = [];
console.log(fruit);       //error
```

***

<a name="解构"></a>
## 解构
<a name="array-destructuring-解构数组"></a>
#### `Array Destructuring` 解构数组

```js
//之前的方法
function fruit() {
  return ['apple','banana','orange'];
}
var tmp = fruit(),
    a = tmp[0], b = tmp[1], c = tmp[2];
console.log(a,b,c);

//ES6
function fruit() {
  return ['apple','banana','orange'];
}
let [a,b,c] = fruit();   //firefox 支持这种写法 chrome 不支持
console.log(a,b,c);
```

<a name="object-destructuring-解构对象"></a>
#### `Object Destructuring` 解构对象

```js
function fruit() {
  return {a:'apple', b:'banana', c:'orange'};
}
let {a: a, b: b, c: c} = fruit();
console.log(a,b,c);      //firefox 支持这种写法 chrome 不支持
```

***

<a name="字符串模板"></a>
## 字符串模板
<a name="template-sreings-模板字符串"></a>
#### `Template Sreings` 模板字符串

```js
//之前的写法
var a = 'apple', b = 'banana';
var fruit = '这的水果有' + a + '和' + b;
console.log(fruit);

//ES6
//chrome
var a = 'apple', b = 'banana';
var fruit = `这的水果有 ${a} 和 ${b}`;
console.log(fruit);
//firefox
let a = 'apple', b = 'banana';
let fruit = `这的水果有 ${a} 和 ${b}`;
console.log(fruit);
```

<a name="tagged-templates-带标签的模板字符串"></a>
#### `Tagged Templates` 带标签的模板字符串

```js
//firefox
let a = 'apple', b = 'banana';
let fruit = tagged`这的水果有 ${a} 和 ${b}`;

function tagged(strings,...values) {
  //console.log(strings);   //Array [ "这的水果有 ", " 和 ", "" ]
  //console.log(values);    //Array [ "apple", "banana" ]
  let result = '';
  for (var i = 0; i < values.length; i++) {
    result += strings[i];
    result += values[i];
  }
  result += strings[strings.length - 1];
  return result;
}
console.log(fruit);     //这的水果有 apple 和 banana
```

<a name="判断字符串里是否包含其他的字符串"></a>
#### 判断字符串里是否包含其他的字符串

```js
let a = 'apple', b = 'banana';
let fruit = `这的水果有 ${a} 和 ${b}`;

console.log(fruit.startsWith('这'));    //true 以'这'开头
console.log(fruit.endsWith('a'));       //true 以'a'结尾
console.log(fruit.includes('apple'));   //true 包含'apple'
```

***

<a name="函数"></a>
## 函数
<a name="default-parameter-values-默认参数"></a>
#### `Default Parameter Values` 默认参数

```js
function fruit(a = 'apple', b = 'banana') {
  return `${a} ${b}`;
}
console.log( fruit() );       //apple banana
console.log( fruit('orange','peach') );   //orange peach
```

<a name="spread-展开操作符"></a>
#### `Spread` 展开操作符

```js
let fruit = [ 'apple', 'banana'],
    shop = ['orange', ...fruit];


console.log(fruit);       //[ "apple", "banana" ]
console.log(...fruit);    //apple banana
console.log(shop);        //Array [ "orange", "apple", "banana" ]
```

<a name="rest-剩余操作符"></a>
#### `Rest` 剩余操作符

```js
function fruit(a, b, ...shop) {
  console.log(a, b, shop);   // apple banana Array [ "orange", "peach" ]
  console.log(a, b, ...shop);   //apple banana orange peach
}  //表示除了参数 a b 以外 剩余参数将放入 shop 数组中
fruit('apple','banana','orange','peach');
```

<a name="destructured-parameters-解构参数"></a>
#### `Destructured Parameters` 解构参数

```js
function fruit(a,b, {c,d} = {}) {
  console.log(a,b,c,d);     //apple banana orange peach
}
fruit('apple','banana',{c:'orange',d:'peach'});
```

<a name="name-函数的名字"></a>
#### `name` 函数的名字

```js
function fruit() {}
console.log(fruit.name);       //fruit

let fruit = function() {}
console.log(fruit.name);       //fruit

let fruit = function shop() {}
console.log(fruit.name);       //shop
```

<a name="arrow-functions-箭头函数"></a>
#### `Arrow Functions` 箭头函数

```js
let fruit = (a, b) => a + b;
//等同于
var fruit = function fruit(a,b) {
  return a + b;
};
```

***

<a name="对象"></a>
## 对象
<a name="对象表达式"></a>
#### 对象表达式

```js
//之前
let a = 'apple', b = 'banana';
let fruit = {
  a: a,
  b: b,
  c: function() {}
};
console.log(fruit);  // Object { a: "apple", b: "banana", c: fruit.c() }

//ES6
let a = 'apple', b = 'banana';
let fruit = {
  a,
  b,
  c() {}
};
console.log(fruit);  // Object { a: "apple", b: "banana", c: c() }
```

<a name="对象属性名"></a>
#### 对象属性名

```js
let fruit = {};
let d = 'e f';

fruit.a = 'apple';
fruit['b c'] = 'banana';    //中间包含空格的写法
fruit[d] = 'orange';

console.log(fruit);  // Object { a: "apple", b c: "banana", e f: "orange" }
```

<a name="objectis-对比两个值是否相等"></a>
#### `Object.is()` 对比两个值是否相等

```js
+0 == -0      //true
+0 === -0     //true
NaN == NaN    //false

Object.is(NaN,NaN)    //true
Object.is(+0,-0)      //false
```

<a name="objectassign-把对象的值复制到另一个对象里"></a>
#### `Object.assign()` 把对象的值复制到另一个对象里

```js
let fruit = {};

Object.assign(
  fruit,                //目标
  {a: 'apple'},
  {a: 'banana'}         //会覆盖掉 'apple' 值
);
console.log(fruit);     //Object { a: "banana" }
```

<a name="objectsetprototypeof-设置对象的-prototype"></a>
#### `Object.setPrototypeOf()` 设置对象的 prototype

```js
let breakfast = {
  getDrink() {
    return 'tea';
  }
};

let dinner = {
  getDrink() {
    return 'beer';
  }
};

let sunday = Object.create(breakfast);
console.log(sunday.getDrink());     //tea
console.log(Object.getPrototypeOf(sunday) === breakfast); //true

Object.setPrototypeOf(sunday, dinner);
console.log(sunday.getDrink());     //beer
console.log(Object.getPrototypeOf(sunday) === dinner);    //true
```

<a name="__proto__"></a>
#### `__proto__`

```js
let breakfast = {
  getDrink() {
    return 'tea';
  }
};

let dinner = {
  getDrink() {
    return 'beer';
  }
};

let sunday = {
  __proto__: breakfast
};

console.log(sunday.getDrink());     //tea
console.log(Object.getPrototypeOf(sunday) === breakfast); //true
sunday.__proto__ = dinner;
console.log(sunday.getDrink());     //beer
console.log(Object.getPrototypeOf(sunday) === dinner);    //true
```

<a name="super"></a>
#### `super`

```js
let breakfast = {
  getDrink() {
    return 'tea';
  }
};

let sunday = {
  __proto__: breakfast,
  getDrink() {
    return super.getDrink() + 'milk';
  }
};

console.log(sunday.getDrink());    // tea milk
```

***

<a name="生成器与迭代器"></a>
## 生成器与迭代器
<a name="iterators-迭代器"></a>
#### `Iterators` 迭代器

```js
function shop(fruits) {
  let i = 0;

  return {
    next() {
      let done = (i >= fruits.length);
      let value = !done ? fruits[i++] : undefined;

      return {
        value: value,
        done: done
      }
    }
  }
}

let buy = shop(['apple','banana']);
console.log(buy.next()); //Object { value: "apple", done: false }
console.log(buy.next()); //Object { value: "banana", done: false }
console.log(buy.next()); //Object { value: undefined, done: true }
```

<a name="generators-生成器"></a>
#### `Generators` 生成器

```js
function* shop() {
  yield 'apple';
  yield 'banana';
}
let buy = shop();
console.log(buy.next()); //Object { value: "apple", done: false }
console.log(buy.next()); //Object { value: "banana", done: false }
console.log(buy.next()); //Object { value: undefined, done: true }

function* shop(fruits) {  //let shop = function*(fruits) {
  for (var i = 0; i < fruits.length; i++) {
    yield fruits[i];
  }
}
let buy = shop(['apple','banana']);
console.log(buy.next()); //Object { value: "apple", done: false }
console.log(buy.next()); //Object { value: "banana", done: false }
console.log(buy.next()); //Object { value: undefined, done: true }
```

***

<a name="类"></a>
## 类
<a name="classes-类"></a>
#### `Classes` 类

```js
class Shop {
  constructor(fruit) {
    this.fruit = fruit;
  }
  buy() {
    console.log(this.fruit);
  }
}
let eat = new Shop('apple');
eat.buy();      //apple
```

<a name="get-与-set"></a>
#### `get` 与 `set`

```js
class Shop {
  constructor(fruit) {
    this.fruit = fruit;
    this.food = [];
  }

  get menu() {
    return this.food;
  }

  set menu(food) {
    this.food.push(food);
  }

  buy() {
    console.log(this.fruit);
  }
}
let eat = new Shop();
console.log(eat.menu = 'apple');   //apple
console.log(eat.menu = 'orange');  //orange
console.log(eat.menu);             //apple orange
```

<a name="static-静态方法"></a>
#### `static` 静态方法

```js
class Shop {
  constructor(fruit) {
    this.fruit = fruit;
    this.food = [];
  }

  get menu() {
    return this.food;
  }

  set menu(food) {
    this.food.push(food);
  }

  static buy(fruit) {
    console.log(fruit);
  }
}
//由于是静态方法，不需要实例化即可使用
Shop.buy('apple');    //apple
```

<a name="extends-继承"></a>
#### `extends` 继承

```js
class Person {
  constructor(name,birthday) {
    this.name = name;
    this.birthday = birthday;
  }

  intro() {
    return `${this.name}, ${this.birthday}`;
  }
}

class Shop extends Person {
  constructor(name,birthday) {
    super(name,birthday);
  }
}

let Lee = new Person('Lee','1988-10-01');
console.log(Lee.intro());
```

***

<a name="集合"></a>
## 集合
<a name="set"></a>
#### `Set`
与数组的不同在于，不能包含重复的内容

```js
let desserts = new Set('apple');
console.log(desserts);      //Set [ "a", "p", "l", "e" ]

desserts.add('s');
console.log(desserts);      //Set [ "a", "p", "l", "e", "s"]
console.log(desserts.size);       //5
console.log(desserts.has('s'));   //true
desserts.delete('s');
console.log(desserts);      //Set [ "a", "p", "l", "e" ]

desserts.forEach(dessert => {
  console.log(dessert);     //a p l e
});
desserts.clear();
console.log(desserts);      //Set []
```

<a name="map"></a>
#### `Map`

```js
let food = new Map();
let fruit = {}, cook = function() {}, dessert = '吃的';

food.set(fruit,'apple');
food.set(cook,'knife');
food.set(dessert,'cake');

console.log(food);      //Map { Object: "apple", cook(): "knife", 吃的: "cake" }
console.log(food.size);          //3
console.log(food.get(fruit));    //apple
food.delete(dessert);
console.log(food.has(dessert));  //false

food.forEach((value, key) => {
  console.log(`${key} = ${value}`);
});     //[object Object] = apple    function () {} = knife

food.clear();                     //全部清空
console.log(food);                //Map { }
```

***

<a name="模块"></a>
## 模块
<a name="modules-模块"></a>
#### `Modules` 模块

```js
//modules.js
let a, b;
export {a,b};

//script/js
import * as modules from './modules';

console.log(modules.a, modules.b);
```

<a name="重命名到处与导入的东西"></a>
#### 重命名到处与导入的东西

```js
//modules.js
let a = 'apple', b = 'banana';
function dinner(a, b) {
  console.log(`${a} and ${b}`);
}
export {a, b, dinner as supper};

//script/js
import {a, b, supper as dinner} from './modules';

dinner(a, b);
```

<a name="导出与导入默认"></a>
#### 导出与导入默认

```js
//modules.js
let a = 'apple', b = 'banana';

export default function dinner(a, b) {    //默认导出
  console.log(`${a} and ${b}`);
}

//script/js
import supper from './modules';    //导入默认不需要{},且可以自定义名称

supper('apple', 'banana');
```

```js
//modules.js
let a = 'apple', b = 'banana';

function dinner(a, b) {    //默认导出
  console.log(`${a} and ${b}`);
}

export {dinner as default};

//script/js
import supper from './modules';    //导入默认不需要{}

supper('apple', 'banana');
```
