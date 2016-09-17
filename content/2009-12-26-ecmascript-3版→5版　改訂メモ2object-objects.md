---
title: ECMAScript 3版→5版　改訂メモ2(Object Objects)
author: hiroyuki_t
layout: post
date: 2009-12-26T07:06:34+00:00
url: /2009/12/26/160634/
categories:
  - Prog

---
<div class="section">
  <p>
    15.2 Object Objectsのメモ
  </p>
  
  <p>
    以下が追加されている
  </p>
  
  <p>
  </p>
  
  <h4>
    15.2.3.2 Object.getPrototypeOf ( O )
  </h4>
  
  <p>
    オブジェクトのプロトタイプを取得
  </p>
  
  <h4>
    15.2.3.3 Object.getOwnPropertyDescriptor ( O, P )
  </h4>
  
  <p>
    Pのプロトタイプ情報を取得
  </p>
  
  <h4>
    15.2.3.4 Object.getOwnPropertyNames ( O )
  </h4>
  
  <p>
    オブジェクトのプロパティを取得
  </p>
  
  <h4>
    15.2.3.5 Object.create ( O [, Properties] )
  </h4>
  
  <p>
    既存オブジェクトをプロパティとして新しいオブジェクトを生成
  </p>
  
  <h4>
    15.2.3.6 Object.defineProperty ( O, P, Attributes )
  </h4>
  
  <p>
    オブジェクトのプロパティを設定する。
  </p>
  
  <h4>
    15.2.3.7 Object.defineProperties ( O, Properties )
  </h4>
  
  <p>
    オブジェクトのプロパティを設定する。
  </p>
  
  <h4>
    15.2.3.8 Object.seal ( O )
  </h4>
  
  <p>
    オブジェクトのプロパティの追加、削除をできないようにする。
  </p>
  
  <h4>
    15.2.3.9 Object.freeze ( O )
  </h4>
  
  <p>
    オブジェクトのプロパティの追加、変更、削除をできないようにする。
  </p>
  
  <h4>
    15.2.3.10 Object.preventExtensions ( O )
  </h4>
  
  <p>
    オブジェクトのプロパティの追加をできないようにする。
  </p>
  
  <h4>
    15.2.3.11 Object.isSealed ( O )
  </h4>
  
  <p>
    以下すべてを満たす時true、それ以外はfalseを返す
  </p>
  
  <p>
    オブジェクトのすべてのプロパティが削除できない
  </p>
  
  <p>
    オブジェクトのプロパティの追加ができない
  </p>
  
  <h4>
    15.2.3.12 Object.isFrozen ( O )
  </h4>
  
  <p>
    以下すべてを満たす時true、それ以外はfalseを返す
  </p>
  
  <p>
    オブジェクトのすべてのプロパティが変更、削除できない
  </p>
  
  <p>
    オブジェクトのプロパティの追加ができない
  </p>
  
  <h4>
    15.2.3.13 Object.isExtensible ( O )
  </h4>
  
  <p>
    以下の時trueそれ以外はfalseを返す
  </p>
  
  <p>
    オブジェクトのプロパティの追加ができない
  </p>
  
  <h4>
    15.2.3.14 Object.keys ( O )
  </h4>
  
  <p>
    オブジェクトのenumerableなプロパティを返す
  </p>
</div>