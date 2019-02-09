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

$ sestatus

Current mode: enforcing 

$ sudo setenforce 0

To execute withoud sudo (Ubuntu)

$ sudo usermod -aG docker $USER
$ sudo service docker restart

## Quick Check

$ docker version
$ docker deamon


