
### 亚马逊EC2(Ubuntu)

这是一个示例会话.这肯定可以改进和自动化.

#### 依赖关系(以root身份)

``` bash
apt-get update
apt-get upgrade -y
apt-get install git awscli nginx

# 安装Docker CE
# 根据说明配置apt-get
# https://docs.docker.com/engine/installation/linux/docker-ce/ubuntu/
apt-get install docker-ce

# 使用不会泄漏磁盘空间的生产质量存储驱动程序
cat >>/etc/docker/daemon.json <<EOF
{
    "storage-driver": "overlay2"
}
EOF

# 确保Docker可以控制PID限制
mount | grep cgroup/pids

# 确保Docker可以控制交换限制
# https://docs.docker.com/engine/installation/linux/linux-postinstall/#your-kernel-does-not-support-cgroup-swap-limit-capabilities

service docker restart
usermod -a -G docker ubuntu # 用户需要再次注销

fallocate -l 1G /swap.fs
chmod 0600 /swap.fs
mkswap /swap.fs
```

#### 留出磁盘空间(以root身份)

```
fallocate -l 512M /playground.fs
device=$(losetup -f --show /playground.fs)
mkfs -t ext3 -m 1 -v $device
mkdir /mnt/playground
```

#### 配置磁盘挂载点(以root身份)

```
cat >>/etc/fstab <<EOF
/swap.fs        none            swap   sw       0   0
/playground.fs /mnt/playground  ext3   loop     0   0
EOF
```

此时重新启动实例.

#### 获取代码

```
git clone https://github.com/integer32llc/rust-playground.git
cd rust-playground
```

#### 设置crontab以更新资源,二进制和docker容器

```
crontab -e
```

回顾一下在这个回购的[示例crontab](crontab).[`update.sh`](update.sh)也在这个回购.

#### 安装SystemD服务

[playground.service](playground.service)

```
cp playground.service /etc/systemd/system/playground.service
service playground start
systemctl enable playground.service
```

#### 安装Nginx反向代理

[游乐场-反向代理](playground-reverse-proxy)

```
cp playground-reverse-proxy /etc/nginx/sites-enabled
service nginx reload
```

#### 配置SSL
