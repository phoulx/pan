FROM jlesage/baseimage-gui:ubuntu-22.04-v4

ENV APP_NAME        "115pc"
ENV APP_VERSION     "2.0.10.2"
# ENV USER_ID         0
# ENV GROUP_ID        0
ENV TZ              Asia/Shanghai
ENV ENABLE_CJK_FONT 1
ENV LANG            zh_CN.UTF-8
ENV LC_ALL          zh_CN.UTF-8

RUN sed -i 's@//.*archive.ubuntu.com@//mirrors.ustc.edu.cn@g' /etc/apt/sources.list

RUN apt update && apt install -y \
      curl libgl1 libglib2.0-0

RUN curl -L https://down.115.com/client/115pc/lin/115_v${APP_VERSION}.deb -o /tmp/115pc.deb
RUN dpkg -i /tmp/115pc.deb

COPY startapp.sh /startapp.sh
