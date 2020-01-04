---
title:  Unity 2018.4.14f1でUnityの教科書 Unity2019完全対応版p55「Can't add script behaviour CallbackExecutor. The script needs to derive from MonoBehaviour!」の時の対処法
author: hiroyuki_t
layout: post
date: 2020-01-04T10:00:00+09:00
url: /2020/01/04/100000/
categories:
- Unity

---

# Unity 2018.4.14f1でUnityの教科書 Unity2019完全対応版p55「Can't add script behaviour CallbackExecutor. The script needs to derive from MonoBehaviour!」の時の対処法

Unity 2018.4.14f1で
Unityの教科書 Unity2019完全対応版 2D&3Dスマートフォンゲーム入門講座　p55のスクリプトのアタッチをしてみたところ

「Can't add script behaviour CallbackExecutor. The script needs to derive from MonoBehaviour!」のエラーになる。  
原因を調べてみたところ、ファイル名はクラス名でなければならないためだった。  
ファイル名を「NewBehaviourScript」に戻すとアタッチできた。  
おそらくバージョンの違いによるものと思われる。（新バージョンでは自動でクラス名が変更される機能がついているのでは？）  


Unityは2020年1月4日現在 Windowsで2018.4.14f1がデフォルトダウンロードされる。  
これはLTS（2 年間のサポート期間）の最新版が2018.4系であるためと思われる。  
LTSはバージョンが「.4」で終わることで判別可能  
詳しくは以下リンク先に記載がある。


[Unity の新しいリリースプラン：TECH ストリームと長期サポート（LTS）ストリームの導入](https://blogs.unity3d.com/jp/2018/04/09/new-plans-for-unity-releases-introducing-the-tech-and-long-term-support-lts-streams/)
