---
title: AVDからEmulatorが起動しない(Ubuntu11.04)
author: hiroyuki_t
layout: post
date: 2011-10-22T08:35:15+00:00
url: /2011/10/22/173515/
categories:
  - Android
  - Ubuntu

---
<div class="section">
  <p>
    Ubuntu11.04にてAVD(Android Virtual Device Manager)からEmulatorを起動しようとしても起動しない
  </p>
  
  <p>
    コマンドラインから実行するとSegmentation faultしており、
  </p>
  
  <p>
    gdbを使うとvfprintfで落ちていることがわかった。
  </p>
  
  <p>
    これをもとに検索すると以下が引っかかった。
  </p>
  
  <p>
  </p>
  
  <p>
    以下を見るとキャプチャーカードが問題の一つとしてあるようだ。(他にWebカメラでの事象もあり)
  </p>
  
  <p>
    Emulator segfault on startup
  </p>
  
  <p>
    <a href="http://code.google.com/p/android/issues/detail?id=20952#c9" target="_blank">http://code.google.com/p/android/issues/detail?id=20952#c9</a>
  </p>
  
  <blockquote>
    <p>
      the emulator was trying to access a video device (/dev/video0 &#8211; a tv tuner card). At the same point as the OP (emulator: Adding boot property: &#8216;qemu.sf.fake_camera&#8217; = &#8216;back&#8217;).
    </p>
  </blockquote>
  
  <p>
  </p>
  
  <p>
    Webカメラであればカメラの設定を変えることで対処できそうだが、
  </p>
  
  <p>
    こちらで問題になっているのはキャプチャーカード(GV-MVP/RX)と思われる。
  </p>
  
  <p>
    そのため以下で解決した。
  </p>
  
  <p>
    Emulator segfault on startup
  </p>
  
  <p>
    <a href="http://code.google.com/p/android/issues/detail?id=20952#c19" target="_blank">http://code.google.com/p/android/issues/detail?id=20952#c19</a>
  </p>
  
  <blockquote>
    <p>
      rename /dev/video0 to /dev/_video0
    </p>
  </blockquote>
</div>