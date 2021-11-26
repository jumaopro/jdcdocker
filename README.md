简易教程
以 Debian/Ubuntu 操作环境作为演示
拉取镜像
docker pull aaronyyds/nvjdc:0.8
安装 wget &unzip
apt install wget unzip -y
创建 JDC 目录并进入
mkdir nolanjdc && cd nolanjdc
下载配置文件
https://cdn.jsdelivr.net/gh/AaronYYDS/nvjdc@main/Config.json
下载Chromium
mkdir -p  .local-chromium/Linux-884014 && cd .local-chromium/Linux-884014

wget https://mirrors.huaweicloud.com/chromium-browser-snapshots/Linux_x64/884014/chrome-linux.zip && unzip chrome-linux.zip

rm  -f chrome-linux.zip
回到JDC目录并启动项目
cd ~/nolanjdc

docker run   --name nolanjdc -p 5703:80 -d  -v  "$(pwd)"/Config.json:/app/Config/Config.json:ro \-v "$(pwd)"/.local-chromium:/app/.local-chromium  \-it --privileged=true  aaronyyds/nvjdc:0.8

日志的查看
docker logs -f nolanjdc 
