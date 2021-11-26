### 本文转自nolan大佬

# 简易教程

## 以 Debian/Ubuntu 操作环境作为演示

### 如果你是装过NVjdc 先看看后面1.2以前如何更新之1.2升级说明

1拉源码 国内
```
git clone https://ghproxy.com/https://github.com/NolanHzy/nvjdcdocker.git /root/nolanjdc
```

### 国外

```
git clone https://github.com/NolanHzy/nvjdcdocker.git /root/nolanjdc
```

### 2 拉取基础镜像以后不需要拉取镜像了 如果需要拉取我会通知
```
sudo docker pull nolanhzy/nvjdc:latest
```

### 3 执行命令

```
https://cdn.jsdelivr.net/gh/AaronYYDS/nvjdc@main/Config.json
```

### 下载Chromium

```
yum install wget unzip -y
```

### 4创建一个目录放配置

```
 cd /root/nolanjdc

mkdir -p  Config && cd Config

```

### 5下载config.json 配置文件 并且修改自己的配置 不能缺少

```
wget -O Config.json  https://raw.githubusercontent.com/NolanHzy/nvjdc/main/Config.json

```

### 国内请使用

```

wget -O Config.json   https://ghproxy.com/https://raw.githubusercontent.com/NolanHzy/nvjdc/main/Config.json

```

### 6 回到nolanjdc目录创建chromium文件夹并进入

```

cd /root/nolanjdc && mkdir -p  .local-chromium/Linux-884014 && cd .local-chromium/Linux-884014

```

### 7下载 chromium

```

wget https://mirrors.huaweicloud.com/chromium-browser-snapshots/Linux_x64/884014/chrome-linux.zip && unzip chrome-linux.zip

```

### 8删除刚刚下载的压缩包

```

rm  -f chrome-linux.zip

```

### 9回到刚刚创建的目录

```

cd  /root/nolanjdc

```

### 10启动镜像

```

sudo docker run   --name nolanjdc -p 5702:80 -d  -v  "$(pwd)":/app \
-v /etc/localtime:/etc/localtime:ro \
-it --privileged=true  nolanhzy/nvjdc:latest

```

### 11查看 日志

```

docker logs -f nolanjdc 

```

### 出现 NETJDC started 即可


