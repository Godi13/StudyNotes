# SASS

<!-- MarkdownTOC -->

- [SASS 安装](#sass-安装)
- [修改编译除数的CSS格式](#修改编译除数的css格式)
- [`&` 嵌套时调用父选择器](#-嵌套时调用父选择器)
- [嵌套属性](#嵌套属性)
- [`@mixin` 混合](#mixin-混合)
- [`@extend` 继承/扩展](#extend-继承扩展)
- [注释](#注释)
- [数据类型](#数据类型)
- [顏色函數](#顏色函數)
- [列表](#列表)
- [`Boolean`](#boolean)
- [`Interpolation`](#interpolation)
- [`@if`](#if)
- [`@for`](#for)
- [`@each`](#each)
- [`@while`](#while)
- [用户自定义的函数](#用户自定义的函数)
- [警告与错误](#警告与错误)

<!-- /MarkdownTOC -->

<a name="sass-安装"></a>
#### SASS 安装

    gem install sass
    sass -v    //检查版本
    sass -i    //可进入sass交互模式

    //常规使用方法
    sass sass/style.scss:css/style.css
    sass --watch sass:css

<a name="修改编译除数的css格式"></a>
#### 修改编译除数的CSS格式

    sass --watch sass:css --style [compact,expanded,compressed]

* `nested` 嵌套（默认）
* `compact` 紧凑
* `expanded` 扩展(类似手打模式)
* `compressed` 压缩

<a name="-嵌套时调用父选择器"></a>
#### `&` 嵌套时调用父选择器

```sass
//scss
.nav {
  height: 100px;
  & &-text {
    font-size: 15px;
  }
}

//css
.nav {
  height: 100px;
}
.nav .nav-text {
  font-size: 15px;
}
```

<a name="嵌套属性"></a>
#### 嵌套属性

```sass
//sass
body {
  font: {
    family: Helvetica, Arial, sans-serif;
    size: 15px;
    weight: normal;
  }
}
.nav {
  border: 1px solid #000 {
    left: 0;
    right: 0;
  }
}

//css
body {
  font-family: Helvetica, Arial, sans-serif;
  font-size: 15px;
  font-weight: normal;
}
.nav {
  border: 1px solid #000;
  border-left: 0;
  border-right: 0;
}
```

<a name="mixin-混合"></a>
#### `@mixin` 混合

```sass
//sass
@mixin alert {
  color: #333;
  background-color: #fff;
}
.alert-warning {
  @include alert;
}

//css
.alert-warning {
  color: #333;
  background-color: #fff;
}
```

```sass
//sass
@mixin alert($text-color, $background) {
  color: $text-color;
  background-color: $background;
  a {
    color: darken($text-color, 10%);
  }
}
.alert-warning {
  @include alert(#8a6d3b, #fcf8e3);
}
.alert-info {
  @include alert($background:#d9edf7, $text-color:#31708f);
}

//css
.alert-warning {
  color: #8a6d3b;
  background-color: #fcf8e3;
}
.alert-warning a {
  color: #66512c;
}
.alert-info {
  color: #31708f;
  background-color: #d9edf7;
}
.alert-info a {
  color: #245269
}
```

<a name="extend-继承扩展"></a>
#### `@extend` 继承/扩展

```sass
//scss
.alert {
  padding: 15px;
}
.alert a {
  font-weight: bold;
}
.alert-info {
  @extend .alert;
  background-color: #d9edf7;
}

//css
.alert, .alert-info {
  padding: 15px;
}
.alert a, .alert-info a {
  font-weight: bold;
}
.alert-info {
  background-color: #d9edf7;
}
```

<a name="注释"></a>
#### 注释

```sass
/*!  多行注释
 *   加!的话，在压缩格式下注释也会存在
 *   如果不加则在压缩格式下不存在  */
```

<a name="数据类型"></a>
#### 数据类型

```sass
percentage(650px / 1000px)      //65%
min(1,2,3)                      //1
max(1,2,3)                      //3

ning - hao                      //"ning-hao"
ning / hao                      //"ning/hao"
ning * hao                      //error

$greeting: "Hello World"
$greeting                       //"Hello World"
to-upper-case($greeting)        //"HELLO WORLD"
to-lower-case($greeting)        //"hello world"
str-length($greeting)           //11
str-index($greeting, "Hello")   //1
str-index($greeting, "World")   //7
str-insert($greeting, "!", 12)  //"Hello World!"
```

<a name="顏色函數"></a>
#### 顏色函數

##### `adjust-hue` 调整色相

```sass
$base-color: #ff0000;

body {
  background-color: adjust-hue($base-color, 127deg);
}
```

##### `lightten` 与 `darken` 调整明度

```sass
$base-color: hsl(222,100%,50%)
$light-color: lighten($base-color,30%)
$dark-color: darken($base-color,20%)
```

##### `saturate` 与 `desaturate` 调整饱和度

```sass
$base-color: hsl(222,50%,50%)
$saturate-color: saturate($base-color,50%)       //相当于 hsl(222,100%,50%)
$desaturate-color: desaturate($base-color,30%)   //相当于 hsl(222,20%,50%)
```

##### `opacify` 与 `transparentize`

```sass
$base-color: hsla(222, 50%, 50%, 0.5)
$fade-in-color: opacify($base-color, 0.3)
$fade-out-color: transparentize($base-color, 0.2)
```

<a name="列表"></a>
#### 列表

```sass
length(5px 10px);             //2
length(5px 10px 5px 0);       //4
nth(5px 10px, 1);             //5px
nth(5px 10px, 2);             //10px
index(1px solid red, solid)   //2
append(5px 10px, 5px)         //5px 10px 5px
join(5px 10px, 5px 0)         //5px 10px 5px 0
join(5px 10px, 5px 0, comma)  //5px, 10px, 5px, 0
```

##### `map`

```sass
$map: (key1: value1, key2: value2, key3: value3)

$colors: (light: #fff, dark: #000)      //输入到 sass -i 中时不要带;
length($colors)                //2
map-get($colors, dark)         //#000000
map-get($colors, light)        //#ffffff
map-keys($colors)              //("light", "dark")
map-values($colors)            //("#ffffff", "#000000")
map-has-key($colors, light)    //true
map-merge($colors,(light-gray: #e5e5e5))    //(light: #ffffff, dark: #000000, light-gray: #e5e5e5)

$colors: map-merge($colors,(light-gray: #e5e5e5))    //(light: #ffffff, dark: #000000, light-gray: #e5e5e5)
$colors     //(light: #ffffff, dark: #000000, light-gray: #e5e5e5)
map-remove($colors, light, dark)  //(light-gray: #e5e5e5)
```

<a name="boolean"></a>
#### `Boolean`

```sass
(5px > 3px) and (5px > 10px)    //false
(5px > 3px) and (5px < 10px)    //true
(5px > 3px) or (5px > 10px)     //true
not(5px > 3px)                  //false
not(5px < 3px)                  //true
```

<a name="interpolation"></a>
#### `Interpolation`

```sass
//sass
$version: "0.0.1";
/* 项目当前版本是： #{$version} */

$name: "info";
$attr: "border";

.alert-#{$name) {
  ${$attr}-color: #ccc;
}

//css
.alert-info {
  border-color: #ccc;
}
```

<a name="if"></a>
#### `@if`

```sass
//sass
$use-prefixes: false;
$theme: "dark";

body {
  @if $theme == dark {
    background-color: black;
  } @else if $theme == light {
    background-color: white;
  } @else {
    background-color: grey;
  }
}
.rounded {
  @if $use-prefixes {
    -webkit-border-radius: 5px;
    -moz-border-radius: 5px;
    -ms-border-radius: 5px;
    -o-border-radius: 5px;
  }
  border-radius: 5px;
}

//css
body {
  background-color: black;
}
.rounded {
  border-radius: 5px;
}
```

<a name="for"></a>
#### `@for`

```sass
@for $var from <开始值> through <结束值> {
  ...
}
@for $var from <开始值> to <结束值> {    //与 through 停止的位置不同
  ...
}

//sass
$columns: 4;

@for $i from 1 through $columns {
  .col-#{$i} {
    width: 100% / $columns * $i;
  }
}

@for $i from 1 to $columns {
  .col-#{$i} {
    width: 100% / $columns * $i;
  }
}

//css
//through
.col-1 { width: 25% };
.col-2 { width: 50% };
.col-3 { width: 75% };
.col-4 { width: 100% };
//to
.col-1 { width: 25% };
.col-2 { width: 50% };
.col-3 { width: 75% };
```

<a name="each"></a>
#### `@each`

```sass
@each $var in $list {
  ...
}

//sass
$icons: success error warning;

@each $icon in $icons {
  .icon-#{$icon} {
    background-image: url(../images/icons/#{$icon}.png);
  }
}

//css
.icon-success {
  background-image: url(../images/icons/success.png);
}
.icon-error {
  background-image: url(../images/icons/error.png);
}
.icon-warning {
  background-image: url(../images/icons/warning.png);
}
```

<a name="while"></a>
#### `@while`

```sass
@while 条件 {
  ...
}

//sass
$i: 6;

@while $i > 0 {
  .item-#{$i} {
    width: 5px * $i;
  }
  $i: $i - 2;
}

//css
.item-6 { width: 30px };
.item-4 { width: 20px };
.item-2 { width: 10px };
```

<a name="用户自定义的函数"></a>
#### 用户自定义的函数

```sass
@function 名称 （参数1， 参数2） {
  ...
}

//sass
$colors: (light: #fff, dark: #000)

@function color($key) {
  @return map-get($colors, $key);
}

body {
  background-color: color(light);
}

//css
body {
  background-color: #ffffff;
}
```

<a name="警告与错误"></a>
#### 警告与错误

```sass
$colors: (light: #fff, dark: #000)

@function color($key) {
  @if not map-has-key($colors, $key) {
    @warn "在 $color 里没找到 #{$key} 这个 key";
    //@error  "在 $color 里没找到 #{$key} 这个 key";
    //@error 会在转换的 css 中报错
  }

  @return map-get($colors, $key);
}

body {
  background-color: color(grey);
}     //在命令行面板中会报错
```
