---
title: Processingで複数のwebカメラを扱う
date: 2014-07-13 11:05:31
category: Processing
---

今回はprocessingでカメラを起動、複数のカメラをあつかうところまでやってみたい。

## カメラを使う

Processingでは、webカメラや内蔵カメラをとても簡単に扱うことができる。
標準のライブラリだけで動くので、以下のコードを張り付ければよい。

<script src="https://gist.github.com/salmon2073/5ba5fb34123076b9186d.js"></script>

カメラを名前から指定してつかう場合は、まずカメラのリストを表示する。<script src="https://gist.github.com/salmon2073/3b84652ffa2c909bcb11.js"></script>
つづいて、表示したいカメラのname= の部分を以下のコードに組み込めばok

<script src="https://gist.github.com/salmon2073/54c37ed762cd5ebbb755.js"></script>

## 複数のカメラを表示する

先ほどカメラの一覧表示をしたが、コンソールには接続されているカメラが全て表示される。 カメラのオブジェクトを増やせば、簡単に複数のカメラを表示することができる。 二つのカメラを扱う場合はこうなる<script src="https://gist.github.com/salmon2073/7914538e0e710879d801.js"></script>

