# docker-lamp

## 実行環境
- macOS High Sierra : バージョン 10.13.2
- Docker for Mac : version 17.09.1-ce
- Apache : 2.4.25 (Debian)
- PHP : 7.2.0 (cli)
- mysql : Ver 14.14 Distrib 5.7.20
- phpMyAdmin : 4.7.7

## ディレクトリ構成図
```
docker-lamp
├── README.md
├── db                  -> DBサーバ用ディレクトリ
│   ├── Dockerfile      
│   ├── my.cnf          -> MySQL設定ファイル
│   ├── mysql           -> MySQLのデータ格納用ディレクトリ
│   └── mysql.env       
├── docker-compose.yml  -> Docker Composeの設定ファイル
├── phpmyadmin          -> phpmyadminサーバ用ディレクトリ
│   ├── Dockerfile
│   ├── phpmyadmin.env
│   └── session
└── web                 -> WEBサーバ用ディレクトリ
    ├── Dockerfile
    ├── my-httpd.conf   -> httpdの設定ファイル
    ├── php.ini         -> PHPの設定ファイル
    └── src             -> 作業ディレクトリ
```

## コンテナ起動手順
1. ダウンロード
```
$ git clone https://github.com/nino0813g/docker-lamp.git
```
2. ディレクトリ移動
```
$ cd docker-lamp
```
3. コンテナビルド起動
```
$ docker-compose up -d --build
```
4. コンテナ起動確認
```
$ docker-compose ps
```
5. ブラウザアクセス
```
http://localhost/index.php
```

## 課題
- `docker-compose.yml`で`mysql.env`を外部読み込みできないエラーの解消
- 各`Dockerfile`の設定を公式イメージベースから軽量化カスタマイズ
