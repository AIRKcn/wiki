# 加速源列表

## 国内开源镜像

 * [阿里](https://opsx.alibaba.com/mirror "" ">>")
 * [搜狐](http://mirrors.sohu.com/ "" ">>")
 * [网易](http://mirrors.163.com/ "" ">>")
 * ~~[新浪](http://mirrors.sina.com/ "" ">>")~~ 已废弃
 * [京东](http://mirror.jdcloud.com/ "" ">>")
 * [中国科学技术大学](http://mirrors.ustc.edu.cn/ "" ">>") [团队Wiki](https://lug.ustc.edu.cn/wiki/start "" ">>")
 * [清华大学开源软件镜像站](https://mirrors.tuna.tsinghua.edu.cn "" ">>")
 * [南京邮电大学开源软件镜像站](http://mirrors.njupt.edu.cn/ "" ">>")


__提示__: 没事儿就上这几家转转，经常能发现一些好玩的东东

## CentOS 系统加速源

>   [阿里源 - CentOS](http://mirrors.aliyun.com/help/centos "" ">>")
>
>   1. 备份
```shell
    mv /etc/yum.repos.d/CentOS-Base.repo /etc/yum.repos.d/CentOS-Base.repo.backup
```
>   2. 下载新的CentOS-Base.repo 到/etc/yum.repos.d/
>       `CentOS 5`
```shell
    wget -O /etc/yum.repos.d/CentOS-Base.repo http://mirrors.aliyun.com/repo/Centos-5.repo
```
>       `CentOS 6`
```shell
    wget -O /etc/yum.repos.d/CentOS-Base.repo http://mirrors.aliyun.com/repo/Centos-6.repo
```
>       `CentOS 7`
```shell
    wget -O /etc/yum.repos.d/CentOS-Base.repo http://mirrors.aliyun.com/repo/Centos-7.repo
```
>   3. 之后运行 `yum makecache` 生成缓存

扩展，如果需要使用 epel 源，可更改系统配置为

>   [阿里源 - Epel](http://mirrors.aliyun.com/help/epel "" ">>")
>
>   Epel
>
>   1. 备份(如有配置其他epel源)
```shell
    mv /etc/yum.repos.d/epel.repo /etc/yum.repos.d/epel.repo.backup
    mv /etc/yum.repos.d/epel-testing.repo /etc/yum.repos.d/epel-testing.repo.backup
```
>   2. 下载新repo 到/etc/yum.repos.d/
>       `epel(RHEL 7)`
```shell
    wget -O /etc/yum.repos.d/epel.repo http://mirrors.aliyun.com/repo/epel-7.repo
```
>       `epel(RHEL 6)`
```shell
    wget -O /etc/yum.repos.d/epel.repo http://mirrors.aliyun.com/repo/epel-6.repo
```
>       `epel(RHEL 5)`
```shell
    wget -O /etc/yum.repos.d/epel.repo http://mirrors.aliyun.com/repo/epel-5.repo
```

## Python pypi 加速源

>   [使用镜像服务器加速你的Python PyPi](http://www.acgso.com/2013/08/using-mirror-accelerate-python-pypi/ "" ">>")
>   [使用国内镜像源来加速python pypi包的安装](http://topmanopensource.iteye.com/blog/2004853 "" ">>")

>   修改 ~/.pip/pip.conf
>   使用 [阿里源](http://mirrors.aliyun.com/help/pypi "" ">>")
```config
[global]
index-url = http://mirrors.aliyun.com/pypi/simple/
```
>   使用 [豆瓣源](http://pypi.douban.com/ "" ">>")
```conf
[global]
timeout = 6000
index-url = http://pypi.douban.com/simple/
trusted-host = pypi.douban.com
[install]
use-mirrors = true
mirrors = http://pypi.douban.com/
```

## Homebrew 加速源

>    [中国科学技术大学 - Homebrew](https://lug.ustc.edu.cn/wiki/mirrors/help/brew.git "" ">>")
>   替换 homebrew 默认源
```shell
cd /usr/local
git remote set-url origin git://mirrors.ustc.edu.cn/brew.git
```

## Cygwin 系统加速源

>    [阿里源 - Cygwin](http://mirrors.aliyun.com/help/cygwin "" ">>")
>   在安装的过程中选择 'Install from Internet'，填入以下地址
>   `http://mirrors.aliyun.com/cygwin/`

## Ruby Gem 加速源

>   ~~[淘宝源 - Ruby](http://ruby.taobao.org "" ">>")~~
>   [阿里源 - Rubygems](http://mirrors.aliyun.com/help/rubygems "" ">>")
```shell
    gem sources -l
    # 移除 https://rubygems.org源
    gem sources -r https://rubygems.org/
    # 增加 http://ruby.taobao.org/源
    gem sources -a http://mirrors.aliyun.com/rubygems/
    # 更新缓存
    gem sources -u
```
>    如果你是用 Bundle (Rails 项目)
```shell
    source 'http://mirrors.aliyun.com/rubygems/'
    gem 'rails', '4.0.2'
```

## NodeJS Package 加速源

>   [淘宝源 - NodeJs npm](https://npm.taobao.org/ "" ">>")

>   [CNPM](http://cnpmjs.org/ "" ">>")
>
>   [给电脑换源 npm 国内镜像 cnpm](http://yijiebuyi.com/blog/b12eac891cdc5f0dff127ae18dc386d4.html "" ">>")

1. 通过 config 配置指向国内镜像源
npm config set registry http://registry.cnpmjs.org
npm info express  //下载安装第三方包
2. 通过 npm 命令指定下载源
npm --registry http://registry.cnpmjs.org info express
3. 在配置文件 ~/.npmrc 文件写入源地址
vim ~/.npmrc   //打开配置文件
registry =https://registry.npm.taobao.org   //写入配置文件
推荐使用最后一种方法, 一劳永逸, 前面 2 钟方法都是临时改变包下载源.

>   [快速搭建 Node.js 开发环境以及加速 npm](http://segmentfault.com/a/1190000000454456 "" ">>")


## Google Fonts 国内镜像加速

>   [基于七牛云](http://fonts.gmirror.org/)

把 //fonts.googleapis.com 替换为 //fonts.gmirror.org 即可。

>   [360 网站卫士常用前端公共库 CDN 服务](http://libs.useso.com/ "" ">>")
>   [科大博客提供 Google Fonts 加速](https://servers.ustclug.org/2014/06/blog-googlefonts-speedup/ "" ">>")

1. ajax.googleapis.com => ajax.lug.ustc.edu.cn
2. fonts.googleapis.com => fonts.lug.ustc.edu.cn
3. themes.googleusercontent.com => google-themes.lug.ustc.edu.cn

## JavaScript 常见库国内镜像加速

>   [BootCDN](http://www.bootcdn.cn/ "" ">>")

## Ubuntu 系统加速源

>   [Ubuntu中文社区-源列表](http://wiki.ubuntu.org.cn/%E6%BA%90%E5%88%97%E8%A1%A8 "" ">>")

>   [阿里源 - Ubuntu](http://mirrors.aliyun.com/help/ubuntu "" ">>")
>
>   1. 软件包管理中心（推荐）
>       在软件包管理中心“软件源”中选择“中国的服务器”下mirros.aliyun.com即可自动使用
>   2. 手动更改配置文件
>       编辑/etc/apt/sources.list文件(需要使用sudo), 在文件最前面添加以下条目(操作前请做好相应备份)
>   `Quantal(12.10)`
```conf
deb http://mirrors.aliyun.com/ubuntu/ quantal main restricted universe multiverse
deb http://mirrors.aliyun.com/ubuntu/ quantal-security main restricted universe multiverse
deb http://mirrors.aliyun.com/ubuntu/ quantal-updates main restricted universe multiverse
deb http://mirrors.aliyun.com/ubuntu/ quantal-proposed main restricted universe multiverse
deb http://mirrors.aliyun.com/ubuntu/ quantal-backports main restricted universe multiverse
deb-src http://mirrors.aliyun.com/ubuntu/ quantal main restricted universe multiverse
deb-src http://mirrors.aliyun.com/ubuntu/ quantal-security main restricted universe multiverse
deb-src http://mirrors.aliyun.com/ubuntu/ quantal-updates main restricted universe multiverse
deb-src http://mirrors.aliyun.com/ubuntu/ quantal-proposed main restricted universe multiverse
deb-src http://mirrors.aliyun.com/ubuntu/ quantal-backports main restricted universe multiverse
```
>   `Precise(12.04)`
```conf
deb http://mirrors.aliyun.com/ubuntu/ precise main restricted universe multiverse
deb http://mirrors.aliyun.com/ubuntu/ precise-security main restricted universe multiverse
deb http://mirrors.aliyun.com/ubuntu/ precise-updates main restricted universe multiverse
deb http://mirrors.aliyun.com/ubuntu/ precise-proposed main restricted universe multiverse
deb http://mirrors.aliyun.com/ubuntu/ precise-backports main restricted universe multiverse
deb-src http://mirrors.aliyun.com/ubuntu/ precise main restricted universe multiverse
deb-src http://mirrors.aliyun.com/ubuntu/ precise-security main restricted universe multiverse
deb-src http://mirrors.aliyun.com/ubuntu/ precise-updates main restricted universe multiverse
deb-src http://mirrors.aliyun.com/ubuntu/ precise-proposed main restricted universe multiverse
deb-src http://mirrors.aliyun.com/ubuntu/ precise-backports main restricted universe multiverse
```
>   `Oneiric(11.10)`
```conf
deb http://mirrors.aliyun.com/ubuntu/ oneiric main restricted universe multiverse
deb http://mirrors.aliyun.com/ubuntu/ oneiric-security main restricted universe multiverse
deb http://mirrors.aliyun.com/ubuntu/ oneiric-updates main restricted universe multiverse
deb http://mirrors.aliyun.com/ubuntu/ oneiric-proposed main restricted universe multiverse
deb http://mirrors.aliyun.com/ubuntu/ oneiric-backports main restricted universe multiverse
deb-src http://mirrors.aliyun.com/ubuntu/ oneiric main restricted universe multiverse
deb-src http://mirrors.aliyun.com/ubuntu/ oneiric-security main restricted universe multiverse
deb-src http://mirrors.aliyun.com/ubuntu/ oneiric-updates main restricted universe multiverse
deb-src http://mirrors.aliyun.com/ubuntu/ oneiric-proposed main restricted universe multiverse
deb-src http://mirrors.aliyun.com/ubuntu/ oneiric-backports main restricted universe multiverse
```
>   `Natty(11.04)`
```conf
deb http://mirrors.aliyun.com/ubuntu/ natty main restricted universe multiverse
deb http://mirrors.aliyun.com/ubuntu/ natty-security main restricted universe multiverse
deb http://mirrors.aliyun.com/ubuntu/ natty-updates main restricted universe multiverse
deb http://mirrors.aliyun.com/ubuntu/ natty-proposed main restricted universe multiverse
deb http://mirrors.aliyun.com/ubuntu/ natty-backports main restricted universe multiverse
deb-src http://mirrors.aliyun.com/ubuntu/ natty main restricted universe multiverse
deb-src http://mirrors.aliyun.com/ubuntu/ natty-security main restricted universe multiverse
deb-src http://mirrors.aliyun.com/ubuntu/ natty-updates main restricted universe multiverse
deb-src http://mirrors.aliyun.com/ubuntu/ natty-proposed main restricted universe multiverse
deb-src http://mirrors.aliyun.com/ubuntu/ natty-backports main restricted universe multiverse
```


## Cydia 源

>   [常用Cydia源地址大全](http://www.25pp.com/news/news_69368.html "" ">>")

## CDN

>   [BootCDN](http://www.bootcdn.cn/ "" ">>")
