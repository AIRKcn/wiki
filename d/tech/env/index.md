# 开发环境


## 虚拟化

	Virtual Box + Ubuntu Server 15.10 + Docker 构建开发环境

* Virtual Box 5.10
* Ubuntu Netbook Image 15.10 [link](http://archive.ubuntu.com/ubuntu/dists/wily/main/installer-amd64/current/images/netboot/)
* Docker



1. 安装基本的 Ubuntu Linux Server VM
2. 配置网络
	1. NAT网卡 enp0s3 (DHCP) 用于访问公网
	2. Host网卡 enp0s8 (STATIC 192.168.56.50) 用于本地主机访问
3. 配置 apt source [link](https://lug.ustc.edu.cn/wiki/mirrors/help/ubuntu)
4. 安装 Virtual Box Additional for Linux
	`apt-get install -y dkms build-essential linux-headers-generic linux-headers-$(uname -r)`

----

1. 安装 docker.io docker-compose tmux zsh git 
2. 安装 wget ifstat htop

