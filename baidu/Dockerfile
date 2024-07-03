FROM jlesage/baseimage-gui:ubuntu-22.04-v4

ENV APP_NAME=baidupan
ENV APP_VERSION=4.17.7
ENV TZ=Asia/Shanghai
# 如果locale为其他，则无法启动，暂时设为C
ENV LC_ALL=C

RUN sed -i 's@//.*archive.ubuntu.com@//mirror.sjtu.edu.cn@g' /etc/apt/sources.list
RUN sed -i 's/security.ubuntu.com/mirror.sjtu.edu.cn/g' /etc/apt/sources.list

RUN apt update && apt install -y \
      curl libgbm1 libasound2 fonts-wqy-zenhei

# COPY baidunetdisk_4.17.7_amd64.deb /tmp/baidupan.deb

RUN curl -SL https://pkg-ant.baidu.com/issue/netdisk/LinuxGuanjia/${APP_VERSION}/baidunetdisk_${APP_VERSION}_amd64.deb -o /tmp/baidupan.deb
RUN apt install -y /tmp/baidupan.deb

COPY startapp.sh /startapp.sh
