### 1、拉取 mysqll 8.0

``` powershell
$ docker pull mysql:8.0
```

### 2、创建容器

``` powershell
# 创建容器
$ docker run \
-itd \
--name mysql \
-p 3306:3306 \
-v /DockerData/mysql/conf:/etc/mysql/conf.d \
-v /DockerData/mysql/data:/var/lib/mysql \
-v /DockerData/mysql/log:/var/log/mysql \
-e MYSQL_ROOT_PASSWORD=123456	\
--restart always \
--privileged=true \
mysql8.0

# 设置 mysql 系统时间和物理机环境一致，需要设置 localtime
$ -v /etc/localtime:/etc/localtime

# 查看创建容器是否成功
$ docker ps -a

# 查看 mysql 日志
$ docker logs -f mysql
```

### 3、登录

#### docker

``` powershell
# 登录 docker
$ docker exec -it mysql:/bin/bash
# 连接 mysql
$ mysql -u root -p
```

#### mycli

``` powershell
# 连接 mysql
$ mycli -u roo - p
```
