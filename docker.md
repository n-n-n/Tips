# Docker Tips
From Using Docker, Adrian Mouat
# Commands
## info (docker * )
{command} --help
or 
- help
- info
- version
- diff
- events
- inspect
- logs
- port
- ps
- top
## run (docker run)
- -a, --attach :  ストリーム(stdout, stderr ..) をアタッチする
- -d, --detach : コンテナをバックグラウンドで起動。コンテナIDが戻り値
- -i, --interactive : stdin付きで起動
- --restart : 終了したコンテナをDockerが再起動する方法を設定
- --rm : 終了時にコンテナを自動削除
- -t, --tty : TTYの割り当て
- -e, --env : コンテナ内の環境設定。　-e var1=foo1。--env-fileでファイル指定
- -h, --hostname : コンテナのUnix　hostnameの設定
- --name : コンテナ名の設定　--name FOO.
- -v, --volume  : ヴォリュームの設定
- --volumes-form :指定されたコンテナからボリュームをマウント。データコンテナと併用される
- --expose
- --link
- -p, --publish : ポートの公開　 (ref docker port)
- -p, --publish-all
- --entrypoint
- -u, --user :コマンドのユーザーの設定
- -w, --workdir : コンテナの作業ディレクトリーの設定

## control (docker * )
- attach
- create
- cp
- exec
- kill
- pause
- restart
- rm
- start
- stop
- unpause

## image (docker * )
- build
- commit
- export
- history
- images
- import
- load
- rmi
- save
- tag
## registory (docker * )
- login
- logout
- pull
- push
- search
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


