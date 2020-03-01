# 安装 Nginx MySQL PHP-fpm

前提示在苹果电脑下已经安装好

1. CommandLine Toolkit
2. Homebrew

----

## 更新 Homebrew

```shell
brew update
# 安装php扩展库
brew tap homebrew/dupes
brew tap josegonzalez/homebrew-php
# 查看仓库中可用的php5.x的版本及扩展
brew search php5
```

----

## 命令行安装 PHP-fpm

假如我们要安装的是 PHP 5.6 的版本

```shell
brew update
brew install php56 --with-fpm --with-gmp --with-imap --with-tidy --with-debug --with-mysql --with-libmysql
brew install php56-memcache php56-memcached php56-redis php56-mongo php56-gearman php56-mcrypt php56-thrift php56-imagick php56-sphinx php56-xhprof php56-pdo-pgsql
```
### 更换系统自带的 PHP

由于Mac自带了php和php-fpm，因此需要添加系统环境变量PATH来替代自带PHP版本。

```shell
echo 'export PATH="$(brew --prefix php56)/bin:$PATH"' >> ~/.bash_profile  #for php
echo 'export PATH="$(brew --prefix php56)/sbin:$PATH"' >> ~/.bash_profile  #for php-fpm
echo 'export PATH="/usr/local/bin:/usr/local/sbib:$PATH"' >> ~/.bash_profile #for other brew install soft
source ~/.bash_profile
```

### 设置 PHP-fpm 开机启动

```shell
ln -sfv /usr/local/opt/php56/*.plist ~/Library/LaunchAgents
launchctl load ~/Library/LaunchAgents/homebrew.mxcl.php56.plist
```

----

## 命令行安装 Nginx 和 MySQL

```shell
brew update
brew install nginx mysql
```

### Nginx开机启动

```shell
ln -sfv /usr/local/opt/nginx/*.plist ~/Library/LaunchAgents
launchctl load ~/Library/LaunchAgents/homebrew.mxcl.nginx.plist
```


### 目录和权限设置

Nginx监听80端口需要root权限执行，因此：

```shell
sudo chown root:wheel /usr/local/Cellar/nginx/1.6.0_1/bin/nginx
sudo chmod u+s /usr/local/Cellar/nginx/1.6.0_1/bin/nginx
```

为 nginx 创建需要用到的目录：

```shell
mkdir -p /usr/local/var/logs/nginx
mkdir -p /usr/local/etc/nginx/sites-available
mkdir -p /usr/local/etc/nginx/sites-enabled
mkdir -p /usr/local/etc/nginx/conf.d
mkdir -p /usr/local/etc/nginx/ssl
sudo mkdir -p /var/www
sudo chown :staff /var/www
sudo chmod 775 /var/www
```

__提示__: 对于 document_root 目录无权限报 403 的解决办法

将 nobody _www www 三个用户添加到 admin 组中

```shell
dscl
cd /Local/Default/Groups
append admin GroupMembership nobody
append admin GroupMembership www
append admin GroupMembership _www
quit
```

----

## 参考

### 关于 dscl 命令，可以参考

1. [Mac Tips: 给用户增加用户组](http://duffqiu.github.io/blog/2014/01/30/mac-tips-gei-yong-hu-zeng-jia-yong-hu-zu/ "" ">>")
2. [Mac OS X 10.5: Use the command line utility "dscl" for some functions formerly found in NetInfo Manager]( "https://support.apple.com/zh-cn/HT2294" ">>")

### 通过 Homebrew 安装 NMP 服务

1. [全新安装Mac OSX 开发者环境 同时使用homebrew搭建 PHP，Nginx ，MySQL，Redis，Memcache ... ... (LNMP开发环境)](http://segmentfault.com/a/1190000000606752 "" ">>")
