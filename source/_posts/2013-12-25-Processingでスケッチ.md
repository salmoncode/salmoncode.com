---
title: Processingでスケッチ
date: 2013-12-25 14:54:46
category: プログラミング
tags: Processing
thumbnail: https://cdn-ak.f.st-hatena.com/images/fotolife/s/salmon2073/20131223/20131223145748.jpg
---

## はじめに

前の記事で Processing の導入方法を紹介した。

<a href="https://salmon2073.hatenablog.com/entry/2013/12/23/124337">Processing をはじめてみる - 鮭の水槽</a>

今回は、いよいよプログラムをつくっていきたいと思う。



## 画面を出す

Processing を起動したら、再生ボタンを押してみてほしい。
小さなウィンドウが出てきたと思う。
まずはこいつの大きさを変えてみよう。

命令

<span style="color: #0000cc;">size<span style="color: #000000;">( </span></span>横の長さ <span style="color: #000000;">, </span>縦の長さ <span style="color: #000000;">);</span>
<span><img class="hatena-fotolife" title="f:id:salmon2073:20131223145748j:plain" src="https://cdn-ak.f.st-hatena.com/images/fotolife/s/salmon2073/20131223/20131223145748.jpg" alt="f:id:salmon2073:20131223145748j:plain" /></span>
これを記述部に書き込むことでウィンドウの大きさを変えられる。
ここでコツがある。
まず、
<span style="color: #0000cc;">size</span>();
と入力してから数字を代入しよう。数値（パラメータという）を入力するたびに「,」を打つのを忘れないように。
ちなみに、size(　と入力した段階で　<span style="color: #0000cc;">size</span>( 　となったと思うが、この機能のおかげでどこが命令部なのかが分かったり、スペルミスをしていないかチェックできたりする。



## 円を描く

画面が表示できたら、そこに円を表示してみよう。

命令

<span style="color: #0000cc;">ellipse</span>( 中心のｘ座標 , 中心のｙ座標 , 横の大きさ , 縦の大きさ );
<span><img class="hatena-fotolife" title="f:id:salmon2073:20131223145834j:plain" src="https://cdn-ak.f.st-hatena.com/images/fotolife/s/salmon2073/20131223/20131223145834.jpg" alt="f:id:salmon2073:20131223145834j:plain" /></span>
ウィンドウの座標は左上が（０，０）になっている。ここで注意して欲しいのは、ｙ座標がしたに行くほど大きくなるということだ。皆さんにはこの感覚に慣れてほしい。
ちなみに、横の大きさと縦の大きさが違うと楕円になる。



## 四角形を描く

四角形を表示してみよう。

命令

<span style="color: #0000cc;">rect</span>( 左上の x 座標 , 左上のｙ座標 , 横の長さ , 縦の長さ );
<span><img class="hatena-fotolife" title="f:id:salmon2073:20131223145953j:plain" src="https://cdn-ak.f.st-hatena.com/images/fotolife/s/salmon2073/20131223/20131223145953.jpg" alt="f:id:salmon2073:20131223145953j:plain" /></span>



## 三角形を描く

三角形を表示してみよう。

命令

<span style="color: #0000cc;">triangle</span>( x1 , y1 , x2 , y2 , x3 , y3 );
<span><img class="hatena-fotolife" title="f:id:salmon2073:20131223150104j:plain" src="https://cdn-ak.f.st-hatena.com/images/fotolife/s/salmon2073/20131223/20131223150104.jpg" alt="f:id:salmon2073:20131223150104j:plain" /></span>
三つの頂点を結んだ三角形が表示される。



## 終わりに

今回は簡単な図形を描画する命令について述べた。
次回はこれらに色をつけてみようと思う。
<span><img class="hatena-fotolife" title="f:id:salmon2073:20131223151231j:plain" src="https://cdn-ak.f.st-hatena.com/images/fotolife/s/salmon2073/20131223/20131223151231.jpg" alt="f:id:salmon2073:20131223151231j:plain" /></span>



##  
