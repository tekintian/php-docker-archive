#Docker Build命令

***
##基础包

	cd /Users/Github/docker-base && docker build -t tekintian/docker-base .

##php

	cd /Users/Github/php/php-5.6 && docker build -t tekintian/php:5.6.38 .

	cd /Users/Github/php/php-7.0 && docker build -t tekintian/php:7.0.32 .

	cd /Users/Github/php/php-7.1 && docker build -t tekintian/php:7.1.24 .

	cd /Users/Github/php/php-7.2 && docker build -t tekintian/php:7.2.12 .

	cd /Users/Github/php/php-7.3-dev && docker build -t tekintian/php:7.3-build20181202 .



docker tag tekintian/php:7.2.12 tekintian/php:7.2
docker tag tekintian/php:7.1.24 tekintian/php:7.1
docker tag tekintian/php:7.0.32 tekintian/php:7.0
docker tag tekintian/php:5.6.38 tekintian/php:5.6


## tengine

cd /Users/Github/tengine-php/php-7.2-waf && docker build -t tekintian/tengine-php:7.2.12-waf .
cd /Users/Github/tengine-php/php-7.2 && docker build -t tekintian/tengine-php:7.2.12 .

cd /Users/Github/tengine-php/php-7.1 && docker build -t tekintian/tengine-php:7.1.24 .
cd /Users/Github/tengine-php/php-7.1-waf && docker build -t tekintian/tengine-php:7.1.24-waf .

cd /Users/Github/tengine-php/php-7.0 && docker build -t tekintian/tengine-php:7.0.30 .
cd /Users/Github/tengine-php/php-7.0-waf && docker build -t tekintian/tengine-php:7.0.30-waf .

cd /Users/Github/tengine-php/php-5.6 && docker build -t tekintian/tengine-php:5.6.36 .


#nginx-php

cd /Users/Github/nginx-php/7.3-waf && docker build -t tekintian/nginx-php:7.3-build20180428 .

cd /Users/Github/nginx-php/7.2-waf && docker build -t tekintian/nginx-php:7.2.12-waf .
cd /Users/Github/nginx-php/7.2 && docker build -t tekintian/nginx-php:7.2.12 .

cd /Users/Github/nginx-php/7.1 && docker build -t tekintian/nginx-php:7.1.24 .
cd /Users/Github/nginx-php/7.1-waf && docker build -t tekintian/nginx-php:7.1.24-waf .

cd /Users/Github/nginx-php/7.0 && docker build -t tekintian/nginx-php:7.0.30 .
cd /Users/Github/nginx-php/7.0-waf && docker build -t tekintian/nginx-php:7.0.30-waf .

cd /Users/Github/nginx-php/5.6 && docker build -t tekintian/nginx-php:5.6.36 .

## 推送
docker push tekintian/nginx-php:7.3-build20180428
docker push tekintian/nginx-php:7.2.12-waf
docker push tekintian/nginx-php:7.2.12
docker push tekintian/nginx-php:7.1.24-waf
docker push tekintian/nginx-php:7.1.24
docker push tekintian/nginx-php:7.0.30-waf
docker push tekintian/nginx-php:7.0.30
docker push tekintian/nginx-php:5.6.36

tag 给镜像起别名
Usage:	docker tag SOURCE_IMAGE[:TAG] TARGET_IMAGE[:TAG]

Create a tag TARGET_IMAGE that refers to SOURCE_IMAGE

docker tag tekintian/php:7.1.24 tekintian/php:7.1

***
#Run：

docker run -it -d --name base -v /Users/Github/diy:/diy tekintian/docker-base
docker exec -it base bash

docker run -it -d --name php70 -v /Users/Github/diy:/diy tekintian/php:7.0.28
docker exec -it php70 bash

docker run -it -d --name php72 -v /Users/Github/diy:/diy tekintian/php:7.2.3
docker exec -it php72 bash



