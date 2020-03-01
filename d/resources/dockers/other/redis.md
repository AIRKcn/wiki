# redis

#!/bin/bash

IMAGE="redis"
VERSION=""
C_NAME="redis"
ENVROOT="/data/etc"
ROOTDIR="/data/Cells/redis"
TPORT=6379
PASSWORD=""

EXISTS=$(docker ps | grep "$IMAGE$VERSION" | wc -l)
if [ $EXISTS="1" ]
then
	docker rm -f $C_NAME
fi

docker run -d \
--name=$C_NAME \
-v $ROOTDIR/data:/data \
-v $ROOTDIR/config/redis.conf:/usr/local/etc/redis/redis.conf \
-p $TPORT:6379 \
-e REDIS_PASS=$PASSWORD \
$IMAGE$VERSION



#cli
#!/bin/bash
docker run \
-it \
--link redis:redis \
--rm redis sh -c 'exec redis-cli -h "$REDIS_PORT_6379_TCP_ADDR" -p "$REDIS_PORT_6379_TCP_PORT"'
