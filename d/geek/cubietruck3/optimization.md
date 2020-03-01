### [返回 Cubietruck3](index.md)

------

# 系统优化

## 硬件

### TTL线链接

__参考__

* http://www.ngu.tw/blog/wei/archives/913

### 关闭LED

关闭 LED。以下命令用于调节 4 个 LED 的亮度，让它们的亮度为 0：

```shell
# ls /sys/class/leds/*/brightness | xargs -i -n1 echo "echo 0 > {}" | sh
```

我们把此段命令加入到 /etc/rc.local 中，这样每次系统启动时都会将 LED 亮度调整为 0。

__参考__

* http://name5566.com/4398.html#comment-7416



## 存储

### 合并NAND分区

通过刷nand-img将系统刷入之后，查看可见nand仅使用了2G的空间，Cubietruck提供了8G的存储并未完全利用。可通过将nand的分区合并充份使用系统提供的存储能空间。

__方法__
```shell
# nand-part -f a20 /dev/nand 32768 'bootloader 131072' 'rootfs 14778368'
```

__参考__

* http://name5566.com/4398.html
* http://linux-sunxi.org/Installing_to_NAND


### 挂载NTFS磁盘

修改 /etc/fstab 添加下面内容

```shell
/dev/sdaX /media/Y ext3 defaults 0 1
```

__参考__

* http://blog.csdn.net/c395565746c/article/details/5424196
* http://forum.cubietech.com/forum.php?mod=viewthread&tid=1234&extra=page%3D3


### 配置Samba服务

__参考__

* http://forum.cubietech.com/forum.php?mod=viewthread&tid=2960


## 软件

### 服务器性能监控工具

```shell
apt-get install -y glances htop iotop
```

### 修正更新源

修改 `/etc/apt/source.list` 将原来的源地址改为

```shell
deb http://ports.ubuntu.com/ubuntu-ports/ utopic main universe
deb-src http://ports.ubuntu.com/ubuntu-ports/ utopic main universe
```

__参考__

* http://forum.cubietech.com/forum.php?mod=viewthread&tid=3005


### 系统备份和恢复

假设 NANDIMG='`/data/nand.ddimg.gz`'

__备份__

```shell
# dd if=/dev/nand conv=sync,noerror bs=64K | gzip -c -9 > $NANDIMG
```

__恢复__

```shell
# cd /data/
# gunzip nand.ddimg.gz ; dd if=$NANDIMG conv=sync,noerror bs=64K of=/dev/nand
```

__参考__

* http://blog.csdn.net/linuxchen/article/details/18709017

### 关闭irqbalance服务

>   内存占用超大的一个服务，当我正在备份MySQL数据库的时候，警告我内存不足，才发现的这个服务进程。查了一下资料，才知道这个服务进程是可以用于在多核服务器上分配进程使用的。

```shell
service irqbalance stop
```

__参考__

* [深度剖析告诉你irqbalance有用吗](http://blog.yufeng.info/archives/2422)
* [cpuspeed和irqbalance服务器的两大性能杀手](http://wubx.net/stop-irqbalance-and-cpuspeed/)

### 在CT制作卡系统

* http://forum.cubietech.com/forum.php?mod=viewthread&tid=2424&extra=page%3D3

### 管理自启动服务

```shell
apt-get install -y sysv-rc-conf
sysv-rc-conf
```

* [Ubuntu 服务优化说明](http://www.linuxidc.com/Linux/2012-10/73123p2.htm "" ">>")

### 选择时区

```shell
# tzselect
# sudo cp /usr/share/zoneinfo/Asia/Shanghai /etc/localtime
# sudo ntpdate time.windows.com
```

## 开发工具

### 安装 JavaSDK

__下载说明页面__

* http://www.oracle.com/technetwork/java/javase/downloads/jdk8-arm-downloads-2187472.html

__查看安装包及源中的安装信息__

__参考__

* http://www.cnblogs.com/forward/archive/2012/01/10/2318483.html

### 安装开发工具包

```shell
# apt-get install build-essential
```

## 本地化

### 让系统显示中文

__基于 Lubuntu Desktop 1.02__

```shell
# cp /usr/share/i18n/SUPPORTED /var/lib/locales/supported.d/local
# 删除不需要的语言
# vi /var/lib/locales/supported.d/local
# 重新生成locale支持文件，慢慢等待一下至运行完成
# locale-gen --purge
```

### 让VIM支持中文

__参考__

* http://blog.csdn.net/feiniao1221/article/details/7000868

### 如何安装SD卡上的第二系统，考虑安装一个LUbuntu Desktop CN版

准备 sdcard 一个，至少要2G，建议大些，8G以上吧。

__参考__

* http://docs.cubieboard.org/tutorials/ct1/installation/install_lubuntu_desktop_server_to_sd_card
* http://forum.cubietech.com/forum.php?mod=viewthread&tid=1698


## 网络

### 如何将WLan提供给周边做为热点使用？

__参考__

* http://forum.cubietech.com/forum.php?mod=viewthread&tid=1544

* [【原创】让CubieBoard具备WIFI AP热点功能](http://forum.cubietech.com/forum.php?mod=viewthread&tid=424)

### 利用Cubieborad破解WiFi

__参考__

* http://blog.hibeiyu.com/archives/518
