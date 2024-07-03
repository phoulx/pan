# 115网盘Linux版本的Docker封装


## build
```sh
docker build -t 115pc .
```
## create
假定挂载目录为`$HOME/Documents/115`
```sh
docker create --name=115 \
    -e USER_ID=$(id -u) -e GROUP_ID=$(id -g) \
    -p 11580:5800 -p 5900:5900 \
    -v $HOME/Documents/115:/root/Downloads/115download \
    115pc
```

## start/stop

```sh
docker start 115
docker stop 115
```

启动之后，可通过`http://<ip>:11580`访问


## 说明
1. 如果不指定`USER_ID`和`GROUP_ID`，镜像默认用户无权限写入，会报错：「下载失败，含违规内容」
2. `USER_ID`和`GROUP_ID`也可以为`0`，则以root用户运行，副作用是下载的文件所有者也为root
