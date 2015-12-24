# Ubuntu

<!-- MarkdownTOC -->

- [`.bashrc` 添加](#bashrc-添加)
- [常用指令](#常用指令)
    - [1. deb 包命令](#1-deb-包命令)
    - [2. 关于权限](#2-关于权限)
    - [3. grep](#3-grep)
    - [4. 其他](#4-其他)
    - [5. 下载](#5-下载)
- [Tmux](#tmux)
- [bash脚本](#bash脚本)
    - [if 语句](#if-语句)
    - [for 循环](#for-循环)
- [强制关闭图形窗口](#强制关闭图形窗口)

<!-- /MarkdownTOC -->


<a name="bashrc-添加"></a>
## `.bashrc` 添加

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

    #alias for cnpm
    alias cnpm="npm --registry=https://registry.npm.taobao.org \
    --cache=$HOME/.npm/.cache/cnpm \
    --disturl=https://npm.taobao.org/dist \
    --userconfig=$HOME/.cnpmrc "

***

<a name="常用指令"></a>
## 常用指令

<a name="1-deb-包命令"></a>
#### 1. deb 包命令

    安装/升级deb包： sudo dpkg -i xxx.deb
    卸载deb包：     sudo dpkg -r（-p） xxxname

    -i  在系统中安装/升级软件
    -r  在系统中卸载软件,不删除配置文件
    -p  在系统中卸载软件以及其配置文件
    -l  在系统中查询软件内容信息

<a name="2-关于权限"></a>
#### 2. 关于权限

    修改用户组 sudo chgrp groupname filename
    修改拥有者 sudo chown ownername filename

<a name="3-grep"></a>
#### 3. grep

    grep -i xxx filename    //取消大小写敏感查找
    grep -w xxx filename    //精确查找
    grep -v xxx             //不匹配
    grep '\<xxx' filename   //匹配xxx在前的
    grep 'xxx\>' filename   //匹配xxx在后的

>`find`专注文件查找，`grep`专注字符串查找

<a name="4-其他"></a>
#### 4. 其他

    ifconfig                           //查看IP
    eog *                              //打开图片
    tar zxvf filename.tgz              //解压缩.tgz
    sudo ln -s /usr/local/bin/python3.5m /usr/bin/python
    mkdir filename && cd $_            //创建文件夹并进入
    kill -9 进程号                      //杀死进程

<a name="5-下载"></a>
#### 5. 下载

     wget -p -np -k -r url(你的网站入口)  //下载网站
     sudo apt-get install axel
     axel http://xxxxxx

***

<a name="tmux"></a>
## Tmux

|快捷键|说明|
|:-----|:---|
|C+b ?|help|
|C+b t|time|
|C+b d|save & exit|
|C+b &|close window|
|C+b space|next default layout|
|C+b "|split pane horizontally|
|C+b %|split pane vertically|
|C+b arrow key|switch pane|
|C+b c|(c)reate a new window|
|C+b n|move to the (n)ext window|
|C+b p|move to the (p)revious window|
|Hold C+b| don't release it and hold one of the arrow keys - resize pane|

    tmux list-sessions          //查看当前tmux窗口情况
    tmux new-session -s name    //创建命名的窗口

    tmux a -t name              //返回指定的窗口
    tmux kill-session -t name   //关闭指定的窗口
    tmux kill-sever             //关闭所有的窗口

>参考资料：[tmux的使用方法和个性配置](http://mingxinglai.com/cn/2012/09/tmux/)  
>参考视频：[命令行操作神器 tmux](http://haoduoshipin.com/v/41)

***

<a name="bash脚本"></a>
## bash脚本

`*.sh` 脚本需要添加执行权限才可执行，文件夹内执行需要文件名前添加`./`，如`./*.sh`

<a name="if-语句"></a>
#### if 语句

    if ls
    then
       echo "hello"
    fi

>if 返回值为`0`时才执行后面的语句，输出`echo $?`可查看返回值

<a name="for-循环"></a>
#### for 循环

    #!/usr/bin/env bash
    for i in 1 2 a b
    do
        echo $i
    done

    #!/usr/bin/env bash
    for i in `ls`
    do
        echo $i
    done

***

<a name="强制关闭图形窗口"></a>
## 强制关闭图形窗口

在`系统`-`键盘`中添加自定义快捷键，Name：`ForceQuit`，Command：`xkill`，快捷键<kbd>ctrl</kbd><kbd>alt</kbd><kbd>X</kbd>
