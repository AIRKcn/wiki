# 镜像

## 构建第一个镜像

基于现有的操作系统，构建基本的镜像

```shell
BASE_IMAGE_NAME="镜像名称"
tar cv --files-from /dev/null | docker import - $BASE_IMAGE_NAME
```

## 基于基本镜像构建自己的镜像
