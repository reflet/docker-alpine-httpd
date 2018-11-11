#  Apache for Alpine Linux

オフィシャルのhttpd:2.4-alpineを元に日本環境の調整を行いました。

### 調整内容 ###

* httpd:2.4-alpine
* 必要なツールのインストール (less vim git)
* virtualhostフォルダ設置

---

### 使い方 ###

下記のコマンドにてコンテナを起動します (port 80 is available):

```
$ docker pull reflet/alpine-httpd
$ docker run --name httpd -d -p 80:80 reflet/alpine-httpd
$ docker ps -a
$ curl http://localhost/
```

---

### メンテナンス ###

下記のコマンドにてソースのダウンロードとイメージの構築を実行します。

```
$ git clone git@bitbucket.org:reflet/docker-alpine-httpd.git .
$ docker build -t reflet/alpine-httpd .
$ docker login
$ docker push reflet/alpine-php
```

---

### コンテナ操作 ( EXEC ） ###

コンテナ内に入って操作したい場合は、下記コマンドにて接続ください。
※操作を終了する場合は、「exit」でコンソールを抜けられます。

```
$ docker exec -u "www-data" -it httpd bash
```