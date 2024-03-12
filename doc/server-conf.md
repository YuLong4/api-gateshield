1.安装docker
https://docs.docker.com/engine/install/ubuntu/按照文档的步骤一步步安装即可

2.安装portainer
```
sudo docker pull portainer/portainer

sudo docker run -d --restart=always --name portainer -p 9000:9000 -v /var/run/docker.sock:/var/run/docker.sock portainer/portainer
```
然后(新的ubuntu serverip)20.115.56.36:9000登陆进portainer

3.安装zookeeper
```
sudo docker pull zookeeper:3.4.13

sudo docker run --name my-zookeeper -p 2181:2181 -d zookeeper:3.4.13
添加自定义的配置文件zoo.cfg
sudo docker run -d -p 2181:2181 --name my-zookeeper -v /Users/yulong/Desktop/BS/yyl/api-gateshield-core/docker/zookeeper/zoo.cfg:/conf/zoo.cfg zookeeper:3.4.13
```

4.安装redis和Mysql
```
sudo docker pull daocloud.io/library/redis
sudo docker run -d -p 6379:6379 --name myredis daocloud.io/library/redis

sudo docker pull daocloud.io/library/mysql
sudo docker run -p 3306:3306 --name mysql -e MYSQL_ROOT_PASSWORD="5436yinyuLONG" -d daocloud.io/library/mysql
```

5.安装node
```
sudo apt install nodejs npm
```

6.上传代码到服务器 / 拉取github代码
