#PHP开发环境（使用alpine）
# 由来

以前本地开发都使用 XAMPP ，经常需要切换工作目录，使用起来不很方便，就用docker 做了一个 PHP 开发环境。

# 特性

* 目前集成 php 、nginx、redis、mysql
* alpine 包较 ubuntu、centos 包体积小
* 配置任意版本，包括 nginx、mysql、redis、php
* 自由切换 htdocs 目录

# 使用帮助

## 安装运行

需要 docker 和 docker-compose，[下载地址](https://docs.docker.com/engine/installation/)

下载文件包：

```
https://github.com/spetacular/php-alpine/archive/master.zip 
```

解压后进入目录执行 build。如果下次启动时没更改 Dockerfile，就不需要再次build。只更改  docker-compose.yml 不需要重新 build。

```
docker-compose build
```

执行如下命令即可启动:

```
docker-compose up
```
## docker-compose.yml 字段说明

| 字段                  | 说明                        |
| ------------------- | ------------------------- |
| ports               | 端口映射，本机端口：docker端口。只能改本机。 |
| volumes             | 文件夹映射，本机目录：docker目录。只能改本机 |
| MYSQL_ROOT_PASSWORD | mysql root用户默认密码          |



# 注意事项

由于代码跑在docker里，所以 localhost 和 127.0.0.1不再可用。如需要连接 redis 和 mysql，应使用如下地址：

```redis-server
redis-server
mysql-server
```

