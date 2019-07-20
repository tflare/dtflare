---
title: YubiKey 5 NFC
author: hiroyuki_t
layout: post
date: 2019-07-20T16:30:00+09:00
url: /2019/07/20/163000/
categories:
- Comp

---

# YubiKey 5 NFC 設定
YubiKey 5 NFCが届いたので、個人的によく使用しているサービスに設定した。
Security keysの設定ができないものについては、SMS認証のみを行った。

GitHubがChromeのみを対応としているのが残念。
ブラウザにVivaldiを使用していて、FIDO U2F対応しているのに使えない。

後は、YubiKey 5 NFCをSSHの秘密鍵の保存に使用しようと思っている。


|              | SMS認証 | Security keys(YubiKey 5) | 備考                                                   |
|--------------|:-------:|:------------------------:|--------------------------------------------------------|
| Google       |    ◎    |             ◎            |                                                        |
| Twitter      |    ◎    |             ◎            |                                                        |
| Facebook     |    ◎    |             ◎            |                                                        |
| GitHub       |    ◎    |             ×            | Security keys使用できない、Chromeのみ対応？            |
| Slack        |    ◎    |             ×            | Security keys使用できない                              |
| Amazon.co.jp |    ◎    |             ×            | Security keys使用できない、バックアップ用にAuthyを設定 |
| Microsoft    |    ◎    |             ×            | Security keys使用できない、Edgeのみ対応？              |





