---
title: ol要素の直下にli要素以外のものを入れてOperaで表示すると
author: hiroyuki_t
layout: post
date: 2010-03-27T08:26:49+00:00
url: /2010/03/27/172649/
categories:
  - Opera

---
<div class="section">
  <p>
    ol要素（順序付きリスト）の直下にli要素以外のものを入れてOperaで表示するとカウントアップしなくなる。
  </p>
  
  <p>
    これを使っているサイトがたまにあるので意外と困る。
  </p>
  
  <p>
    Operaは仕様どおり作っているのだが
  </p>
  
  <p>
    Internet ExplorerやFirefoxはカウントアップするので見過ごされているのだろう。
  </p>
  
  <h4>
    例
  </h4>
  
  <h5>
    html
  </h5>
  
  <pre class="syntax-highlight">
<span class="synIdentifier">&#60;</span><span class="synStatement">ol</span><span class="synIdentifier">&#62;</span>
<span class="synIdentifier">&#60;</span><span class="synStatement">div</span><span class="synIdentifier"> </span><span class="synType">class</span><span class="synIdentifier">=</span><span class="synConstant">&#34;comment&#34;</span><span class="synIdentifier">&#62;</span>
<span class="synIdentifier">&#60;</span><span class="synStatement">li</span><span class="synIdentifier">&#62;</span>
<span class="synIdentifier">&#60;</span><span class="synStatement">div</span><span class="synIdentifier"> </span><span class="synType">class</span><span class="synIdentifier">=</span><span class="synConstant">&#34;Title&#34;</span><span class="synIdentifier">&#62;</span>title<span class="synIdentifier">&#60;/</span><span class="synStatement">div</span><span class="synIdentifier">&#62;</span>
<span class="synIdentifier">&#60;/</span><span class="synStatement">li</span><span class="synIdentifier">&#62;</span>
<span class="synIdentifier">&#60;/</span><span class="synStatement">div</span><span class="synIdentifier">&#62;</span>
<span class="synIdentifier">&#60;</span><span class="synStatement">div</span><span class="synIdentifier"> </span><span class="synType">class</span><span class="synIdentifier">=</span><span class="synConstant">&#34;comment&#34;</span><span class="synIdentifier">&#62;</span>
<span class="synIdentifier">&#60;</span><span class="synStatement">li</span><span class="synIdentifier">&#62;</span>
<span class="synIdentifier">&#60;</span><span class="synStatement">div</span><span class="synIdentifier"> </span><span class="synType">class</span><span class="synIdentifier">=</span><span class="synConstant">&#34;Title&#34;</span><span class="synIdentifier">&#62;</span>title<span class="synIdentifier">&#60;/</span><span class="synStatement">div</span><span class="synIdentifier">&#62;</span>
<span class="synIdentifier">&#60;/</span><span class="synStatement">li</span><span class="synIdentifier">&#62;</span>
<span class="synIdentifier">&#60;/</span><span class="synStatement">div</span><span class="synIdentifier">&#62;</span>
<span class="synIdentifier">&#60;/</span><span class="synStatement">ol</span><span class="synIdentifier">&#62;</span>
</pre>
  
  <h5>
    表示
  </h5>
  
  <ol>
    <div class="comment">
      <li>
        <div class="Title">
          title
        </div>
      </li>
    </div>
    
    <div class="comment">
      <li>
        <div class="Title">
          title
        </div>
      </li>
    </div>
  </ol>
  
  <p>
  </p>
  
  <p>
    Operaだと1. title（改行）1. titleと表示される。
  </p>
  
  <p>
    Firefoxだと1. title（改行）2. titleと表示される。
  </p>
</div>