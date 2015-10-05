# 知识点总结

## GitHub
#### 1. Github上创建新项目静态网页
>0. 新建仓库，命名如：`qd`
1. 建立分支保存名称：`gh-pages`
2. 创建`index.html`文件
3. 输入`godi13.github.io/qd`即可登陆该分支网页

#### 2. 发现push版本错误等情况的时候

>[How to undo (almost) anything with Git](https://github.com/blog/2019-how-to-undo-almost-anything-with-git)

#### 3. ～/.gitconfig设置与Git技巧之小步快跑

```
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
```
`git throw` 用于在修改过程中，尚未推送前，回滚到最后一次推送的版本。  
`git throwh` 会删除掉最近一次推送的版本。  
`git rebase -i HEAD~~` 合并最近的两个版本，将第二行的`pick`改为`s`即可压缩，版本留言时可以删除其他只留一个。  
`git rebase -i origin/gh-pages` 合并最新版本到指定的指针所指版本之间所有的版本。

>参考视频教程：*HappyPeter* 老师的[如何利用Git辅助本地项目开发](http://haoduoshipin.com/v/92)和[git使用技巧：小步快跑](http://qd.haoduoshipin.com/p/git-tricks)
