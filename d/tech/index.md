# 技术



## 资料查询

[RFC Index](http://www.rfc-editor.org/rfc-index2.html)

## 在指定的目录中遍历所有 git 本地仓库，并更新代码
```
#!/bin/bash

CURRENT=`pwd`

for i in `ls`
do
    if [ -d $i ]
    then
        cd $i
        echo "PATH : $CURRENT/$i"
        git pull
        cd - > /dev/null 2>&1
    fi
done
```



## 在已经打开的页面中注入指定的 javascript 代码

```
var script=document.createElement("script");  
script.type="text/javascript";  
script.src="http://cdn.bootcss.com/jquery/3.0.0-alpha1/jquery.min.js";  
document.getElementsByTagName('head')[0].appendChild(script);
```

## Ubuntu Server 14.04

### 中文环境

1. 查看当前的 `locale` 设置，输入

```
locale -a
```

2. 用文本编辑器 (我用的是 `vim` )，如果文件不存在则新建。

```
vim /var/lib/locales/supported.d/local
```

在文件中加入下面2行:

```
zh_CN.UTF-8 UTF-8
en_US.UTF-8 UTF-8
```

3. 用 `vim` 编辑 文件 `/etc/environment`

```
vim /etc/environment
```

在文件中加入：

```
LANG="zh_CN.UTF-8"
LANGUAGE="zh_CN:zh:en_US:en"
LC_CTYPE="zh_CN.UTF-8"  
```


4. 生成需要的 `locale` 文件，在终端中输入:

```
# 可以加 --purge参数用来删除所有旧的配置，在出现问题时很有用
locale-gen
```
