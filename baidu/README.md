# 百度网盘Linux版本的Docker封装


## build
```sh
docker build -t baidupan .
```

## create
需设置对应目录
```sh
docker create --name=baidupan \
    -e USER_ID=$(id -u) -e GROUP_ID=$(id -g) \
    -p 5800:5800 -p 5900:5900 \
    -v $HOME/Documents/baidupan:/root/pan \
    baidupan
```

## start/stop
```sh
docker start baidupan
docker stop baidupan
```

启动之后，可通过`http://<ip>:5800`访问  
部分设置参考115
