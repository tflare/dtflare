---
title: WordPressからHugoに移行
author: hiroyuki_t
layout: post
date: 2016-09-20T00:01:00+00:00
url: /2016/09/20/090100/
categories:
  - Comp

---
# WordPressからHugoに移行

WordPress to Hugo Exporterを使用して移行しました。
<https://github.com/SchumacherFM/wordpress-to-hugo-exporter>

***

## GitHub Pagesへの移行試行（取りやめ）
これに伴って、GitHub Pagesに移行しようとしましたが、取りやめました。

### 前提
* ドメインはスタードメインを使用
* メールはさくらのメールボックスを使用

### 取りやめた理由
* GitHub Pagesではサブドメインの際はDNSの設定において、CNAMEの設定をする必要があるようです。（サブドメインでない場合にどうなるかは未確認）
* 上記ドメインでメールも使用しようとしていたためMXレコードの設定もしようとしていたが、CNAMEとMXレコードの混在は不可能
<http://www.ocn.ne.jp/business/customer/set_up/dns_12.html>

（ドメイン会社のDNSレコード編集機能でNSレコードが変更できれば可能性があるが、スタードメインではNSレコードは編集不可能）

***

## 環境の変更
### Web　さくらの共有サーバ（スタンダード）→スターサーバ

WordPressを使用しなくなり、静的なサイトになったため
さくらの共有サーバ（スタンダード）は不要だろうということでやめ、
スタードメインに付属しているサーバを使用

### メール　さくらの共有サーバ（スタンダード）→さくらのメールボックス

メールはスタードメインのメール転送機能を使用しようと思ったが、
安定性が低いというページが有ったためさくらのメールボックスを使用することにした。

エックスドメインであればドメインを契約すれば通常のメール機能が使えるようなので以降も要検討
（スタードメインはメール転送機能のみ）

***

### 現在のスタードメインのDNS設定
tflare.com　A　スターサーバのIPアドレス

d.tflare.com　A　スターサーバのIPアドレス

tflare.com　MX　さくらのメールボックスのサーバホスト名

tflare.com　TXT　v=spf1 a:さくらのメールボックスのサーバホスト名 -all



