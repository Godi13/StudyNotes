# 知识点整理

## 索引
<!-- MarkdownTOC -->

- [GitHub](#github)
- [工作环境配置](#工作环境配置)
- [工具使用](#工具使用)
- [设计相关](#设计相关)
- [Ubuntu 环境设置](#ubuntu-环境设置)
- [CSS相关](#css相关)

<!-- /MarkdownTOC -->

***

<a name="github"></a>
## GitHub
#### 1. Github上创建新项目静态网页
>0. 新建仓库，命名如：`qd`
1. 建立分支保存名称：`gh-pages`
2. 创建`index.html`文件
3. 输入`godi13.github.io/qd`即可登陆该分支网页

#### 2. push后发现版本有误等情况的时候

>[How to undo (almost) anything with Git](https://github.com/blog/2019-how-to-undo-almost-anything-with-git)

#### 3. ～/.gitconfig设置与Git技巧之小步快跑

    [user]
      name = godi13
      email = godi13@vip.qq.com
    [credential]
      helper = cache --timeout=3600
    [core]
      editor = vim
    [alias]
      ci = commit -a -v
      co = checkout
      st = status -s
      br = branch
      throw = reset --hard HEAD
      throwh = reset --hard HEAD^
      lg = log --color --graph --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset' --abbrev-commit
    [color]
      ui = true
    [push]
      default = current
    [merge]
      tool = meld
`git throw` 用于在修改过程中，尚未推送前，回滚到最后一次推送的版本。  
`git throwh` 会删除掉最近一次推送的版本。  
`git rebase -i HEAD~~` 合并最近的两个版本，将第二行的`pick`改为`s`即可压缩，版本留言时可以删除其他只留一个。  
`git rebase -i origin/gh-pages` 合并最新版本到指定的指针所指版本之间所有的版本。

>参考视频教程：*HappyPeter* 老师的 [如何利用Git辅助本地项目开发](http://haoduoshipin.com/v/92) 和 [git使用技巧：小步快跑](http://qd.haoduoshipin.com/p/git-tricks)

***

<a name="工作环境配置"></a>
## 工作环境配置

#### 1. Ubuntu14.04 服务器上安装 NodeJS
>0. 添加 PPA
`$ curl -sL https://deb.nodesource.com/setup | sudo bash -`
1. 安装 PPA 中提供的nodejs 和 npm
`$ sudo apt-get install nodejs`
2. 安装编译环境
由于 npm 装包的时候，有些 node 的包是需要在本地编译的，所以还要保证系统上有编译环境，很简单，只需要安装
`$ sudo apt-get install build-essential`

>参考资料: [How To Install Node.js on an Ubuntu 14.04 server](https://www.digitalocean.com/community/tutorials/how-to-install-node-js-on-an-ubuntu-14-04-server)

#### 2. Ubuntu 14.04 安装 node v4
    打开终端输入

    curl -o- https://raw.githubusercontent.com/creationix/nvm/v0.27.1/install.sh | bash

    退出 shell 重新登录，执行

    nvm ls-remote

    可以看到最近的 node 版本是 4.1.1 ，执行安装

    nvm install 4.1.1

    这样会报警告

    ···
    nvm is not compatible with the npm config "prefix" option: currently set to "/home/peter/.npm-global" Run npm config delete prefix or nvm use --delete-prefix v4.1.1 to unset it.
    ···

    这是由于咱们自己做的 prefix 造成的。解决方法

    mv .npmrc npmrc
    nvm install 4.1.1
    mv npmrc .npmrc

    最后

    node -v

    可以看到系统上的 node 版本已经是 4.1.1 了

#### 3. glup安装

    npm get prefix        //获取Nodejs安装位置信息

      默认情况下，npm 全局装包会安装到 /usr/local/ 之中。
      默认情况下，如果不用 sudo ，很可能会报权限错误。
      最好的方式是修改一下全局安装的位置。

    mkdir ～/.npm-global  //新建安装位置
    npm config set prefix '~/.npm-global'  //设置npm全局安装位置

    npm i -g gulp         //安装gulp
    cd .npm-global/lib/node_modules        //gulp安装位置
    cd .npm-global/bin    //gulp 执行文件的位置，需要在.bashrc或.profile中添加 export PATH=~/.npm-global/bin:$PATH
    source .bashrc        //修改后加载

    gulp          //确认gulp安装是否成功
    which gulp    //确认gulp安装位置

<a name="工具使用"></a>
## 工具使用

#### 1. glup

    进入项目文件夹下，在项目内安装gulp

    gulp -v                  //查看gulp版本信息
    npm init                 //一路回车确认，保留默认设置即可，得到 package.json
    npm i gulp --save-dev    //将gulp信息保留到package.json，同时会生成node_modules文件夹
    vim package.json         //可以在最下面看到gulp版本信息
    vim .gitignore           //输入node_modules/
    npm i gulp-sass -D       // i 相当于install，-D 相当于--save-dev，gulp-sass 依赖于 libsass
```js
创建 gulpfile.js 文件

var gulp = require('gulp');
var sass = require('gulp-sass');

gulp.task('sass',function(){    //任务名’sass‘
  gulp.src('styles/main.scss')  //被处理的文件
      .pipe(sass())             //传递给sass()进行处理
      .pipe(gulp.dest('css'));  //输出的位置
  });
```
    gulp sass   //执行任务名为'sass'的命令，会新建文件夹css，里面有main.css

###### 自动更新sass变动

```js
在 gulpfile.js 文件中添加

gulp.task('watch',function(){
  gulp.watch('styles/*.scss',['sass']);  //styles下的.scss文件有改动便执行sass命令
});
```
    gulp watch  //开始自动更新

###### 安装其他的gulp插件方法，如 autoprefixer

    npm i gulp-autoprefixer -D    //先在终端安装插件

```js
在 gulpfile.js 文件对应的位置上添加

var prefix = require('gulp-autoprefixer');

      .pipe(prefix())            //prefix()可以设置支持的浏览器版本，具体的看官方文档
```

###### [在gulp出错时不中止watch的方法](https://github.com/happypeter/modern-web-dev/issues/19)

```js
function handleError(err) {
  console.log(err.toString());
  this.emit('end');
}

      .on('error', handleError)  //加入.pipe(sass())下面即可
```

#### 2. React

>0. 命名组件时，首字母要大写
0. [国内cdn](http://www.bootcdn.cn/react/) 复制`//cdn.bootcss.com/react/0.14.0-rc1/react.js` 粘贴后添加`http:` 不用启动服务器文件
0. _JSXTransformer.js_ 仅在开发测试阶段使用，上线之前需要预编译
0. [HTML to JSX Compiler](http://facebook.github.io/react/html-jsx.html) 转换 _HTML_ 到 _JSX_
0. 父子嵌套时，父元素要注意包裹才可生效，出问题可以看一下Chrome开发者工具中报的什么错误

* ###### 原版

```html
<script src="http://cdn.bootcss.com/react/0.14.0-rc1/react.js"></script>

<div id="app"></div>
<script>
var HelloWorld = React.createClass({
  render: function(){
    return (
      React.createElement("div", null,
        "Hello World!"
      )
    )
  }
});
React.render(React.createElement(HelloWorld, null), document.getElementById('app'));
</script>
```
* ###### 改进版

```html
<script src="http://cdn.bootcss.com/react/0.14.0-rc1/react.js"></script>
<script src="http://cdn.bootcss.com/react/0.14.0-beta3/JSXTransformer.js"></script>

<div id="app"></div>
  <script type="text/jsx">
    var HelloWorld = React.createClass({
      render: function(){
        return (
            <div> Hello World </div>
            )
          }
    });
    React.render(<HelloWorld />, document.getElementById('app'));
  </script>
```
* ###### 父子嵌套

```html
<script src="http://cdn.bootcss.com/react/0.14.0-rc1/react.js"></script>
<script src="http://cdn.bootcss.com/react/0.14.0-beta3/JSXTransformer.js"></script>

<script type="text/jsx">
  var Child= React.createClass({
    render: function(){
      return (
          <div> Child </div>
          )
        }
  });
  var Parent = React.createClass({
    render: function(){
      return (
          <div>
            <div> Hello World </div>
            <Child/>
          </div>
          )
        }
  });
  React.render(<Parent />, document.getElementById('app'));
</script>
```
>参考视频教程： *HappyPeter* 老师的 [好多视频第164期](http://haoduoshipin.com/v/164)

***

<a name="设计相关"></a>
## 设计相关

* [GitHub组件标准](http://primercss.io/)
* [语义UI](http://semantic-ui.com/introduction/getting-started.html)
* [Google设计](https://design.google.com/)
* [Polymer](https://www.polymer-project.org/1.0/)
* [Materialup](http://www.materialup.com/)
* [Dribbble](https://dribbble.com/)
* [色盘](http://www.materialpalette.com/blue-grey/lime)

>注意：从色盘网上下载的sass颜色不是scss版本，需要在后面补全<kbd>;</kbd>

* [Normalize.css页面重置](http://www.bootcss.com/p/html5boilerplate/)

``` sass
font-family: "Helvetica Neue", "Segoe UI", Helvetica, Arial, "Hiragino Sans GB", "Microsoft YaHei", "WenQuanYi Micro Hei", sans-serif;
```

* [网站文字排版的技巧](http://www.haoduoshipin.com/v/80)

***

<a name="ubuntu-环境设置"></a>
## Ubuntu 环境设置

#### 1. .bashrc 添加

    # Change umask to make directory sharing easier
    umask 0002
    # Ignore duplicates in command history and increase
    # history size to 1000 lines
    export HISTCONTROL=ignoredups
    export HISTSIZE=1000
    # Add some helpful aliases
    alias l.='ls -d .* --color=auto'
    # alias ll='ls -l --color=auto'

    alias subl='LD_PRELOAD=/opt/sublime_text/libsublime-imfix.so /opt/sublime_text/sublime_text'

    export PATH=~/.npm-global/bin:$PATH

<a name="css相关"></a>
## CSS相关

#### 1. .clearfix

```sass
.clearfix:before,
.clearfix:after
{
 content: " ";
 display: table;
}
.clearfix:after {
  clear: both;
}
```
>参考视频教程： *HappyPeter* 老师的 [Clearfix详解](http://qd.haoduoshipin.com/p/clearfix-in-detail)  
>参考资料：[The very latest new new way to do "clearfix"](http://cssmojo.com/latest_new_clearfix_so_far/)

#### 2. 常用CSS

```sass
* {
  box-sizing: border-box;
}

@media (min-width: 600px) {}  //当最小宽度大于600px时

border：1px solid red;   //调式时可以先添加边框
```
