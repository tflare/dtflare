---
title: MhtViewerのintent-filterの現状
author: hiroyuki_t
layout: post
date: 2013-01-26T06:17:08+00:00
url: /2013/01/26/151708/
categories:
  - Android

---
AndroidにMhtViewerをインストールするとファイルマネージャでHTMLファイルを選択した際に    
MhtViewerが選択肢に現れる事がある。    
これについて現在わかっている情報をまとめる。

MhtViewerのintent-filterは以下としている。
`AndroidにMhtViewerをインストールするとファイルマネージャでHTMLファイルを選択した際に    
MhtViewerが選択肢に現れる事がある。    
これについて現在わかっている情報をまとめる。  
MhtViewerのintent-filterは以下としている。
`

まずandroid:pathPatternのみの設定で良いのではないかと思うかもしれないが    
android:pathPatternでは反応しないファイルマネージャがあるためandroid:mimeTypeも設定している。  
android:mimeType=&#8221;message/rfc822&#8243;だけではなく、android:mimeType=&#8221;text/html&#8221;も対象にしている。

これはファイルマネージャによっては、MHTML形式のファイルをmimeType=&#8221;text/html&#8221;と誤判定する場合があるためである。

上記のため、現状では上記設定としている。

ファイルマネージャがファイルの判定を拡張子で行い、mimeType=”message/rfc822と判定してくれれば問題はない。  
しかしファイルマネージャがファイルの中身でファイルを判定する場合、MHTML形式はHTMLファイルとの区別が難しいファイルもあるため誤判定によりandroid:mimeType=&#8221;text/html&#8221;と解釈されるケースがそれなりに存在する。

それを救うために上記intent-filterの設定にしている。  
とりあえず、上記設定としているが、もっと良い方はないのだろうか。
