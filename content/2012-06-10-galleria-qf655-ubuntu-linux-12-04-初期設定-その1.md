---
title: Galleria QF655 Ubuntu Linux 12.04 初期設定 その1
author: hiroyuki_t
layout: post
date: 2012-06-10T00:35:24+00:00
url: /2012/06/10/093524/
categories:
  - Comp
  - Ubuntu

---
Prime Note Galleria QF655購入

## スペック

| 項目 | 内容 |
|---|---|
| CPU | Core i7-3610QM |
| MEMORY | 8GB(M471B5273DH0-CK0 Samsung 4GB PC3-12800✕2) |
| SSD | 128G(Intel SSD 330) |
| GPU | NVIDIA GeForce GT 650M 2GB |
| 光学ドライブ | DVDスーパーマルチドライブ |
| OS | Windows7 Home Premium 64bit |

HDDから SSDに変更している。

## パーテーション切り分け

| マウント先 | サイズ | ファイルシステム | OS |
|---|---|---|---|
| / | 12G | ext4 | Ubuntu Linux 12.04 |
| /home | 39G | ext4 | Ubuntu Linux 12.04 |
| | 67G | ntfs | Windows7 |

Ubuntu Linuxで使用するのがメインの用途となるが、

Windowsはゲーム （Skyrim等）で容量を取ることを想定し、多めに設定

データ移行等が行いやすいように、/homeは別パーテーションとする。

swapはメモリーが8GBあるので、設定しない。

## ソフトウエア設定

２００６年から設定を引き継いでおり、新しく設定し直したかったので、homeをコピーするのではなく、

必要なもののみ設定しなおしする方針とした。

### Opera

本家からインストール

flashもインストール

以下のファイルを以前のPCから移行

bookmarks.adr, operaprefs.ini, override.ini, search.ini, wand.dat

urlfilterの設定

上記のGeneralのみurlfilter.iniという名前で $HOME/.operaに保存

### zsh

補完が便利なシェル

```
apt-get install zsh
```

```
$ chsh
新しいシェル [/bin/bash]: /bin/zsh
```

補完が便利なので、ないと辛い

この[リンク][2]の.zshrcや.zsh_historyを過去のデータから移行

### mozc

Google日本語入力のオープンソース版

```
sudo apt-get install ibus-mozc mozc-server mozc-utils-gui
```

画面右上のキーボード→[再起動]

画面右上のキーボード→[設定] →[インプットメソッドタブ]mozcを設定

```
/usr/lib/mozc/mozc_tool --mode=config_dialog
```

でATOKキーバインドに変更

### 他のソフト

FTPソフト

```
sudo apt-get install filezilla
```

グラフィック編集・加工ソフト

```
sudo apt-get install gimp
```

ブラウザ

```
sudo apt-get install chromium-browser
```

 [2]: https://d.tflare.com/2007/02/10/210703/
