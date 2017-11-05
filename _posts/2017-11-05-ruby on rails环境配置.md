## Xcode是什么？

Mac上建立程序开发环境的辅助应用程序,直接在App Store中下载，需要关闭VPN。

## 安装command line tools

- command line tools是什么？安装ruby需要的library，可以编译程序的软件，我们不直接使用。

- 如何安装？terminal中执行`xcode-select --install`。

- 如何确定已经装好？terminal中执行`xcode-select -p`,显示 /Applications/Xcode.app/Contents/Developer即是安装成功。

## 安装Hombrew

- Hombrew是什么？开发者社群为MacOSX打造的第三方套件管理的软件。

- 如何安装？terminal中执行指令：

        /usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"

- 参考：[homebrew官网](https://brew.sh/index_zh-tw.html)

## 安装git

- 使用Homebrew安装git,终端中执行`brew install git`。

- 如何确认安装成功？`git --version`,显示git版本。

## 安装ImageMagick

- 使用Homebrew安装ImageMagick,终端机中执行：`brew install imagemagick`。

- ImageMagick是处理图片的函式库，未来在ruby中会经常用到，所以提前安装。

## 安装 PostgreSQL

- PostgreSQL简介：资料库。

- 终端执行`brew install postgresql`。

安装完成后执行：

- `brew services start postgresql`，确保下次开机时开启资料库。

## 安装RVM

- RVM简介：

    ruby版本更新较快，在开放过程中经常会用到版本和权限的问题，因此通常不用内建的ruby，而是用RVM( Ruby Version Manager)去管理ruby的安装和升级。

- 安装：

    先执行`\curl -sSL https://get.rvm.io | bash -s stable`安装，再执行`source ~/.rvm/scripts/rvm`让rvm生效，最后安装一个套件`brew install libxml2`。

## 安装ruby

- 终端机输入：`rvm install 2.3.1`进行安装，然后输入：`rvm use 2.3.1 --default`  使ruby2.3.1为预设版本。`rvm list`能够显示安装的ruby版本。

- 直无法连上？

    https://rubygems.org是rubygems的来源，需要VPN才能连接。可以指定新的gem来源：

        gem sources --add https://gems.ruby-china.org/ --remove https://rubygems.org/

## 安装rails

终端输入：`gem install rails -v 5.0.0`，预设是最新版本，我们这里指定了版本。

安装失败原因：

- 墙是挡掉 rubygems.org ，需要打开VPN。

- gem和xcode-select不是最新版本，执行`gem update --system `和`xcode-select --install`更新。

## 安装Atom

[atom官网](https://atom.io/)中下载、解压、安装即可。


## 设定在terminal中打开atom

打开atom，点击菜单栏中的Atom,如何点击install shell commands，重启terminal即可。

## 总结

1. 首先安装Xcode和command line tool。

2. 安装Homebrew，然后利用Homebrew安装第三份套件。

3. 按照rvm，然后利用rvm安装ruby。

4. 使用gem命令安装rails。

5. 安装rails的编辑器atom。

**gem与homebrew的区别**

Homebrew使macOS更完整。使用gem来安装gems、用brew来安装那些依赖包。



