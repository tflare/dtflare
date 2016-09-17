---
title: Tutorial Kahuaプログラミングを始めよう。その2
author: hiroyuki_t
layout: post
date: 2007-02-25T05:04:53+00:00
url: /2007/02/25/140453/
categories:
  - Scheme

---
<div class="section">
  <p>
    kahua-adminでlsするとエラーになっていたのは
  </p>
  
  <p>
    Kahuaアプリケーションが立ち上がっていなかったためで
  </p>
  
  <p>
    Kahuaアプリケーションがたちあがっている状態だと正常に動いた。
  </p>
  
  <p>
  </p>
  
  <p>
    ソーシャルブックマークを作る(2)までいったが
  </p>
  
  <p>
    ちょっとリファクタリングの一番最後のコードを使うと
  </p>
  
  <p>
    Kahua error &#8211; stale session keyというエラーページが表示されるので
  </p>
  
  <p>
    newのとこだけ以下のように変更すると作成ページが表示されるようになった。
  </p>
  
  <pre class="syntax-highlight">
<span class="synSpecial">(</span>define-entry <span class="synSpecial">(</span>newbm<span class="synSpecial">)</span>
<span class="synSpecial">(</span>standard-page <span class="synConstant">&#34;New Bookmark&#34;</span>
<span class="synSpecial">(</span>node-set/
<span class="synSpecial">(</span>all-bookmarks-link/<span class="synSpecial">)</span>
<span class="synSpecial">(</span>bookmark-form/ <span class="synConstant">&#34;&#34;</span> <span class="synConstant">&#34;&#34;</span><span class="synSpecial">))))</span>
<span class="synSpecial">(</span><span class="synStatement">define</span> new-bookmark-link/ <span class="synSpecial">(</span>cut make-link/ newbm <span class="synConstant">&#34;[New Bookmark]&#34;</span><span class="synSpecial">))</span>
</pre>
</div>