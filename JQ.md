# jQuery

## 选择器

```js
$('元素')
$('#id')
$('.class')
//精确选择用空格隔开即可

$('img:first')           //选择第一个img元素
$('img:odd')             //选择第奇数个img元素，从0开始
$('img:even')            //选择第偶数个img元素，从0开始
$('img:eq(1)')           //选择第2个img元素，从0开始,eq为等于的含义
$('img:lt(3)')           //选择小于3的img元素，即前3个,lt为小于的含义
$('img:gt(5)')           //选择大于5的img元素，第7个开始，gt为大于的含义

$('[属性名称]')
$('元素[属性名称]')        //选择指定元素中包含属性名称的对象
$('元素[属性名称]=属性值 > 元素')    // > 含义为直接的子元素
$('元素[属性名称]!=属性值 > 元素')   // != 含义为选择不是该值的属性
$('元素[属性名称]~=属性值 > 元素')   // ~= 只能包含有空格的值
$('元素[属性名称]*=属性值 > 元素')   // *= 全部包含
$('元素[属性名称]^=属性值 > 元素')   // ^= 以该字符开始
$('元素[属性名称]$=属性值 > 元素')   // $= 以该字符结束

$(':input')       //与表单相关的选择器都有个 : ,button也被作为input元素
$(':button')      //只选择button
$(':submit')      //只选择submit
$(':reset')       //只选择reset
$(':password')    //选择密码类型的input元素
$(':file')        //选择文件类型的input元素
$(':checkbox')    //选择复选框类型的input元素
$(':radio')       //选择单选框类型的input元素
$(':checked')     //选择被勾选的input元素
$(':focused')     //选择焦点状态的input元素
$(':disabled')    //选择被禁用的input元素
$(':enabled')     //选择启用的input元素

$('元素:first-child')     //找到作为第一个子元素的元素
$('元素:last-child')      //找到作为父元素的最后一个子元素
$('元素:nth-child(1)')    //该1与eq的不同，是从1开始的，不是从0
$('元素:nth-child(odd)')  //选择奇数位置上的子元素，从1开始
$('元素:nth-last-child(4n)')  //将倒过来数

$('元素:contains("字符")')  //选择包含字符内容的元素
$('元素').eq(1)            //选择第2个
$('元素').eq(-1)           //选择倒数第1个
$('元素').first()          //选择第1个
$('元素').last()           //选择最后1个
$('元素').slice(4,8)       //选择第5~8个元素

$('#id').children()       //选择子元素
$('#id').children('元素')  //精确选择子元素
$('#id').parent()         //选择父元素
$('#id').next()           //选择下一个元素
$('#id').prev()           //选择上一个元素
$('#id').siblings()       //选择所有的兄弟，除了自身
$('#id').nextAll()        //选择其后所有的兄弟，不包括自己
$('#id').prevAll()        //选择其前所有的兄弟，不包括自己
```

## 属性

```js
$().attr('属性'，'值')    //设置属性值
$().attr('属性')         //获取属性值，如有多个则为获取第一个值，如需获取多个值需要配合each，map
$().removeAttr('属性')

$().addClass()           //添加类
$().removeClass()
$().hasClass()           //用于判断有无指定的类
$().toggleClass()        //切换类，如下所示
$('元素').click(function() {
  $(this).toggleClass('类名');
})

$().width()
$().innerWidth()         //宽度+内边距
$().outerWidth()         //宽度+内边距+边框+外边距
$().outerWidth(350)      //设置宽度
$().height()
$().innerHeight()
$().outerHeight()

$().css('属性名称')       //查看属性值，返回带单位的字符串
$().css('width')         //"300px"
$().css('属性名称','属性值')    //设置属性值，设置的值可以不带单位，如
$().css('width','300')
$().css('width','+=20')  //在当前值的基础上加20
$().css({width: '200', border: '1px solid #000'})  //同时设置多个属性值

$().offset()              //相对于文档的位置，返回 Object {top: xxx, left: xxx}
$().offset({top: xxx, left: xxx})     //设置元素到顶部与左侧的距离
$().position()            //获取和设置元素的位置，相对于定位的父元素的位置
```

## DOM

```js
$().wrap('<div></div>')         //包装指定对象
$().wrapInner('<div></div>')    //包装指定对象内部元素
$().wrapAll('<div></div>')
$().unwrap()                    //移除不需要参数

//内部追加
$().prepend('<h1>Title</h1>')   //添加到指定对象子元素的最前面
$().append('<h1>Title</h1>')    //添加到指定对象子元素的最后
$('<h1>Title</h1>').appendTo('对象')  //追加到最后
$('<h1>Title</h1>').prependTo('对象') //追加到最前

//外部追加
$().after('<h5>DOM</h5>')
$().before('<h5>DOM</h5>')
$('<h5>DOM</h5>').insertBefore()      //追加到指定对象前面
$('<h5>DOM</h5>').insertAfter()       //追加到指定对象后面

$('对象').empty()     //清空指定对象的内容
$('对象').remove()    //移除指定对象

$().replaceWith('<h5>Title</h5>')     //替换,"被"
$('<h5>Title</h5>').replaceAll()      //替换，"把"

$().clone().appendTo()   //复制指定对象并插入到另一个对象
```

## 事件

```js
//鼠标事件
$(function() {
  $('对象1').css('display', 'none');
  $('对象2').click(function() {
    $(this).siblings('h6').toggle();
  });
})


dblclick()    //双击
hover()       //鼠标在上面或离开时都触发
mouseenter()  //鼠标在上面时触发
mouseleave()  //鼠标离开时触发


//键盘与表单事件
$(function() {
  $('对象').focus(function() {
    $(this).attr('属性','值');
  });

  $('对象').blur(function() {
    if ($(this).val() === '') {
      $(this).attr('属性','值');
    }
    $('对象').text('xxxx').show();
  });

  $('对象').keyup(function() {
    $('对象').text('XXXX').show();
  });

  $('对象').change(function() {
  	if($(this).prop('checked')) {
  	  $('对象').text('XXXX').show();
  	} else {
  	  $('对象').text('xxxx').show();
  	}
  });

  $('form').submit(function() {
  	 $('对象').text('XXXXX').show();
  	 alert($('对象').val());
  });
})

//on,相当于最上面的例子
$(function() {
  $('对象1').css('display', 'none');
  $('对象2').on('click', function() {
    $(this).siblings('h6').toggle();
  });
})
//one
  $('对象2').one('click', function() {  //one 只执行一次
    $(this).siblings('h6').toggle();
  });

$('对象').off('click')   //取消事件绑定
```

## 效果

```js
//渐隐渐现，默认400毫秒，fast为200毫秒，slow为600毫秒
$().fadeIn()       //渐现
$().fadeOut()      //渐隐
$().fadeToggle()   //渐隐渐现切换
$().fadeIn(1000)   //渐现过程持续1000毫秒
$().fadeIn().fadeOut()   //先渐现后渐隐
$().fadeIn(1000，function() {
	console.log('XXXX');  
})；               //渐现后回调函数

//逐渐渐隐渐现
arguments.callee
$('对象').fadeOut('fast',function() {
	$(this).prev().fadeOut('fast', arguments.callee);
});
$('对象').fadeIn('fast',function() {
	$(this).next().fadeIn('fast', arguments.callee);
});

//滑动效果渐隐渐现
slideup() slidedown() slidetoggle()

//隐藏显示
show() hide() 
```