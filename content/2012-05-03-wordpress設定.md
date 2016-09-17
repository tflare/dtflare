---
title: WordPress設定
author: hiroyuki_t
layout: post
date: 2012-05-03T08:37:35+00:00
url: /2012/05/03/173735/
categories:
  - WordPress

---
**テーマ**

  * iFeature

html5対応、スマートフォン対応がなされており、シンプルなデザインのものという観点で決めた。

**プラグイン**

  * Akismet　スパムチェック
  * Broken Link Checker　リンクチェック
  * Google XML Sitemaps   サイトマップ作成
  * Simple Yearly Archive　アーカイブページ作成
  * SyntaxHighlighter Evolved　ソースコードのハイライトに使用
  * Quick Cache   キャッシュプラグイン　ページにもよるが2倍は早くなる。
  * WP Multibyte Patch　マルチバイト文字の取り扱い（日本語版に標準添付されている）
  * WP SlimStat　アクセス解析
  * WP-DBManager   データベースバックアップ

&nbsp;

Chrome Developer Toolsで測定すると、

Grid Archivesだとアーカイブ以外のページでも300ミリ秒程度遅くなるので、Simple Yearly Archiveに置き換え