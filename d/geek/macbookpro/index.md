# Macbook Pro 15

    我的第一台苹果笔记本

## 环境配置

### 安装 commandline 工具箱

Homebrow 依赖苹果官方的 commandline 工具箱。开发人员必装，没有之一。

### 安装Homebrow

[见官网](http://brew.sh/index_zh-cn.html "Homebrow官网" ">>")

顺便安装一个 [Caskroom](https://github.com/caskroom/homebrew-cask "Caskroom@Github" ">>")， 用于安装一些好用的 Application。


### 安装 NMP

[Nginx, MySQL, PHP](install.nmp.md)


### 常用工具

#### 命令行
* iTerm
* 替换shell环境 -> zsh
* svn, git
* curl, wget

### 安装扩展

#### Quicklook扩展

* WebP图片预览插件 [官网@Github](https://github.com/emin/WebPQuickLook "WebP预览" ">>")

```shell
curl -L https://raw.github.com/emin/WebPQuickLook/master/WebpQuickLook.tar.gz | tar -xvz
mkdir -p ~/Library/QuickLook/
mv WebpQuickLook.qlgenerator ~/Library/QuickLook/
qlmanage -r
```

### 技巧

* [设置ssh的自动化登录](http://blog.yongliang.info/2015/07/ssh_auto_login/ "" ">>")

## 资源汇总

### 苹果应用下载网站

* [browcask](https://github.com/caskroom/homebrew-cask "" ">>") :命令行安装应用程序
* [MacApp.so](http://www.macapp.so/ "" ">>") :新出的一个破解软件下载站，网站风格很优雅
* [MacX](http://soft.macx.cn/ "MacX" ">>") :比较老版的破解软件下载站
* [苹果软件园](http://www.maczapp.com/ "" ">>")


...待续
