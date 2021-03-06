# Jekyll

## [安装](http://jekyll.bootcss.com/docs/installation/)

#### Ubuntu 环境配置

1.安装[RVM](http://rvm.io/)、Ruby

    gpg --keyserver hkp://keys.gnupg.net --recv-keys 409B6B1796C275462A1703113804BB82D39DC0E3
    \curl -sSL https://get.rvm.io | bash -s stable
    source ~/.rvm/scripts/rvm
    rvm requirements     //安装RVM环境依赖
    rvm install ruby     //安装ruby
    rvm list             //查看安装ruby版本号
    rvm use 2.2          //切换ruby版本如2.2

>注意：使用`rvm use`命令需要打开终端菜单栏中的 `Edit`-`Profile Preferences`-`Title and Command`中勾选`Command`下的`Run conmand as a login shell`，[详细说明](https://rvm.io/integration/gnome-terminal)

2.安装RubyGems

先下载[TGZ](https://rubygems.org/pages/download#formats)

    tar zxvf filename.tgz   //解压缩ruby
    cd filename             //进入ruby文件
    sudo ruby setup.rb      //安装rubygems

3.安装[Jekyll](https://docs.rubygems.org/gems/jekyll/versions/3.0.0.pre.beta10)

    sudo gem install jekyll --pre    //最新版需要ruby2.0以上版本
    //如果安装出现问题
    gem sources --remove https://rubygems.org/
    gem sources -a http://rubygems.org/

#### 命令行

    $ jekyll
      NAME:
        jekyll

      DESCRIPTION:
        Jekyll is a blog-aware, static site generator in Ruby

      COMMANDS:
        build                Build your site
        default
        docs                 Launch local server with docs for Jekyll v1.3.0
        doctor               Search site and print specific deprecation warnings
        help                 Display global or [command] help documentation.
        import               Import your old blog to Jekyll
        new                  Creates a new Jekyll site scaffold in PATH
        serve                Serve your site locally

      ALIASES:
        hyde                 doctor
        server               serve

      GLOBAL OPTIONS:
        -s, --source [DIR]
            Source directory (defaults to ./)
        -d, --destination [DIR]
            Destination directory (defaults to ./_site)
        --safe
            Safe mode (defaults to false)
        -p, --plugins PLUGINS_DIR1[,PLUGINS_DIR2[,...]]
            Plugins directory (defaults to ./_plugins)
        --layouts DIR
            Layouts directory (defaults to ./_layouts)
        -h, --help
            Display help documentation
        -v, --version
            Display version information
        -t, --trace
            Display backtrace when an error occurs

#### _config.yml 配置

    defaults:
      -
        values:
          layout: "default"

    统一文件默认布局
