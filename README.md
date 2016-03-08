#!/bin/sh

#### This README.md is a shell script 
exit 1
```
if [ -z "$1" ];then
echo "$0 [cattle-name] [port]"
exit 1
fi
if [ -z "$2" ];then
echo "$0 [cattle-name] [port]"
exit 1
fi
echo Launching cattle $1 into $2 space!
# Run it, port 80.
# Add app/config
# Add app/database
# Add public/theme
# Add files/
# Name the instance, use aerth/boltcms:latest image as base.

docker run -it -d -p $2:80 \
-v /cattle/$1/app/config:/var/www/app/config \
-v /cattle/$1/app/database:/var/www/app/database \
-v /cattle/$1/public/theme:/var/www/public/theme \
-v /cattle/$1/public/files:/var/www/public/files \
--name $1 aerth/boltcms:latest

echo Visit http://127.0.0.1:$2 (or http://$1)

#
```
#
