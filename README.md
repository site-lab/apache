# WebServer
WebServer関連のシェルスクリプト置き場、CentOS7専用となります。**centos7 minimal インストール** した状態で何もはいっていない状態で必要なファイルを実行してください
Apache+PHPなどの環境構築シェルスクリプトです
※自己責任で実行してください

## 実行環境
* conohaのVPS
* メモリ：512MB
* CPU：1コア
* SSD：20GB

### 実行方法
SFTPなどでアップロードをして、rootユーザーもしくはsudo権限で実行
wgetを使用する場合は[環境構築スクリプトを公開してます](https://www.logw.jp/cloudserver/8886.html)を閲覧してください。
wgetがない場合は **yum -y install wget** でインストールしてください

**sh ファイル名.sh** ←同じ階層にある場合

**sh /home/ユーザー名/ファイル名.sh** ユーザー階層にある場合（rootユーザー実行時）

## [apache.sh](https://github.com/site-lab/apache/blob/master/apache.sh)
### 実行内容
* epelインストール
* gitのインストール
* システム更新
* apache2.4.6のインストール
* mod_sslのインストール
* HTTP2の有効化
* firewallのポート許可(80番、443番)
* gzip圧縮の設定

Apacheはドキュメントルートのみhtaccessの有効化された状態となります。
gzipは/etc/httpd/conf.d/gzip.conf　にて設定が記述されています
HTTP2については、モジュールの有効可をしてあるため、各々でconfファイルに追記をしてください
参考サイト：https://www.logw.jp/server/8359.html

Apacheのみのインストールとなります。PHPをfast_cgiで使いたいとか、HHVMを使いたいなどの場合はこれを選択してください

## [apache_php72.sh](https://github.com/site-lab/apache/blob/master/apache_php72.sh)
### 実行内容
* epelインストール
* gitのインストール
* システム更新
* apache2.4.6のインストール
* mod_sslのインストール
* php7.2のインストール
* php7.2の必要モジュールインストール
* firewallのポート許可(80番、443番)
* gzip圧縮の設定

Apacheはドキュメントルートのみhtaccessの有効化された状態となります。
gzipは/etc/httpd/conf.d/gzip.conf　にて設定が記述されています
PHP7は **モジュール版** となります。
データベースは自分でインストールしていただく形になります。データベースも含めてインストールしたい場合は[LAMP](https://github.com/site-lab/lamp)リポジトリからインストールしてください。

## [apache_php72_fcgid.sh](https://github.com/site-lab/apache/blob/master/apache_php72_fcgid.sh)
### 実行内容
* epelインストール
* gitのインストール
* システム更新
* apache2.4.6のインストール
* mod_sslのインストール
* php7.2のインストール
* php7.2の必要モジュールインストール
* firewallのポート許可(80番、443番)
* gzip圧縮の設定

Apacheはドキュメントルートのみhtaccessの有効化された状態となります。
gzipは/etc/httpd/conf.d/gzip.conf　にて設定が記述されています
PHP7は **FastCGI版** となります。
データベースは自分でインストールしていただく形になります。データベースも含めてインストールしたい場合は[LAMP](https://github.com/site-lab/lamp)リポジトリからインストールしてください。


## [nginx.sh](https://github.com/site-lab/apache/blob/master/nginx.sh)
### 実行内容
* epelインストール
* gitのインストール
* システム更新
* nginxのインストール
* mod_sslのインストール
* HTTP2の有効化
* HTTPSへのリダイレクト設定可（一部ファイル編集してください）
* firewallのポート許可(80番、443番)
* gzip圧縮の設定

## [nginx_php72.sh](https://github.com/site-lab/apache/blob/master/nginx_php72.sh)
### 実行内容
* epelインストール
* gitのインストール
* システム更新
* nginxのインストール
* mod_sslのインストール
* php7.2のインストール
* php7.2の必要モジュールインストール
* HTTP2の有効化
* HTTPSへのリダイレクト設定可（一部ファイル編集してください）
* firewallのポート許可(80番、443番)
* gzip圧縮の設定

PHP7は **FastCGI版** となります。
データベースは自分でインストールしていただく形になります。データベースも含めてインストールしたい場合は[LAMP](https://github.com/site-lab/lamp)リポジトリからインストールしてください。

## [nginx_nodejs.sh](https://github.com/site-lab/apache/blob/master/nginx_nodejs.sh)
### 実行内容
* epelインストール
* gitのインストール
* システム更新
* nginxのインストール
* mod_sslのインストール
* node.jsのインストール
* Expressのインストール
* HTTP2の有効化
* HTTPSへのリダイレクト設定可（一部ファイル編集してください）
* firewallのポート許可(80番、443番)
* gzip圧縮の設定

nginx+node.jsです。nginxでリバースプロキシをしてます。
