镜像的构建和分享
====================

-t 就是tag 指定一个名字, 默认是最新的latest
REPOSITORY   TAG       IMAGE ID       CREATED          SIZE
hello        latest    84b82db6d8cd   55 seconds ago   202MB
docker image build -t hello .

指定版本号
docker image build -t hello:1.0.0 .

运行
docker run -it hello

如果两个imageid 相同如何删除
dockerDemo % docker image ls
REPOSITORY        TAG       IMAGE ID       CREATED          SIZE
jason9532/hello   latest    84b82db6d8cd   10 minutes ago   202MB
hello             latest    84b82db6d8cd   10 minutes ago   202MB
nginx             latest    5628e5ea3c17   5 days ago       192MB


使用名字:tag 来删除
docker image rm jason9532/hello:latest

Untagged: jason9532/hello:latest

修改已有的名字和tag
docker image tag 旧的名字 新的名字:tag

wangtengfei@192 dockerDemo % docker image ls
REPOSITORY        TAG       IMAGE ID       CREATED          SIZE
jason9532/hello   latest    84b82db6d8cd   10 minutes ago   202MB
hello             latest    84b82db6d8cd   10 minutes ago   202MB
nginx             latest    5628e5ea3c17   5 days ago       192MB
wangtengfei@192 dockerDemo % docker image rm jason9532/hello:latest
Untagged: jason9532/hello:latest
wangtengfei@192 dockerDemo % docker image tag hello jason9532/hello:1.0.0


wangtengfei@192 dockerDemo % docker image ls
REPOSITORY        TAG       IMAGE ID       CREATED          SIZE
hello             latest    84b82db6d8cd   16 minutes ago   202MB
jason9532/hello   1.0.0     84b82db6d8cd   16 minutes ago   202MB
nginx             latest    5628e5ea3c17   5 days ago       192MB

docker push

1. 登录
docker login

docker image push jason9532/hello:1.0.0

拉取自己的Docker
wangtengfei@192 dockerDemo % docker image pull jason9532/hello:1.0.0
1.0.0: Pulling from jason9532/hello
bfbe77e41a78: Already exists 
ab364b8adecb: Already exists 
ed5b8425e42d: Already exists 
Digest: sha256:185683d9c0ec8ed20cafe0bf2db1556e0662fb99ab552f1fe7e9ec957f2326f3
Status: Downloaded newer image for jason9532/hello:1.0.0
docker.io/jason9532/hello:1.0.0
wangtengfei@192 dockerDemo % docker image ls
REPOSITORY        TAG       IMAGE ID       CREATED          SIZE
jason9532/hello   1.0.0     84b82db6d8cd   34 minutes ago   202MB
nginx             latest    5628e5ea3c17   5 days ago       192MB