# Docker Tips
From Using Docker, Adrian Mouat

# 1.
Linux Containers(LXC) 2008-
- CGroups
- Kernel namespace
- chroot
- ...

Open Container Initiative 2015-


## 64bit Linux
コンテナはホストのカーネルと同じでないとならない。

### コラム
モノリシック vs マイクロサービス

# 2
https://get.docker.com

SELinuxのモードが利用できところでは、permissive モードで動作を推奨。enforceモードは非推奨。
```
$ sestatus
```
Current mode: enforcing 
```
$ sudo setenforce 0
```
To execute withoud sudo (Ubuntu)
```
$ sudo usermod -aG docker $USER
$ sudo service docker restart
```
## Quick Check
```
$ docker version
```
start deamon by hand
```
$ docker deamon
```
# 3.

test command
```
$ docker run debian echo "Hello World"
```
enter a shell
```
$ docker run -i -t debian /bin/bash
```
-i, -t interactive teletype??

Run and Give a host name (container name)
```
$ docker run -h CONTAINER -it debian /bin/bash
```
ps, inspect ,diff and logs on the host computer.
```
$ docker ps
$ docker inspect {container name}
$ docker inspect --format {{Go-lang template}} {container name}

$ docker diff {container name}
$ docker logs {container name}
```
remove the container
```
$ docker rm {container name}
```

```
$ docker run -it --name cowsay --hostname cowsay debian bash
root@cowsay:/# ....
root@cowsay:/# exit
exit
$ docker commit cowsay test/cowsayimage
$docker run test/cowsayimage {some command}

## Dockerfile
union file system (UFS)


```


