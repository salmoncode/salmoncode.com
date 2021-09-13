---
title: Processingでスケッチ（２）
date: 2013-12-26 15:44:12
category: プログラミング
tags: Processing
thumbnail: https://cdn-ak.f.st-hatena.com/images/fotolife/s/salmon2073/20131223/20131223164309.jpg
---

## はじめに

前の記事で図形を描く方法を述べた。
<a href="https://salmon2073.hatenablog.com/entry/2013/12/23/145446">Processing でスケッチ - 鮭の水槽</a>
今回はこれらに色を付けていこうと思う。



## Processing における「色」

Processing では、色は赤、緑、青を混ぜて作る RGB 方式がデフォルトである。もちろん、R は Red、G は Green、B は Blue からきている。
色に関する命令を記述する際には、基本的にパラメーター（数値）はこの３つを使うことが多い。



## 図形を塗りつぶす

実際に図形を塗りつぶしてみよう。

命令

<span style="color: #0000cc;">fill</span>( R の数値, G の数値 , B の数値  );
<span><img class="hatena-fotolife" title="f:id:salmon2073:20131223164309j:plain" src="https://cdn-ak.f.st-hatena.com/images/fotolife/s/salmon2073/20131223/20131223164309.jpg" alt="f:id:salmon2073:20131223164309j:plain" /></span>
この命令の後に描いた図形はすべて指定した色で塗りつぶされる。
各値の最大値は 255 で、値が大きければ大きいほどその要素が強くなる。
例えば、fill(255,0,0);ならば赤になる。
黄色は fill(255,255,0); で、紫は fill(255,0,255);である。僕は fill(0,255,255);が好みである。
ちなみに、fill(0,0,0);ならば黒、fill(255,255,255);ならば白である。
また、黒や白のように値がすべて同じ場合は
<span style="color: #0000cc;">fill</span>(数値);
と表してもよい。
この場合、255 段階のグレースケールになる。



## プログラムを実行する順番

プログラムの実行順序について考えよう。
プログラムは基本的に、<span style="color: #cc0000;">上から下</span>の順番で実行される。
よって、円のあとに四角形を重ねて描いた場合、四角形が前面に出ることになる。
だから、size();などはなるべく初めに書こう。



## 背景を塗りつぶす

図形だけでなく、時には背景を塗りつぶしたいこともあるだろう。キャンバスいっぱいに大きな四角形を描くというのも一つの手だが、Processing には背景を塗りつぶす命令が用意されている。

命令

<span style="color: #0000cc;">background</span>( R , G , B );
<span><img class="hatena-fotolife" title="f:id:salmon2073:20131223165156j:plain" src="https://cdn-ak.f.st-hatena.com/images/fotolife/s/salmon2073/20131223/20131223165156.jpg" alt="f:id:salmon2073:20131223165156j:plain" /></span>
実は、この命令が実行されるとそれまで描かれていた図形も塗りつぶされてしまう。図形を描く前に記述しよう。



## 塗りつぶさない

図形は最初白で塗りつぶされているが、完全に透明な図形を描きたいこともあると思う。

命令

<span style="color: #0000cc;">noFill</span>(); 
<span><img class="hatena-fotolife" title="f:id:salmon2073:20131223170527j:plain" src="https://cdn-ak.f.st-hatena.com/images/fotolife/s/salmon2073/20131223/20131223170527.jpg" alt="f:id:salmon2073:20131223170527j:plain" /></span>
パラメーター（数値）はない。つまり、上記をそのままコピペしてもよい。



## Processing における単語の区別

Processing の命令において、２単語から成る命令は後ろの単語の頭文字が大文字になる。
例えば、前述の noFill();の場合、no+fill なので noFill になる。



## 透過度

これまで、RGB やグレースケールのみを扱ってきたが、半透明にしたり、中途半端に透かしたいこともあるだろう。
色の命令にはさらにもう一つパラメータを追加することができる。
例えば、
fill(255,0,0,255);
とすると、真っ赤に塗りつぶされるが、
fill(255,0,0,0);
とすると、透明になる。
fill(255,0,0,100);
とすると、半透明のようになる。
<span><img class="hatena-fotolife" title="f:id:salmon2073:20131223165538j:plain" src="https://cdn-ak.f.st-hatena.com/images/fotolife/s/salmon2073/20131223/20131223165538.jpg" alt="f:id:salmon2073:20131223165538j:plain" /></span>



## 終わりに

今回は内容が多く、初めて読む人にとっては少々重かったかもしれない。
実は、ここに乗っている全ての情報が必ずしも必要とは限らない。目的の達成のために必要のない情報は読み飛ばしてもらっても構わないのだ。



##  
