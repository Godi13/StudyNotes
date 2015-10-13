# 索引

<!-- MarkdownTOC -->

- [React 学习笔记](#react-学习笔记)
  - [1. React 基本写法](#1-react-基本写法)
  - [2. JSX 介绍](#2-jsx-介绍)
  - [3. JSX 语法](#3-jsx-语法)
    - [四种条件判断方式](#四种条件判断方式)
    - [万能的函数表达式](#万能的函数表达式)
  - [4. 非DOM属性](#4-非dom属性)
  - [5. JSX解释器架构介绍](#5-jsx解释器架构介绍)
    - [源码阅读方法](#源码阅读方法)
    - [理解解释器架构](#理解解释器架构)
  - [6. 组件的生命周期详解](#6-组件的生命周期详解)

<!-- /MarkdownTOC -->

<a name="react-学习笔记"></a>
# React 学习笔记
>总结自[极客学院-ReactJS](http://www.jikexueyuan.com/course/reactjs/)，在此感谢

<a name="1-react-基本写法"></a>
## 1. React 基本写法
```html
<script src="http://cdn.bootcss.com/react/0.14.0/react.js"></script>
<script src="http://cdn.bootcss.com/react/0.14.0-beta3/JSXTransformer.js"></script>

<script type="text/jsx">    //注意一定要写 jsx
  var HelloWorld = React.createClass({
    render: function() {
      return <p>Hello,World</p>
    }
  });
  React.render(<HelloWorld />,document.body);
</script>
```

<a name="2-jsx-介绍"></a>
## 2. JSX 介绍
>**JSX** = JavaScriptXml

>*  基于ECMAScript的一种新特性  
* 一种定义带属性树结构的语法

    特点
      1. 类XML语法容易接受
      2. 增强JS语义
      3. 结构清晰
      4. 抽象程度高，React屏蔽了手动DOM操作
      5. 代码模块化

<a name="3-jsx-语法"></a>
## 3. JSX 语法
```js
var HelloMessage = React.createClass({
  render: function() {
    return <div className="test">Hello {this.props.name}</div>
  }
});
React.render(<HelloMessage name="John" />, mountNode);
```
>React对字母大小写敏感，组件首字母要大写，如果小写会默认为DOM的自带元素

```js
var style = {
  color  : "red",
  border : "1px #000 solid",
}
var HelloWorld = React.createClass({
  render: function() {
    return <p>Hello,World</p>
  }
});
React.render(<div style={style}><HelloWorld /></div>,document.body);
```

```js
var style = {
  color  : "red",
  border : "1px #000 solid",
}
var HelloWorld = React.createClass({
  render: function() {
    return <p style={style}>Hello,World</p>
  }
});
React.render(<HelloWorld />,document.body);
```
>以上两种方法在浏览器中的显示效果略有不同

<a name="四种条件判断方式"></a>
#### 四种条件判断方式

###### 1. 三元条件表达式

```js
var HelloWorld = React.createClass({
  render: function() {
    return <p>Hello, {this.props.name ? this.props.name : "World"}</p>
  }
});
React.render(<HelloWorld name="Li"/>,document.body);
```

###### 2. 函数变量表达式

```js
var HelloWorld = React.createClass({
  getName: function() {
    if (this.props.name)
        return this.props.name
    else
        return "World"
  },
  render: function() {
    var name = this.getName();
    return <p>Hello, {name}</p>
  }
});
React.render(<HelloWorld name="Li"/>,document.body);
```

###### 3. 直接调用函数

```js
var HelloWorld = React.createClass({
  getName: function() {
    if (this.props.name)
        return this.props.name
    else
        return "World"
  },
  render: function() {
    return <p>Hello, {this.getName()}</p>
  }
});
React.render(<HelloWorld name="Li"/>,document.body)
```

###### 4. 比较运算符

```js
var HelloWorld = React.createClass({
  render: function() {
    return <p>Hello, {this.props.name || "World"}</p>
  }
});
React.render(<HelloWorld name="Li"/>,document.body);
```

<a name="万能的函数表达式"></a>
#### 万能的函数表达式

```js
var HelloWorld = React.createClass({
  render: function() {
    return <p>Hello, {
      (function (obj){               //强制求值运算
        if (obj.props.name)
            return obj.props.name
        else
            return "World"
      })(this)                       //括号也可以放在外面，如 }(this))
    }</p>
  }
});
React.render(<HelloWorld name="Li"/>,document.body);
```
> 参考视频：[如何使用JSX](http://www.jikexueyuan.com/course/969_2.html?ss=2)

<a name="4-非dom属性"></a>
## 4. 非DOM属性

React中有三个非DOM属性：*key*、*ref*、*dangerouslySetInnerHTML*

* *dangerouslySetInnerHTML*： 在JSX中直接插入HTML代码
* *ref*                    ： 父组件__引用__子组件
* *key*                    ： 提高渲染__性能__，key在组件内部不可以相同，列表元素最好加上唯一的key

```js
//dangerouslySetInnerHTML
var rawHTML = {
    __html: "<h1>I'm inner HTML</h1>"
};
var HelloWorld = React.createClass({
  render: function() {
    return <p>Hello, World</p>
  }
});
React.render(<div dangerouslySetInnerHTML={rawHTML}></div>,document.body);
```

```js
//ref
var HelloWorld = React.createClass({
  render: function() {
    this.refs.childp
    return <p ref="childp">Hello, World</p>
  }
});
React.render(<HelloWorld />,document.body);
```

<a name="5-jsx解释器架构介绍"></a>
## 5. JSX解释器架构介绍

<a name="源码阅读方法"></a>
#### 源码阅读方法
* 从执行顺序入手
* 适当忽略细节
* 重视烂笔头
* 反复阅读

<a name="理解解释器架构"></a>
#### 理解解释器架构
* 入口函数
* 载入模块
* 解析JSX
* 执行JS

>前3步在服务器端编译，浏览器端直接执行JS，[参考视频](http://www.jikexueyuan.com/course/969_4.html?ss=2)

<a name="6-组件的生命周期详解"></a>
## 6. 组件的生命周期详解
* 初始化阶段
* 运行中阶段
* 销毁阶段



