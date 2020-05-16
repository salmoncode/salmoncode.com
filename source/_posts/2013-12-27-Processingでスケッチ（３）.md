---
title: Processingでスケッチ（３）
date: 2013-12-27 19:52:12
category: Processing
thumbnail: https://cdn-ak.f.st-hatena.com/images/fotolife/s/salmon2073/20131223/20131223194026.jpg
---

## はじめに
今回は、点・線 を描画してみようと思う。
そして、それらに色をつけたり大きさを変えたりしてみよう。
 
## 点を描く

命令

<span style="color: #0000cc;">point</span>( x , y );
<span><img class="hatena-fotolife" title="f:id:salmon2073:20131223194026j:plain" src="https://cdn-ak.f.st-hatena.com/images/fotolife/s/salmon2073/20131223/20131223194026.jpg" alt="f:id:salmon2073:20131223194026j:plain" /></span>
指定した位置に点が描画される。
え？真ん中に描いたんだけど、みえないかも…
 
## 線を描く

命令

<span style="color: #0000cc;">line</span>( x1 , y1 , x , y );
<span><img class="hatena-fotolife" title="f:id:salmon2073:20131223194130j:plain" src="https://cdn-ak.f.st-hatena.com/images/fotolife/s/salmon2073/20131223/20131223194130.jpg" alt="f:id:salmon2073:20131223194130j:plain" /></span>
始点の( x , y )から終点の( x , y )までの線分が表示される。
 
## 点・線に色をつける

命令

<span style="color: #0000cc;">stroke</span>( R , G , B );
<span><img class="hatena-fotolife" title="f:id:salmon2073:20131223194717j:plain" src="https://cdn-ak.f.st-hatena.com/images/fotolife/s/salmon2073/20131223/20131223194717.jpg" alt="f:id:salmon2073:20131223194717j:plain" /></span>
直後から描かれた点・線が指定した色になる。
やっぱり点は見えない。
 
## 点・線の大きさを変える
<span style="color: #000000;">・命令</span>
<span style="color: #0000cc;">strokeWeight</span>(大きさ);
<span><img class="hatena-fotolife" title="f:id:salmon2073:20131223194800j:plain" src="https://cdn-ak.f.st-hatena.com/images/fotolife/s/salmon2073/20131223/20131223194800.jpg" alt="f:id:salmon2073:20131223194800j:plain" /></span>
直後から描かれた点・線が指定した大きさになる。
ようやく点が出現した。
 
## 終わりに
これまでの命令を覚えることで、たいていの形を描くことはできるようなる。
次回からはさらに一歩進んだことをやりたいと思う。
 
 
 
---
