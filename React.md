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
    - [什么是生命周期](#什么是生命周期)
    - [不同生命周期内可以自定义的函数](#不同生命周期内可以自定义的函数)
    - [初始化阶段介绍](#初始化阶段介绍)
    - [运行中阶段介绍](#运行中阶段介绍)
    - [销毁阶段介绍](#销毁阶段介绍)
  - [7. React 属性和状态详解](#7-react-属性和状态详解)
    - [属性的含义和用法](#属性的含义和用法)
    - [状态的含义和用法](#状态的含义和用法)
    - [属性和状态的对比](#属性和状态的对比)
  - [8.React 事件的用法](#8react-事件的用法)
    - [事件处理函数的使用](#事件处理函数的使用)
    - [事件对象介绍](#事件对象介绍)
    - [事件和状态关联](#事件和状态关联)
  - [9. 组件的协同使用](#9-组件的协同使用)
    - [组件嵌套](#组件嵌套)

<!-- /MarkdownTOC -->

<a name="react-学习笔记"></a>
# React 学习笔记
>总结自[极客学院 - ReactJS](http://www.jikexueyuan.com/course/reactjs/)，在此感谢

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
```]

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

<a name="什么是生命周期"></a>
#### 什么是生命周期
组件本质上时__状态机__，输入确定，输出一定确定。
状态发生__转换__时会触发不同的钩子函数，从而让开发者有机会做出响应。
可以用__事件__的思路来理解状态。

<a name="不同生命周期内可以自定义的函数"></a>
#### 不同生命周期内可以自定义的函数
* 初始化阶段
* `getDefaultProps`：只调用一次，实例之间__共享引用__，在执行React.createClass时即被调用
* `getInitialState`：初始化每个实例特有的__状态__
* `componentWillMount`：render之前最后一次__修改状态__的机会
* `render`：只能访问 _this.props_ 和 _this.state_，只有一个顶层组件，__不允许__修改状态和DOM输出
* `componentDidMount`：成功render并渲染完成真实DOM之后触发，__可以__修改DOM
* 运行中阶段
* `componentWillReceiveProps`：父组件修改属性触发，__可以__修改新属性、修改状态
* `shouldComponentUpdate`：返回 _false_ 会__阻止__ _render_ 调用
* `componentWillUpdate`：__不能__修改属性和状态
* `render`：只能访问 _this.props_ 和 _this.state_，只有一个顶层组件，__不允许__修改状态和DOM输出
* `componentDidUpdate`：__可以__修改DOM
* 销毁阶段
* `componentWillUnmount`：在删除组件之前进行__清理__操作，比如计时器和事件监听器

<a name="初始化阶段介绍"></a>
#### 初始化阶段介绍
查看触发顺序

```js
var HelloWorld = React.createClass({
  getDefaultProps: function() {
    console.log("getDefaultProps, 1")
  },
  getInitialState: function() {
    console.log("getInitialState, 2");
    return null;
  },
  componentWillMount: function() {
    console.log("componentWillMount, 3")
  },
  render: function() {
    console.log("render, 4")
    return <p>Hello, World</p>
  },
  componentDidMount: function() {
    console.log("componentDidMount, 5")
  },
});
React.render(<HelloWorld/>,document.body);
```
各个函数的正确用法

```js
<script src="http://cdn.bootcss.com/react/0.14.0/react.js"></script>
<script src="http://cdn.bootcss.com/react/0.14.0-beta3/JSXTransformer.js"></script>
<script src="http://cdn.bootcss.com/jquery/3.0.0-alpha1/jquery.min.js"></script>
<script type="text/jsx">
  $(document).ready(
    function() {
      var count = 0;
      var HelloWorld = React.createClass({
        getDefaultProps: function() {
          console.log("getDefaultProps, 1");
          return {name: "Tom"};
        },
        getInitialState: function() {
          console.log("getInitialState, 2");
          return {myCount: count++,
            ready: false};
          },
          componentWillMount: function() {
            console.log("componentWillMount, 3");
            this.setState({ready: true});
          },
          render: function() {
            console.log("render, 4")
            return <p>Hello, {this.props.name ? this.props.name : "World"}<br/>{" " + this.state.ready} {this.state.myCount}</p>;
          },
          componentDidMount: function() {
            console.log("componentDidMount, 5");
            $(React.findDOMNode(this)).append("surprise!");
          },
        });
        React.render(<div><HelloWorld/><HelloWorld/></div>,document.body);
      });
</script>
```

<a name="运行中阶段介绍"></a>
#### 运行中阶段介绍
查看触发顺序

```js
var HelloWorld = React.createClass({
    componentWillReceiveProps: function () {
        console.log("componentWillReceiveProps 1");
    },
    shouldComponentUpdate: function () {
        console.log("shouldComponentUpdate 2");
        return true;
    },
    componentWillUpdate: function () {
        console.log("componentWillUpdate 3")
    },
    render: function () {
        console.log("render 4");
        return <p>Hello, {this.props.name ? this.props.name : "World"}</p>;
    },
    componentDidUpdate: function() {
        console.log("componentDidUpdate 5");
    },
});
var HelloUniverse = React.createClass({
    getInitialState: function () {
        return {name: ''};
    },
    handleChange: function (event) {
        this.setState({name: event.target.value});
    },
    render: function () {
        return <div>
        <HelloWorld name={this.state.name}></HelloWorld>
        <br/>
        <input type="text" onChange={this.handleChange} />
        </div>
    },
});
React.render(<HelloUniverse />, document.body);
```
各个函数的正确用法

```js
<script src="http://cdn.bootcss.com/react/0.14.0/react.js"></script>
<script src="http://cdn.bootcss.com/react/0.14.0-beta3/JSXTransformer.js"></script>
<script src="http://cdn.bootcss.com/jquery/3.0.0-alpha1/jquery.min.js"></script>
<script type="text/jsx">
  $(document).ready(
    function() {
      var HelloWorld = React.createClass({
        componentWillReceiveProps: function (newProps) {
          console.log("componentWillReceiveProps 1");
          console.log(newProps);
        },
        shouldComponentUpdate: function () {
          console.log("shouldComponentUpdate 2");
          return true;
        },
        componentWillUpdate: function () {
          console.log("componentWillUpdate 3");
        },
        render: function () {
          console.log("render 4");
          return <p>Hello, {this.props.name ? this.props.name : "World"}</p>;
        },
        componentDidUpdate: function() {
          $(React.findDOMNode(this)).append("surprise!");
        },
      });
      var HelloUniverse = React.createClass({
        getInitialState: function () {
          return {name: ''};
        },
        handleChange: function (event) {
          this.setState({name: event.target.value});
        },
        render: function () {
          return <div>
          <HelloWorld name={this.state.name}></HelloWorld>
          <br/>
          <input type="text" onChange={this.handleChange} />
        </div>
      },
    });
      React.render(<HelloUniverse />, document.body);
    }
  );
</script>
```

<a name="销毁阶段介绍"></a>
#### 销毁阶段介绍

```js
var HelloWorld = React.createClass({
    render: function () {
        console.log("render 4");
        return <p>Hello, {this.props.name ? this.props.name : "World"}</p>;
    },
    componentWillUnmount: function() {
        console.log("BOOOOOOOOOOOOOOOOOM!");
    },
});
var HelloUniverse = React.createClass({
    getInitialState: function () {
        return {name: ''};
    },
    handleChange: function (event) {
        if (event.target.value == "123") {
            React.unmountComponentAtNode(document.getElementsByTagName("body")[0]);
            return;
        }
        this.setState({name: event.target.value});
    },
    render: function () {
        return <div>
        <HelloWorld name={this.state.name}></HelloWorld>
        <br/>
        <input type="text" onChange={this.handleChange} />
        </div>
    },
});
React.render(<HelloUniverse/>, document.body);
```

<a name="7-react-属性和状态详解"></a>
## 7. React 属性和状态详解

<a name="属性的含义和用法"></a>
#### 属性的含义和用法

props = properties  
属性：一个事物的性质与关系  
属性往往是__与生俱来__，无法自己改变的

###### 第一种使用方法
`<HelloWorld name = ? />`中`？`可以为：`"Tim"` `{123}` `{"Tim"}` `{[1,2,3]}` `{variable}`

```js
var HelloWorld = React.createClass({
  render: function() {
    return <p>Hello, {this.props.name ? this.props.name : "World"}</p>;
  },
});
var HelloUniverse = React.createClass({
  getInitialState: function() {
    return {name: ''};
  },
  handleChange: function (event) {
      this.setState({name: event.target.value});
  },
  render: function (){
    return <div>
    <HelloWorld name={this.state.name}></HelloWorld>
    <br/>
    <input type="text" onChange={this.handleChange} />
    </div>
  },
});
React.render(<HelloUniverse />, document.body);
```

###### 第二种使用方法
```js
var props = {
  one:"123",
  two:321
}
<HelloWorld{...props}/>   //...必须有三个点
```
```js
var HelloWorld = React.createClass({
  render: function() {
    return <p>Hello, {this.props.name1 + ' ' + this.props.name2}</p>;
  },
});
var HelloUniverse = React.createClass({
  getInitialState: function() {
    return {
      name1: 'Tim',
      name2: 'John',
    };
  },
  handleChange: function (event) {
      this.setState({name: event.target.value});
  },
  render: function (){
    return <div>
    <HelloWorld {...this.state}></HelloWorld>
    <br/>
    <input type="text" onChange={this.handleChange} />
    </div>
  },
});
React.render(<HelloUniverse />, document.body);
```

###### 第三种使用方法
```js
//几乎不用该方法
var instance = React.render(<HelloWorld />,document.body);
instance.setProps({name:"Tim"});
```
```js
var HelloWorld = React.createClass({
  render: function() {
    return <p>Hello, {this.props.name ? this.props.name : "World"}</p>;
  },
});
var instance = React.render(<HelloWorld/>, document.body);
instance.setProps({name: 'Tim'});
```

<a name="状态的含义和用法"></a>
#### 状态的含义和用法
state  
状态：事物所处的状况  
状态是由事物自行处理、不断变化的

`getInitialState`：初始化每个实例特有的状态  
`setState`：更新组件状态，用此方法会触发__diff算法__，有变化则更新DOM

```js
var HelloWorld = React.createClass({
  render: function() {
    return <p>Hello, {this.props.name}</p>;
  },
});
var HelloUniverse = React.createClass({
  getInitialState: function() {
    return {
      name: 'Tim',
    };
  },
  handleChange: function (event) {
    this.setState({name: event.target.value});
  },
  render: function() {
    return <div>
    <HelloWorld name={this.state.name}></HelloWorld>
    <br/>
    <input type="text" onChange={this.handleChange} />
    </div>
  },
});
React.render(<HelloUniverse/>, document.body);
```

<a name="属性和状态的对比"></a>
#### 属性和状态的对比
组件在运行时__需要修改__的数据就是状态。
>相似点

>* 都是纯JS对象
* 都会触发render更新
* 都具有确定性

|-                     |属性|状态|
|----------------------|---|----|
|能否从父组件获取初始值？  |Y||
|能否由父组件修改？       |Y||
|能否在组件内部设置默认值？|Y|Y|
|能否再组件内部修改？     ||Y|
|能否设置子组件的初始值？  |Y||
|能否修改子组件的值？     |Y||

表格总结：__状态只和组件本身相关，组件不能修改属性。__

<a name="8react-事件的用法"></a>
## 8.React 事件的用法

<a name="事件处理函数的使用"></a>
#### 事件处理函数的使用

>onClick={this.handleClick} 不能加括号，加括号会调用返回值

|触摸-移动端   |键盘       |剪切  |表单     |焦点   |UI元素|滚动|
|-------------|----------|-----|--------|-------|------|----|
|onTouchCancel|onKeyDown|onCopy|onChange|onFocus|onScroll|onWheel|
|onTouchEnd   |onKeyPress|onCut|onInput|onBlur|
|onTouchMove  |onKeyUp|onPaste|onSubmit|
|onTouchStart |

鼠标点击移动：`onClick` `onContextMenu` `onDoubleClick` `onMouseDown` `onMouseEnter` `onMouseLeave` `onMouseMove` `onMouseOut` `onMouseOver` `onMouseUp`  
鼠标拖拽：`onDrop` `onDrag` `onDragEnd` `onDragEnter` `onDragExit` `onDragLeave` `onDragOver` `onDragStart`

<a name="事件对象介绍"></a>
#### 事件对象介绍

```js
handleChange: function (event) {
  console.log(event.target.value);
},
```
##### 通用属性：所有的对象都有的属性
|属性类型|属性名  |描述 |
|-------|-------|------|
|boolean|bubbles|事件是否可以冒泡|
|boolean|cancelable|事件是否可以取消|
|DOMEventTarget|currentTarget|
|boolean|defaultPrevented|事件是否禁止默认行为|
|number|eventPhase|事件所处阶段|
|boolean|isTrusted|事件是否可信|
|DOMEvent|nativeEvent|
|void|perventDefault()|
|void|stopPropagation()|对应bubbles|
|DOMEventTarget|target|
|number|timeStamp|时间戳，事件触发时间|
|string|type|

##### 不同属性
|属性类型|属性名  |描述 |
|-------|-------|------|
|剪切|
|DOMDataTransfer|clipboardData|
|键盘|
|boolean|altKey|是否按下alt键|
|Number|charCode|通过按键的字符编码确定按下的键|
|boolean|ctrlKey|是否按下ctrl键|
|function|getModifierState(Key)|是否按下辅助按键|
|String|key|按下的键|
|Number|keyCode|非字符编码的键|
|String|locale|本地化的一些字符串|
|Number|location|位置|
|boolean|metaKey|window键|
|boolean|repeat|按键是否重复|
|boolean|shiftKey|是否按下shift|
|Number|which|通用化的charCode、keyCode|
|焦点|
|DOMEventTarget|relatedTarget|转移前的焦点|
|鼠标|
|boolean|altKey|
|Number|button|
|Number|buttons|
|Number|clientX|当前鼠标所处的X轴坐标，原点为浏览器窗口的左上角|
|Number|clientY|
|boolean|ctrlKey|
|function|getModifierState(Key)|
|boolean|metaKey|
|Number|pageX|原点为HTML页面的左上角|
|Number|pageY|
|DOMEventTarget|relatedTarget|
|Number|screenX|原点为显示器的左上角|
|Number|screenY|
|boolean|shiftKey|
|触摸|
|boolean|altKey|
|DOMTouchList|changedTouches|
|boolean|ctrlKey|
|function|getModifierState(key)|
|boolean|metaKey|
|boolean|shiftKey|
|DOMTouchList|targetTouches|
|DOMTouchList|touches|
|UI元素|
|Number|detail|滚动的距离|
|DOMAbstractView|view|界面|
|鼠标滚轮滚动|
|Number|deltaMode|
|Number|deltaX|
|Number|deltaY|
|Number|deltaZ|

<a name="事件和状态关联"></a>
#### 事件和状态关联

```js
handleChange: function (event) {
  this.setState({inputText: event.target.value});  //this.setState 设置组件的状态
},
```

<a name="9-组件的协同使用"></a>
## 9. 组件的协同使用

组件的协同本质上是对组件的一种__组织、管理方式__。

目的：逻辑清晰、代码模块化、封装细节、代码复用

组件协同方式：组件嵌套（用于嵌套与封装）、Mixin混入（用于抽离与复用）

<a name="组件嵌套"></a>
#### 组件嵌套
组件嵌套的本质时__父子关系__。

父组件通过属性与子组件通信，子组件通过委托与父组件通信。

|优点   |说明   |
|-------|------|
|逻辑清晰|父子关系和人类社会的父子关系对应，易于理解|
|代码模块化|每个模块对应一个功能，不同的模块可以同步开发|
|封装细节|开发者只需要关注组件的功能，不用关心组件的实现细节|

|缺点   |说明   |
|-------|------|
|编写难度高|父子关系的具体实现需要经过深思熟虑，贸然编写将导致关系混乱、代码难以维护|
|无法掌握所有细节|使用者只知道组件用法，不知道实现细节，遇到问题难以修复|












































