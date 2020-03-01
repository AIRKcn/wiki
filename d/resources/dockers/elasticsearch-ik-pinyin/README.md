# README

## 基本信息

使用镜像为 `liukaitj/elasticsearch-ik-pinyin-docker`

* 源码 : @[`Github`](https://github.com/liukaitj/elasticsearch-ik-pinyin-docker)
* 介绍 : @[`Docker Hub`](https://hub.docker.com/r/liukaitj/elasticsearch-ik-pinyin-docker/)


## 使用

先解决启动问题
	将镜像中的 `config` 目录中的文件复制到 主机 `config` 目录中
	然后将 `before_run.sh` 复制到主机 `config` 目录中
再运行 `./run` 启动服务

### 映射

* 卷映射关系
	* `config` : 配置目录
	* `data` : 数据目录
	* `logs` : 日志目录
* 端口映射关系
	* `9200` : HTTP 服务端口
	* `9300` : ES 服务通讯端口
* 配置变量
	

### 存在问题

存在问题，通过 定制 `docker-entrypoint` 修复启动问题

__注意:__ 首第一次运行服务之前，先将镜像中 `/elasticsearch/config` 目录中的文件都复制到主机的 `config` 目录中

```
# docker run --name es -i -t liukaitj/elasticsearch-ik-pinyin-docker /bin/bash
$ exit
# docker cp es:/elasticsearch/config config
```

并将修复启动 `bug` 的引导 `before_run.sh` 复制到主机的 `config` 目录中


## Change Logs

### @ 2016-04-17

* 添加 配置和引导 [打包文件](elasticsearch-ik-pinyin.7z "下载" ">>")

