---
title: WordPress使用開始
author: hiroyuki_t
layout: post
date: 2012-05-02T11:08:57+00:00
url: /2012/05/02/200857/
categories:
  - WordPress

---
# WordPress使用開始

WordPressの使用を開始した。  
過去のデータははてなからMovable Type and TypePad Importerを使用してインポートした。  
一部手作業が発生したが問題なく終わった。

まずテーマを探したが、スマートフォン対応されているもの（viewport等の設定等があり、対応していそうなもの）がなかなか無く、標準のTwenty Elevenを使うことにした。  

ヘッダーのサイズが気になったので、  
Twenty Eleven Theme Extensionsでヘッダーの画像のサイズを変更した。  
またプラグインはWP SlimStatを入れた。

## 移行時に使用した設定の個人的なメモ

<day date=&#8221;([0-9]{4}\-[0-9]{2}\-[0-9]{2})&#8221; title=&#8221;(.+?)&#8221;(.|\n)+?</body>

<day date=&#8221;\1&#8243; title=&#8221;\2&#8243;><body><a href=&#8221;http://d.tflare.com/\1&#8243;>\2</a></body>

http://d.tflare.com/([0-9]{4})\-([0-9]{2})-([0-9]{2})

http://d.tflare.com/\1/\2/\3
