---
title: Haskellプログラミング入門（4）reverse
author: hiroyuki_t
layout: post
date: 2006-03-21T11:31:50+00:00
url: /2006/03/21/203150/
categories:
  - Prog

---
<div class="section">
  <p>
    Haskellプログラミング入門（3）reverseを書いて見ようの続き
  </p>
  
  <p>
    reverseは標準で意味されてるけど。
  </p>
  
  <p>
  </p>
  
  <p>
    <a href="http://www.sampou.org/haskell/report-revised-j/basic.html" target="_blank">http://www.sampou.org/haskell/report-revised-j/basic.html</a>
  </p>
  
  <p>
    上記6.1.2 文字と文字列から
  </p>
  
  <blockquote>
    <p>
      文字列は文字のリストである。
    </p>
  </blockquote>
  
  <p>
  </p>
  
  <p>
    <a href="http://web.archive.org/web/20050216042941/www.teu.ac.jp/kougi/koshida/Prog6/text05.html" target="_blank">http://web.archive.org/web/20050216042941/www.teu.ac.jp/kougi/koshida/Prog6/text05.html</a>
  </p>
  
  <p>
    上記2.2.1　リストの構築子から
  </p>
  
  <blockquote>
    <p>
      全てのリストは，空リスト（[]）であるか，空でないかのいずれかである．空でないリスト（例：[4,2,3]）は，x:xsの書式で表すことができる．ここで，xは先頭要素，xsは，先頭要素を除いた，リストの残りを表す．
    </p>
  </blockquote>
  
  <p>
  </p>
  
  <pre>
myr :: String -&#62; String
myr &#91;] = &#91;]
myr (x:xs) = myr (xs) ++ &#91;x]
</pre>
  
  <p>
    ということでこれでいいのか？
  </p>
  
  <p>
    <a href="http://web.archive.org/web/20050216042941/www.teu.ac.jp/kougi/koshida/Prog6/text05.html" target="_blank">http://web.archive.org/web/20050216042941/www.teu.ac.jp/kougi/koshida/Prog6/text05.html</a>
  </p>
  
  <p>
    上記のリストに関する基本再帰を使うから空リストが必要。
  </p>
  
  <p>
    それから再帰すると出来る。
  </p>
  
  <p>
  </p>
  
  <p>
    <a href="http://www.sampou.org/haskell/report-revised-j/standard-prelude.html#preludelist" target="_blank">http://www.sampou.org/haskell/report-revised-j/standard-prelude.html#preludelist</a>
  </p>
  
  <p>
    上記によると以下のようになっている。
  </p>
  
  <p>
    まだまだHaskellの基本的なことがわかってない。
  </p>
  
  <p>
    再帰を自分でせずに標準関数を使えばいいのか。
  </p>
  
  <blockquote>
    <p>
      reverse :: [a] -> [a]
    </p>
    
    <p>
      reverse = foldl (flip (:)) []
    </p>
  </blockquote>
</div>