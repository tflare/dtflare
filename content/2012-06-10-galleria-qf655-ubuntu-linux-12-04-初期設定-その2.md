---
title: Galleria QF655 Ubuntu Linux 12.04 初期設定 その2
author: hiroyuki_t
layout: post
date: 2012-06-10T01:09:00+00:00
url: /2012/06/10/100900/
categories:
  - Comp
  - Ubuntu

---
Galleria QF655 Ubuntu Linux 12.04 初期設定 その2

## 設定

### アドレスバーの表示

gsettings set org.gnome.nautilus.preferences always-use-location-entry true

### グローバルメニューの無効化

sudo apt-get autoremove appmenu-gtk appmenu-gtk3 appmenu-qt

### 隠しファイルの表示

フォルダーを開き、メニューから

[編集]→[設定]

隠しファイルと バックアップ・ファイルを表示する

&nbsp;

&nbsp;

## 開発用ソフトウエア

### git

sudo apt-get install git-core

### RabbitVCS

バージョン管理GUIツール

gitで使用

sudo add-apt-repository ppa:rabbitvcs/ppa

sudo apt-get install rabbitvcs-nautilus3

### SSH

すべて以前の設定を持ってくる。

bitbucket用の設定も持ってくる。

### Java7

sudo add-apt-repository ppa:webupd8team/java

sudo apt-get update

apt-get install oracle-java7-installer

### Eclipse

sudo apt-get install eclipse

起動しようとすると以下のエラーになるので

no swt-gtk-3740 in java.library.path

no swt-gtk in java.library.path

32bit版であれば以下を実行することで解消される。

sudo cp /usr/lib/jni/libswt-*3740.so ~/.swt/lib/linux/x86/

64bit版はリンク参照

参考:[http://askubuntu.com/questions/125150/unsatisfied-link-error-and-missing-so-files-when-starting-eclipse ][2]

### Android

[Ubuntu 10.04にAndroid SDKをインストールする][3]

を参照

 [2]: http://askubuntu.com/questions/125150/unsatisfied-link-error-and-missing-so-files-when-starting-eclipse
 [3]: http://techbooster.jpn.org/andriod/environment/492/
