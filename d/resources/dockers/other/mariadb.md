# 未通过
docker run --name mariadb --link some-mariadb:mysql -d application-that-uses-mysql

# run
#!/bin/bash

IMAGE="mariadb"
VERSION=""
C_NAME="mariadb"
ENVROOT="/data/etc"
ROOTDIR="/data/Cells/mariadb"
TPORT=3306
PASSWORD="maria.pwd"

EXISTS=$(docker ps | grep "$IMAGE$VERSION" | wc -l)
if [ $EXISTS="1" ]
then
	docker rm -f $C_NAME
fi

docker run -d \
--name=$C_NAME \
-v $ROOTDIR/data:/var/lib/mysql \
-v $ROOTDIR/config:/etc/mysql/conf.d \
-p $TPORT:3306 \
-e MYSQL_ROOT_PASSWORD=$PASSWORD \
$IMAGE$VERSION

# cli
#!/bin/bash

docker run \
-it \
--link mysql:mysql \
--rm mariadb sh -c 'exec mysql -h"$MYSQL_PORT_3306_TCP_ADDR" -P"$MYSQL_PORT_3306_TCP_PORT" -uroot -p"$MYSQL_ENV_MYSQL_ROOT_PASSWORD"'

# 手工启动

docker run -i -t \
--name=$C_NAME \
-v $ROOTDIR/data:/var/lib/mysql \
-v $ROOTDIR/config:/etc/mysql/conf.d \
-p $TPORT:3306 \
-e MYSQL_ROOT_PASSWORD=$PASSWORD \
$IMAGE$VERSION
