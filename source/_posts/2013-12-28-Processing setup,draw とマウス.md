---
title: Processing setup,draw とマウス
date: 2013-12-28 20:01:59
category: プログラミング
tags: Processing
---

## はじめに

前の記事までで、基本的な図形や点、線を描くことができ、色や大きさまで変えられるようになるはずである。これだけでももうプログラマーと名乗っていいいのではないだろうか。
しかし、皆さんは「これではペイントツールとおなじでは…」と思われるかもしれない。
そこで、プログラムに新たな機能を追加して「プログラム感」を味わっていただきたい。



## 保存する

自分の画面上のプログラムを人に見せるだけではつまらない。
保存方法を考えよう。
①.pde ファイルで保存する。
プログラムをそのまま保存する方法である。
File → Save As で名前をつけて保存できる。上書き保存したい場合は Save を選ぼう。
②.exe ファイルで保存する。
この方法だと、プログラムを書きかえれなくなる代わりに、ほとんどどの PC でも動く実行ファイルにして保存できる。
File → Export Application → 任意の場所を選ぶ → Export
① の方法で保存していない場合、途中で聞かれるので保存しよう。



## setup,draw について

Processing のプログラミングにおける性質をより深く知ってもらうためには、setup,draw という考え方が不可欠である。
setup とは、初期設定のことである。
draw とは、初期設定後の繰り返し作業（ルーチン）のことである。
これをプログラムに組み込むことで、できることの幅が広がる。

setup,draw を利用したプログラム

<span style="color: #00cccc;">void</span> <span style="color: #0000cc;">setup</span>(){<br />size(400,400);<br />}
<span style="color: #00cccc;">void</span><span style="color: #0000cc;"> draw</span>(){<br />ellipse(200,200,100,100);<br />}

上記のプログラムをコピペか記述して、実行してみよう。
画面の中に円が描かれていれば成功である。
今までのプログラムと何も違わないように見えると思う。しかし、今回のプログラムと今までのプログラムでは決定的に違う点がある。
それは、<span style="color: #cc0000;">描かれ続けている</span>ということだ。

まずは、setup から詳しい説明をしよう。
<span style="color: #00cccc;">void <span style="color: #0000cc;">setup</span></span>(){
初期設定
}
である。
「void」 という単語や setup の後についている「()」については今は特に意味がない。
覚えていただきたいのはその後の「{}」の中に初期設定を記述するということだ。
初期設定は、はじめに一回実行されるとその後はもう行われない作業のことである。
例えば、size(); がそうである。毎回ウィンドウのサイズを決めなくても、普通ウィンドウの大きさは一定である。
ちなみに setup,draw が導入されていない今までのプログラムは、全て setup であるという見方もできる。

次に、draw について説明しよう。
<span style="color: #00cccc;">void</span> <span style="color: #0000cc;">draw</span>(){
繰り返し作業（ルーチン）
}
である。
こちらも「void」や「()」について今は意味がない。
繰り返し作業は、setup のあとに、１秒に約６０回のペースで行われ続ける。
プログラムのメインはこっちである。



## setup,draw の使い方

パラパラ漫画を思い浮かべて欲しい。棒人間が踊っているとする。
ページの大きさや紙の厚さは途中で変える必要がないだろう。一度決めれば十分である。これが setup である。
棒人間は１ページごとに（あるいは４ページかもしれない）ポーズを変えてやる必要がある。棒立ちでは面白くないからだ。これが draw である。
Processing では、この「ページ」を「フレーム」と呼ぶ。フレームごとに絵をかえてやればプログラムが「動いているように」見える。　いや、「動いている」のだ。
  もっとも、そのためにはフレームごとに絵を変える方法を知らないといけない。
手っ取り早いのはマウスをつかうことである。



## マウスの使い方

いよいよプログラムを「動かす」時がきた。
<span style="color: #00cccc;">void</span> <span style="color: #0000cc;">setup</span>(){<br /><span style="color: #0000cc;">size</span>(400,400);<br />}
<span style="color: #00cccc;">void</span> <span style="color: #0000cc;">draw</span>(){<br /><span style="color: #0000cc;">ellipse</span>(<span style="color: #cc00cc;">mouseX</span>,<span style="color: #cc00cc;">mouseY</span>,30,30);<br />}
上記のプログラムをコピペまたは記述して実行してみよう。
そしてウィンドウの上でマウスカーソルを動かしてみよう。
マウスカーソルに円がついてきたら成功である。

感動の一瞬である。

さて、解説をしよう。

変数

```
mouseX　マウスのｘ座標
mouseY　マウスのｙ座標
```

プログラミングにおいて変数とは、数字の入れ物のことである。
マウスを動かすと、マウスカーソルの座標が動くので、mouseX と mouseY も変わる。
その場所を指定して ellipse(); を記述してやればマウスカーソルの場所に円が出現し、追尾してくるように見えるというわけである。

次に、直前に描かれた円を消してみよう。
<span style="color: #00cccc;">void</span> <span style="color: #0000cc;">setup</span>() {<br />  <span style="color: #0000cc;">size</span>(400, 400);<br />}
<span style="color: #00cccc;">void</span> <span style="color: #0000cc;">draw</span>() {<br /> <span style="color: #0000cc;"> background</span>(255);<br />  <span style="color: #0000cc;">ellipse</span>(<span style="color: #cc00cc;">mouseX</span>, <span style="color: #cc00cc;">mouseY</span>, 30, 30);<br />}
上記をコピペしてもいいが、要するに ellipse();の前に background();を記述するだけである。
色についてはこちらを見ていただきたい。
<a href="https://salmon2073.hatenablog.com/entry/2013/12/23/154412">Processing でスケッチ（２） - 鮭の水槽</a>



## マウスを使って色を変える

色の話題が出てきたところで、背景色をマウスの位置によってかえるプログラムを考えてみよう。
background();はパラメーターを３つ持つが、マウスからは mouseX と mouseY しか情報がとれない。そこで、今回は R と G をそれぞれ mouseX,mouseY にあててみよう。
<span style="color: #00cccc;">void</span><span style="color: #0000cc;"> setup</span>() {<br /><span style="color: #0000cc;">  size</span>(400, 400);<br />}
<span style="color: #00cccc;">void</span> <span style="color: #0000cc;">draw</span>() {<br />  <span style="color: #0000cc;">background</span>(<span style="color: #cc00cc;">mouseX</span>,<span style="color: #cc00cc;">mouseY</span>,0);<br />}
となる。

ところで、色は 255 段階しかないのに対し mouseX,mouseY は size(400,400);なのでそれぞれ 400 まであるはずである。255 を超えたらどうなるのだろう？

色は 255 を超えても 255 に直される。だから、mouseX が 255 より右に行ったとしてもそれ以上色は変わらないのだ。



## 終わりに

今回はマウスカーソルの座標を用いて setup,draw について解説した。通常では味わえない「プログラム感」を味わっていただければ本望である。
ただし、変数についてはまた期を新たにじっくり取り組む必要があるし、最低限の説明ができているのかも分からない。Wikipedia にも確実な解説がなかったときは正直驚いた。それだけ人に文字で説明するのが難しいテーマなのかもしれない。
ところで、今回画像を用いていないのはいじわるではなく、手持ちのツールでは原理的にマウスカーソルを画像に表示できなかったためである。プリントスクリーンも勝手が悪い。どこかにいいツールがないものだろうか。
そのうち自分でつくろうと思う。

##  
