# HTML 5 学习笔记

## 1. 新增内容

#### 1.1 新增的标签

|标签    |说明           |
|-------|---------------|
|article|元素时可以嵌套使用的，可以表示插件，强调独立性|
|section|不推荐没有标题的内容使用该元素，强调分段或分块|
|nav    |html5中不能使用menu代替nav|
|aside  |表示当前或文章的附属信息部分|
|time   |`<time datetime="2015-10-10T20:00Z"></time>`|
|header |可以出现多次|
|hgroup |可以用来包裹多个标题|
|address|联系人，地址，联系方式等|

#### 1.2 新增的属性

|属性            |说明           |
|---------------|---------------|
|contentEditable|使当前标签下内容可编辑，如 ul|
|designMode     |在 js 中设置 on/off 启动，全局控制contentEditable属性|
|hidden         |显示/隐藏|
|spellcheck     |查看拼写正确与否，chrome中没有反应|
|tabindex       |属性值为数字，可以控制按tab键选择的顺序|
|pubdate        |`<time datetime="2015-10-10T20:00Z" pubdate="true"></time>` 明确发布时间|

#### 1.3 新增表单元素与属性

|属性            |说明           |
|---------------|---------------|
|form       |指定一个 form 属性，属性值为表单的 id，即可声明该元素从属于指定表单|
|formaction |为提交按钮增加不同的formaction属性，使单击不同的按钮时可以将表单提交到不同的页面|
|formmethod |指定post/get，对每一个表单元素分别指定不同的提交方法|
|formenctype|对表单元素分别指定不同的编码方式|
|formtarget |分别指定提交后在何处打开所需加载的页面|
|autofocus  |为文本框、选择框或按钮控件加上该属性，当画面打开时，该控件自动获得光标焦点|
|required   |应用在输入元素上，在提交时，如果内容为空白，则不允许提交，同时在浏览器中显示信息提示文字|
|label      |为所有可使用标签的表单元素，button、select等，定义labels属性，属性值为一个NodeList对象，代表该元素所绑定的标签元素所构成的集合|

>[label参考视频](http://www.jikexueyuan.com/course/772_4.html?ss=1)
