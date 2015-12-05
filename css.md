## CSS相关

#### 1. .clearfix

```sass
.clearfix {
  &:before,
  &:after {
      content: " ";
      display: table;
  }
  &:after {
      clear: both;
  }
}
```
>参考视频教程： *HappyPeter* 老师的 [Clearfix详解](http://qd.haoduoshipin.com/p/clearfix-in-detail)  
>参考资料：[The very latest new new way to do "clearfix"](http://cssmojo.com/latest_new_clearfix_so_far/)

***

#### 2. 常用CSS

``` sass
font-family: "Helvetica Neue", "Segoe UI", Helvetica, Arial, "Hiragino Sans GB", "Microsoft YaHei", "WenQuanYi Micro Hei", sans-serif;

* {
  box-sizing: border-box;
}

@media (min-width: 600px) {}  //当最小宽度大于600px时

border：1px solid red;   //调式时可以先添加边框

.simple {
  background: #91877b;
  text-shadow: 0 1px 0 rgba(255, 255, 255, 0.4);  //喜欢的字体阴影
}

box-shadow: 0px 3px 8px #AAA, inset 0px 2px 3px #FFF;  //内外阴影，可做按钮效果

transition: property duration timing-function delay;
//property 规定设置过度效果的CSS属性的名称
//duration 规定完成过渡效果需要多少秒或毫秒
//timing-function 规定速度效果的速度曲线，默认ease
//delay 定义过度效果延迟多久开始，默认0
```

***
