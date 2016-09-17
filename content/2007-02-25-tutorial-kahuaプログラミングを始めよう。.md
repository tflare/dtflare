---
title: Tutorial Kahuaプログラミングを始めよう。
author: hiroyuki_t
layout: post
date: 2007-02-25T05:04:53+00:00
url: /2007/02/25/140453/
categories:
  - Scheme

---
<div class="section">
  <p>
    <a href="http://www.kahua.org/cgi-bin/kahua.fcgi/kahua-web/show/doc/Tutorial" target="_blank">http://www.kahua.org/cgi-bin/kahua.fcgi/kahua-web/show/doc/Tutorial</a>
  </p>
  
  <p>
    を参考にしてKahuaのセッティングを行う。
  </p>
  
  <p>
    Gauche 0.8.9と Kahua 1.0.2をインストールして
  </p>
  
  <p>
    Step 1. まずは動かそうの
  </p>
  
  <blockquote>
    <p>
      保存したら、kahua-adminコマンドを起動してapp-serversファイルを reloadコマンドで再読み込みします。
    </p>
  </blockquote>
  
  <p>
    までいったのだけどそこでkahua-adminすると、下記のエラーが出た。
  </p>
  
  <p>
    ERROR: working directory does not exist or is not writable: &#8220;/usr/local/kahua/var/kahua&#8221;
  </p>
  
  <p>
    見てみるとディレクトリはあるが権限がない状態になっている。
  </p>
  
  <p>
  </p>
  
  <p>
    強引に権限を付けてやってみるとkahua-adminはうまくいくけど
  </p>
  
  <p>
    lsすると下記のエラー
  </p>
  
  <p>
    ERROR: connect failed to #<sockaddr unix &#8220;/usr/local/kahua/tmp/kahua/kahua&#8221;>: No such file or directory
  </p>
  
  <p>
  </p>
  
  <p>
    EmacsでM-x run-kahuaしても
  </p>
  
  <p>
    Symbol&#8217;s function definition is void read-directory-name
  </p>
  
  <p>
  </p>
  
  <p>
    とでてうまくいかないので後でやりなおし。
  </p>
</div>