### docker-php

最小化满足 php 开发的 docker 环境，使用国内镜像

### 软件

- nginx 最新
- php 7.4 (包含 swoole4.4 )
- composer
- redis 最新
- mysql 5.7
- nodejs 10
- npm
- yarn

### 配置

其他配置在对应目录下,数据库配置在 `docker-compose.yml` 里面，包含
```
MYSQL_DATABASE=default
MYSQL_USER=default
MYSQL_PASSWORD=root
MYSQL_ROOT_PASSWORD=root
```
项目目录为和 docker-php 同级的 wwwroot 目录（需要自己创建）

### 使用

```
git clone https://github.com/gzp199301/docker-php.git
cd docker-php
docker-compose up -d
```