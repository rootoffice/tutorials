国内访问Docker Hub有时会遇到问题，所以我们可以配置镜像加速器
curl -sSL https://get.daocloud.io/daotools/set_mirror.sh | sh -s http://8ad7943c.m.daocloud.io
之后重启docker，就能下载部署镜像了
sudo systemctl restart docker.service
