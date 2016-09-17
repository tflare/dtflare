---
title: Action Controllerのマッピング
author: hiroyuki_t
layout: post
date: 2006-06-01T14:30:25+00:00
url: /2006/06/01/233025/
categories:
  - Prog

---
<div class="section">
  <p>
    mod_rewriteの代わりに使えるわけねー
  </p>
  
  <p>
    というかmod_rewriteがないと下記のようなアドレスでcgiが見つからなくてNot Foundで終わりじゃん
  </p>
  
  <p>
    <a href="http://www.hoge.net/diary/2006/06/02/" target="_blank">http://www.hoge.net/diary/2006/06/02/</a>
  </p>
  
  <p>
    なにを考えてるんだろう。
  </p>
  
  <p>
  </p>
  
  <p>
    Action Controllerのマッピングをちょっと調べてみたら
  </p>
  
  <p>
    基本的にREQUEST_URIを元にマッピングしてる
  </p>
  
  <p>
    いろいろと省略可能だったり
  </p>
  
  <p>
    オプションがいろいろついていたりしているので複雑になっている。
  </p>
</div>