## Consul-Cluster

docker-compose consul集群

### 组件（容器）及相关软件版本

* Consul：latest

### 目录结构

    cluster
    |----/config                 配置文件目录
    |----/data                   持久化数据目录
    |----/.env-example           配置文件
    |----/docker-compose.yml     docker compose 配置文件

## 开始安装

没有安装 Docker 的同学移步 [安装教程](https://github.com/telanflow/consul-cluster.git#安装-docker-及相关工具)，如果你有足够的时间强烈建议通读 [Docker — 从入门到实践](https://yeasy.gitbooks.io/docker_practice/content/)

    cd ~/
    git clone https://github.com/telanflow/consul-cluster.git

    cd dnmp
    cp .env-example .env

    # 修改配置
    vim .env

    # 构建全部镜像并启动容器
    sudo docker-compose up --build -d

    # 构建单个镜像并启动容器
    sudo docker-compose build --no-cache [srv1 |srv2|srv3|ui ...]

启动成功访问 http://localhost:8500/ui 即可

## 安装 Docker 及相关工具

### 安装 docker（2选1）
    
1、参考 daocloud 提供的文档（推荐）

    # 注意按照文档如果执行类似 install docker-ce=17.03.1* 出错，执行 install docker-ce 即可
    https://download.daocloud.io/Docker_Mirror/Docker

2、ubuntu 系统（可能不是最新版本的，适合学习或者测试用）

    apt-get update && apt install docker.io    
    
### 安装 docker-compose
    
    sudo curl -L "https://github.com/docker/compose/releases/download/1.23.2/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
    
    sudo chmod +x /usr/local/bin/docker-compose

### 启动 Docker

    sudo service docker start
    sudo docker info

### 配置 DockerHub 加速器（你用的阿里云也许不用配置，如果觉得下载镜像很慢就配置）

阿里云加速器：每个人有对应的加速地址，访问 https://cr.console.aliyun.com ->【镜像加速器】配置加速器

DaoCloud 加速器：http://guide.daocloud.io/dcs/daocloud-9153151.html

腾讯云加速器：https://www.qcloud.com/document/product/457/7207

### 鸣谢
[Docker LNMP 3.2](https://github.com/exc-soft/docker-lnmp)

### License
MIT