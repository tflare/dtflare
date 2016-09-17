---
title: Firestarter設定他
author: hiroyuki_t
layout: post
date: 2007-03-06T11:29:41+00:00
url: /2007/03/06/202941/
categories:
  - Ubuntu

---
<div class="section">
  <p>
    FirestarterのGUIのフロントエンドの自動起動の方法がわからなかったので
  </p>
  
  <p>
    下記を参考に設定した。
  </p>
  
  <p>
    <a href="http://blogs.dion.ne.jp/fedora_blog/archives/2931040.html" target="_blank">http://blogs.dion.ne.jp/fedora_blog/archives/2931040.html</a>
  </p>
  
  <p>
    <a href="http://ubuntuforums.org/showthread.php?t=187899" target="_blank">http://ubuntuforums.org/showthread.php?t=187899</a>
  </p>
  
  <p>
  </p>
  
  <p>
    下記のところを
  </p>
  
  <p>
    /usr/bin/から/usr/sbin/に変えた。
  </p>
  
  <p>
    user ALL= NOPASSWD: /usr/sbin/firestarter
  </p>
  
  <p>
  </p>
  
  <p>
    UbuntuのGnomeのアプリの自動起動の方法は
  </p>
  
  <p>
    [システム]→[設定]→[セッション]から自動起動するプログラムに追加
  </p>
  
  <p>
  </p>
  
  <p>
    Firestarterとは関係ないが、自動起動するプログラムの以下については使わないので停止させた。
  </p>
  
  <p>
    /usr/lib/evolution/2.8/evolution-alarm-notify
  </p>
  
  <p>
  </p>
  
  <p>
    あとchkrootkitとrkhunterもインストールした。
  </p>
  
  <p>
  </p>
  
  <p>
    Firestarterのログを見ていると
  </p>
  
  <p>
    ポート135とポート445のアクセスが多い
  </p>
  
  <p>
    このアクセス状態を見ると前からわかっていたことだが
  </p>
  
  <p>
    Windowsを狙ったウイルスの蔓延していることが実感できる。
  </p>
  
  <p>
    後は韓国からICMPプロトコルのアクセスがときどき見受けられた。
  </p>
</div>