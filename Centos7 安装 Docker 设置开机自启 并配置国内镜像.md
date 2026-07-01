以下命令均以root权限执行
卸载docker旧版本

```bash
yum remove docker docker-client docker-client-latest docker-common docker-latest docker-latest-logrotate docker-logrotate docker-selinux docker-engine-selinux docker-engine

```
安装相关工具类
```bash
yum install -y yum-utils device-mapper-persistent-data lvm2
```


配置docker仓库

```bash
yum-config-manager --add-repo https://download.docker.com/linux/centos/docker-ce.repo
```

aliyun的源

```bash
yum-config-manager --add-repo http://mirrors.aliyun.com/docker-ce/linux/centos/docker-ce.repo

```

安装Docker
```bash
yum install docker-ce

```

执行安装docker

```bash
yum install docker-ce
 
Installed:
  docker-ce.x86_64 0:18.03.0.ce-1.el7.centos
 
Dependency Installed:
  audit-libs-python.x86_64 0:2.7.6-3.el7 checkpolicy.x86_64 0:2.5-4.el7   container-selinux.noarch 2:2.42-1.gitad8f0f7.el7 libcgroup.x86_64 0
  libtool-ltdl.x86_64 0:2.4.2-22.el7_3   pigz.x86_64 0:2.3.3-1.el7.centos policycoreutils-python.x86_64 0:2.5-17.1.el7     python-IPy.noarch
 
Complete!
```

验证docker安装成功

启动docker

```bash
systemctl start docker
```

验证docker

```bash
docker run hello-world

```


配置国内镜像与存储目录

```bash
vim /etc/docker/daemon.json

{
  "registry-mirrors": [
    "https://docker.m.daocloud.io",
    "https://docker.1panel.dev"
  ],
  "data-root": "/home/docker"
}



systemctl daemon-reload
systemctl restart docker
```
