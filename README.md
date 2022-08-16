# DockerBuild-RaspberryPi-Nginx
RaspberryPi(64bit)にDockerでNginxを構築

## 環境
- kernel：Linux ホスト名 5.15.32-v8+ #1538 SMP PREEMPT Thu Mar 31 19:40:39 BST 2022 aarch64 GNU/Linux
- OS：Debian GNU/Linux 11 (bullseye)
- SSL証明書：Let's Encrypt
- DNS：[DockerBuild-RaspberryPi64-Dnsmasq](https://github.com/takanori-azegami-jp/DockerBuild-RaspberryPi64-Dnsmasq)

## 修正ファイル
./conf/nginx.conf<br>
[FQDN名]を変更する(例: test.example.com)

## Dockerコマンド
```bash
# Docker-composeビルド
$ docker-compose up -d

# Docker コンテナ確認
$ docker ps

# Docker イメージ確認
$ docker images

# Docker コンテナの中に入る
$ docker exec -it [コンテナID] bash

# 起動しているコンテナをdokcerイメージから再ビルド
$ docker-compose up -d --build --force-recreate

# dokcer-composeでの一括削除（滅びの呪文）
$ docker-compose down --rmi all --volumes --remove-orphans
```

## 参考リンク
- [Docker による nginx の導入と基本設定](https://blog1.mammb.com/entry/2020/09/01/000000)
- [nginxの初期の設定ファイルを読み解いてみよう](https://www.y-techmemo.work/entry/2018/05/16/182700)
