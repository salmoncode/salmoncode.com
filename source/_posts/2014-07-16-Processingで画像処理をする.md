---
title: Processingで画像処理をする
date: 2014-7-16 16:54:58
category: プログラミング
tags: Processing
---

processing はビジュアルデザインのための言語であるが、それだけに画像処理も得意としている。
今回は僕が processing を用いて画像処理を学ぶ際の主な手法を紹介したいと思う。

<!-- more -->

## 画像を表示する

processing で画像を表示するには、まずスケッチに画像をドラッグ&amp;ドロップする。
画像の拡張子は、.gif, .jpg, .tga, .png がいいだろう。
それでは、さっそく画像を表示してみよう。Girl.jpg を表示するコードは以下のようになる。

<script src="https://gist.github.com/salmon2073/ae7447048e64892606ed.js"></script>

実行結果は以下のようになる

<img src="https://www5469up.sakura.ne.jp/file/Girl.png" alt="そのままの画像" />

## 画像のサイズについて

画像のサイズは画像を表示させる関数 image()で指定することができる。画面全体に表示したいときは width,height を指定すればいいのだが、 縦横の比率を維持したかったり n 倍という形で表現したかったりすることもある。 そのようなときは、サイズを取得するメソッドを使うことで画像の元のサイズを取得するとよい。

<script src="https://gist.github.com/salmon2073/49783ef7f593efb81206.js"></script>

## 画像のピクセルデータを取得、セットする

processing の場合、画像ファイル自体のデータを扱うよりも、画面のピクセルデータを取得して扱うことが多い。
ピクセルデータを取得するには get(x 座標,ｙ座標) セットするには set(x 座標,ｙ座標) を使う。

## 色を反転、2 値化

それでは簡単に画像処理を行ってみよう。まずはピクセルデータを取得し、それから R,G,B の成分を取り出す。
それらに変更を加えたものを表示する　という作業をウィンドウ全体のピクセルに対して行う。
画像の色をを反転させるコードは以下のようになる。

<script src="https://gist.github.com/salmon2073/1b0e5e54ab39f6a9378b.js"></script>

実行結果は以下のようになる

<img src="https://www5469up.sakura.ne.jp/file/Girl_reverse.png" alt="反転した画像" />

続いて 2 値化してみよう。get() から得られた RGB を求め、任意の値より小さければ黒、大きければ白にセットする。 画像を 2 値化するコードは以下のようになる。

<script src="https://gist.github.com/salmon2073/c00ff3d42c27f16c22d4.js"></script>

実行結果は以下のようになる

<img src="https://www5469up.sakura.ne.jp/file/Girl_grayScale.png" alt="反転した画像" />

輝度については以下のページに詳しく書いてある。

## 画像を出力する

処理した画像を出力するには、いろいろな方法がある。僕は主に saveFrame()で出力しているが、processing の公式リファレンスを読むのがいいと思う。

## 終わりに

上記のコードから、基本は get()と set()で間に様々な処理を挟めることが分かる。
もっといろいろなことがしたい人は信号処理の理論的な勉強をしてみることをおすすめする。
