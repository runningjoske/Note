# docker 安装部署

## docker 最核心的组件

- image镜像，构建容器（应用程序运行所需要的环境，打包为镜像文件）
- Container，容器（应用程序，跑在容器中）
- 镜像仓库（dockerhub）（保存镜像文件，提供上传、下载镜像）作用好比github



## 安装步骤

基础环境配置

更新linux内核版本（危险操作）

```
yum update
```

安装docker

开启linux内核的流量转发

```
cat <<EOF > /etc/sysctl.d/docker.conf
net.bridge.bridge-nf-call-ip6tables = 1
net.bridge.bridge-nf-call-iptables = 1
net.ipv4.conf.default.rp_filter = 0
net.ipv4.conf.all.rp_filter = 0
net.ipv4.ip_forward=1
EOF

# 加载修改内核的参数，配置文件
modprobe br_netfilter
sysctl -p /etc/sysctl.d/docker.conf

[root@localhost xuzhengyuan]# sysctl -p /etc/sysctl.d/docker.conf
net.bridge.bridge-nf-call-ip6tables = 1
net.bridge.bridge-nf-call-iptables = 1
net.ipv4.conf.default.rp_filter = 0
net.ipv4.conf.all.rp_filter = 0
net.ipv4.ip_forward = 1
```

利用yum 安装

```
# 提前配置好yum仓库
# 1、阿里云自带仓库；2、阿里云提供的docker专属repo仓反馈
```

yum-config-manager --add-repo https://download.docker.com/linux/centos/docker-ce.repo

yum install -y docker-engine

systemctl start docker

docker version

