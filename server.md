# 服务器相关

#### 1. 初步设置服务器
1. 启用服务器
2. `ssh root@公网IP`
3. `apt-get update`
4. `apt-get install nginx`
5. `service nginx status`查看状态
6. 如果成功，浏览器中输入ip即可登陆
7. 登陆本地终端，上传指令`scp -r 目录名 root@公网IP:`，冒号不能忘
8. 在服务器终端可以输入`ls`查看
9. 查看nginx默认配置`cat /etc/nginx/sites-enabled/default`，查找存放项目位置，如`root /usr/share/nginx/html`
10. `cp 目录名/* /usr/share/nginx/html`
11. `cd /usr/share/nginx/html`
12. `ls`查看确认

***

#### 2. 服务器相关指令
1. `lsb_release -a` 查看服务器系统版本
2. `scp filename/folder -r root@公网IP 或 域名:/usr/share/nginx/html/` 上传文件到服务器指定位置
3. `scp filename/folder -r root@公网IP 或 域名:/usr/share/nginx/html/ .` 下载文服务器上的文件到本地
4. `rsync -r --delete filename/folder root@公网IP 或 域名:`同步本地与服务器的文件[rsync](https://rsync.samba.org/)
5. `rsync -rv --dry-run --delete filename/folder root@公网IP 或 域名:`同步文件,`v`报告信息，`--dry-run`虚拟执行
6. `logout` 退出回到本地终端

***

#### 3. 本地SSH设置
1. `sudo vim /etc/hosts` 添加ip地址，设置别名，如`127.0.0.1 loc`
2. 不输密码登陆服务器设置步骤：
    * `ssh-keygen` 生成SSH密钥
    * `cd .ssh`
    * `id_rsa.pub`拷贝到服务器
    * `ssh-copy-id root@公网IP`
3. 自定义登陆服务器指令：
    * `cd /bin`
    * 新建`sudo vim name_ssh`
    * 添加`ssh root@公网IP`后<kbd>Z</kbd><kbd>Z</kbd>
    * `sudo chmod +x name_ssh`添加执行权限
    * 输入`name_ssh`即可登陆网站服务器

***

#### 4. 服务器本地同步脚本设置

    bin cat filename.sh
    #!/usr/bin/env bash

    cd ~/项目位置
    git add -A
    git commit -a -m"i"
    git push
    ssh root@公网IP或域名 'source .bashrc && ~/bin/filename.sh'

    //source .bashrc 的意思是：运行一下 .bashrc 中的初始化语句。
    //~/bin/filename.sh 的意思是执行 filename.sh 这个脚本

      注意，这个脚本是存放在服务器之上的。里面的内容是：

    cd ~/foldername/
    git pull
    /home/peter/.rbenv/shims/bundle
    /home/peter/.rbenv/shims/bundle exec /home/peter/.rbenv/shims/rake db:migrate RAILS_ENV=production
    /home/peter/.rbenv/shims/bundle exec /home/peter/.rbenv/shims/rake assets:precompile RAILS_ENV=production
    touch tmp/restart.txt

    //注意：最后四句是Rails部署相关代码，可以忽略

>[安装开发环境](http://book.haoduoshipin.com/go-responsive/c/chap-2.html)  
>[browsersync使用说明](http://www.browsersync.cn/#install)

    与服务器同步文件的脚本

    #!/usr/bin/env bash
    sync_server()
    {
        echo
        rsync -arv  --exclude "css" --exclude ".git" --exclude "node_modules" --exclude "_site"  --delete ~/Desktop/res-demo/ peter@haoduoshipin.com:~/res-demo/
        echo
    }

    sync_server
