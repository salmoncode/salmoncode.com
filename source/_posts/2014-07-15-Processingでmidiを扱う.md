---
title: Processingでmidiを扱う
date: 2014-07-15 00:48:42
category: Processing
---

processingでmidiを扱う方法はいくつかあるが、僕が今まで使った中では「proMIDI」というライブラリが一番使い勝手が良かった。
今回はこのライブラリの使い方を説明しようと思う。

## proMIDIをスケッチに加える

まずは以下のページからライブラリをダウンロードしよう。

<a href="http://creativecomputing.cc/p5libs/promidi/">proMIDI</a>

展開してlibraryフォルダの中のpromidi.jarをprocessingのスケッチにドラッグ＆ドロップ。
念のためスケッチを保存しておこう。

## 音を鳴らしてみる

importして、単音を鳴らすまでのコードは以下のようになる。

<script src="https://gist.github.com/salmon2073/aa9f793eefa07196b9cd.js"></script>

楽器やノート（音符）を変えることで、PC上の音をいろいろ出せるだけでなく、PCに接続された外部midi音源から出力することもできる。
逆に、外部機器からmidi信号も受け取ることもできる。詳しくは上述のサイトのリファレンスを見ていただきたい。

## 終わりに

うまく使えばゲームやアプリケーションにも組み込めるだろうし、外部機器との連帯やmidiそのものを勉強する際にも役立つだろう。
また、導入が簡単なので、外部ライブラリを初めて扱う人などにはおすすめである。

