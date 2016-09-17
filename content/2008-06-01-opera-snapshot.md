---
title: Opera snapshot
author: hiroyuki_t
layout: post
date: 2008-06-01T01:18:57+00:00
url: /2008/06/01/101857/
categories:
  - Opera
  - Ubuntu

---
<div class="section">
  <p>
    opera_static-9.50-1983.gcc4-qt4_i386.deb
  </p>
  
  <p>
    を入れたときはまともに動いていたのが
  </p>
  
  <p>
  </p>
  
  <p>
    opera-static_9.50-1992.gcc4-static-qt3_i386.deb
  </p>
  
  <p>
    を入れたあとにブックマークが化けて表示されるようになった。（メニューを日本語にするとメニューも化ける）
  </p>
  
  <p>
    フォントの設定を変えても駄目
  </p>
  
  <p>
  </p>
  
  <p>
    opera-static_9.50-1997.gcc4-static-qt3_i386.deb
  </p>
  
  <p>
    その後上記Build1997を入れても改善しない。
  </p>
  
  <p>
  </p>
  
  <p>
    opera_9.50-1997.gcc4-qt4_i386.deb
  </p>
  
  <p>
    そこでqtの問題かと思いqt4のバージョンを入れ直したら直った。
  </p>
  
  <p>
  </p>
  
  <p>
    結局opera-staticでBuild1992からqt4がなくなったので
  </p>
  
  <p>
    static-qt3バージョンを入れたのが原因だった。
  </p>
  
  <p>
    staticじゃないoperaのqt4版で上記問題が解決し
  </p>
  
  <p>
    他の問題も発生していないのでこれで作業する予定。
  </p>
</div>