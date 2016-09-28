#用到的SSH命令
进入服务器
```
ssh sxwl1080@192.168.0.206
```
运行docker容器
```
sudo docker start hzy_caffe_gpu
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

当前目录下的所有文件(生成树)
```
find . -print | sort | sed 's;[^/]*/;|---;g;s;---|; |;g'
```
复制文件和目录
```
http://www.cnblogs.com/hitwtx/archive/2011/11/16/2251254.html
```
* 复制文件： 
        命令格式： 
                scp local_file remote_username@remote_ip:remote_folder 
                或者 
                scp local_file remote_username@remote_ip:remote_file 
                或者 
                scp local_file remote_ip:remote_folder 
                或者 
                scp local_file remote_ip:remote_file 

                第1,2个指定了用户名，命令执行后需要再输入密码，第1个仅指定了远程的目录，文件名字不变，第2个指定了文件名； 
                第3,4个没有指定用户名，命令执行后需要输入用户名和密码，第3个仅指定了远程的目录，文件名字不变，第4个指定了文件名； 
        例子： 
                scp /home/space/music/1.mp3 root@www.cumt.edu.cn:/home/root/others/music 
                scp /home/space/music/1.mp3 root@www.cumt.edu.cn:/home/root/others/music/001.mp3 
                scp /home/space/music/1.mp3 www.cumt.edu.cn:/home/root/others/music 
                scp /home/space/music/1.mp3 www.cumt.edu.cn:/home/root/others/music/001.mp3 

* 复制目录： 
        命令格式： 
                scp -r local_folder remote_username@remote_ip:remote_folder 
                或者 
                scp -r local_folder remote_ip:remote_folder 

                第1个指定了用户名，命令执行后需要再输入密码； 
                第2个没有指定用户名，命令执行后需要输入用户名和密码； 
        例子： 
                scp -r /home/space/music/ root@www.cumt.edu.cn:/home/root/others/ 
                scp -r /home/space/music/ www.cumt.edu.cn:/home/root/others/ 

                上面命令将本地music目录复制到远程others目录下，即复制后有远程有../others/music/目录 
