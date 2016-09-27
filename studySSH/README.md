#用到的SSH命令
进入服务器
```
ssh sxwl1080@192.168.0.206
```
查看正在运行的docker容器
```
sudo docker ps
```
进入docker容器
```
sudo docker exec -it [dockername] zsh
```
docker中的dl-data和服务器路径中的/hzy/dl-data/是同一目录
