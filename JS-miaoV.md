
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

不要拿来做判断的几个点：
* 所有的相对路径
* 颜色值
* innerHTML

```css
IE(styleFloat) 非IE(cssFloat)
可以用class回避兼容性问题
.left { float: left };
.right { float: right };

filter: alpha(opacity:90);  兼容IE
```

```
document.title = 123;    //title后面可以直接接文字
document.body.innerHTML
style.cssText   //类似于innnerHTML，会替换之前的cssText
```

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
