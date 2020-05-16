---
title: Processing setup,draw とマウス
date: 2013-12-28 20:01:59
category: Processing
---

## はじめに
前の記事までで、基本的な図形や点、線を描くことができ、色や大きさまで変えられるようになるはずである。これだけでももうプログラマーと名乗っていいいのではないだろうか。
しかし、皆さんは「これではペイントツールとおなじでは…」と思われるかもしれない。
そこで、プログラムに新たな機能を追加して「プログラム感」を味わっていただきたい。
 
## 保存する
自分の画面上のプログラムを人に見せるだけではつまらない。
保存方法を考えよう。
①.pdeファイルで保存する。
プログラムをそのまま保存する方法である。
File → Save As で名前をつけて保存できる。上書き保存したい場合は Save を選ぼう。
②.exeファイルで保存する。
この方法だと、プログラムを書きかえれなくなる代わりに、ほとんどどのPCでも動く実行ファイルにして保存できる。
File → Export Application → 任意の場所を選ぶ → Export
①の方法で保存していない場合、途中で聞かれるので保存しよう。
 
## setup,drawについて
Processingのプログラミングにおける性質をより深く知ってもらうためには、setup,drawという考え方が不可欠である。
setupとは、初期設定のことである。
drawとは、初期設定後の繰り返し作業（ルーチン）のことである。
これをプログラムに組み込むことで、できることの幅が広がる。
 
setup,drawを利用したプログラム

<span style="color: #00cccc;">void</span> <span style="color: #0000cc;">setup</span>(){<br />size(400,400);<br />}
<span style="color: #00cccc;">void</span><span style="color: #0000cc;"> draw</span>(){<br />ellipse(200,200,100,100);<br />}
 
上記のプログラムをコピペか記述して、実行してみよう。
画面の中に円が描かれていれば成功である。
今までのプログラムと何も違わないように見えると思う。しかし、今回のプログラムと今までのプログラムでは決定的に違う点がある。
それは、<span style="color: #cc0000;">描かれ続けている</span>ということだ。
 
まずは、setupから詳しい説明をしよう。
<span style="color: #00cccc;">void <span style="color: #0000cc;">setup</span></span>(){
初期設定
}
である。
「void」 という単語やsetupの後についている「()」については今は特に意味がない。
覚えていただきたいのはその後の「{}」の中に初期設定を記述するということだ。
初期設定は、はじめに一回実行されるとその後はもう行われない作業のことである。
例えば、size(); がそうである。毎回ウィンドウのサイズを決めなくても、普通ウィンドウの大きさは一定である。
ちなみにsetup,drawが導入されていない今までのプログラムは、全てsetupであるという見方もできる。
 
次に、drawについて説明しよう。
<span style="color: #00cccc;">void</span> <span style="color: #0000cc;">draw</span>(){
繰り返し作業（ルーチン）
}
である。
こちらも「void」や「()」について今は意味がない。
繰り返し作業は、setupのあとに、１秒に約６０回のペースで行われ続ける。
プログラムのメインはこっちである。
 
## setup,drawの使い方
パラパラ漫画を思い浮かべて欲しい。棒人間が踊っているとする。
ページの大きさや紙の厚さは途中で変える必要がないだろう。一度決めれば十分である。これがsetupである。
棒人間は１ページごとに（あるいは４ページかもしれない）ポーズを変えてやる必要がある。棒立ちでは面白くないからだ。これがdrawである。
Processingでは、この「ページ」を「フレーム」と呼ぶ。フレームごとに絵をかえてやればプログラムが「動いているように」見える。　いや、「動いている」のだ。
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
マウスを動かすと、マウスカーソルの座標が動くので、mouseXとmouseYも変わる。
その場所を指定してellipse(); を記述してやればマウスカーソルの場所に円が出現し、追尾してくるように見えるというわけである。
 
次に、直前に描かれた円を消してみよう。
<span style="color: #00cccc;">void</span> <span style="color: #0000cc;">setup</span>() {<br />  <span style="color: #0000cc;">size</span>(400, 400);<br />}
<span style="color: #00cccc;">void</span> <span style="color: #0000cc;">draw</span>() {<br /> <span style="color: #0000cc;"> background</span>(255);<br />  <span style="color: #0000cc;">ellipse</span>(<span style="color: #cc00cc;">mouseX</span>, <span style="color: #cc00cc;">mouseY</span>, 30, 30);<br />}
上記をコピペしてもいいが、要するにellipse();の前にbackground();を記述するだけである。
色についてはこちらを見ていただきたい。
<a href="http://salmon2073.hatenablog.com/entry/2013/12/23/154412">Processingでスケッチ（２） - 鮭の水槽</a>
 
## マウスを使って色を変える
色の話題が出てきたところで、背景色をマウスの位置によってかえるプログラムを考えてみよう。
background();はパラメーターを３つ持つが、マウスからはmouseXとmouseYしか情報がとれない。そこで、今回はRとGをそれぞれmouseX,mouseYにあててみよう。
<span style="color: #00cccc;">void</span><span style="color: #0000cc;"> setup</span>() {<br /><span style="color: #0000cc;">  size</span>(400, 400);<br />}
<span style="color: #00cccc;">void</span> <span style="color: #0000cc;">draw</span>() {<br />  <span style="color: #0000cc;">background</span>(<span style="color: #cc00cc;">mouseX</span>,<span style="color: #cc00cc;">mouseY</span>,0);<br />}
となる。
 
ところで、色は255段階しかないのに対しmouseX,mouseYはsize(400,400);なのでそれぞれ400まであるはずである。255を超えたらどうなるのだろう？
 
色は255を超えても255に直される。だから、mouseXが255より右に行ったとしてもそれ以上色は変わらないのだ。
 
## 終わりに
今回はマウスカーソルの座標を用いてsetup,drawについて解説した。通常では味わえない「プログラム感」を味わっていただければ本望である。
ただし、変数についてはまた期を新たにじっくり取り組む必要があるし、最低限の説明ができているのかも分からない。Wikipediaにも確実な解説がなかったときは正直驚いた。それだけ人に文字で説明するのが難しいテーマなのかもしれない。
ところで、今回画像を用いていないのはいじわるではなく、手持ちのツールでは原理的にマウスカーソルを画像に表示できなかったためである。プリントスクリーンも勝手が悪い。どこかにいいツールがないものだろうか。
そのうち自分でつくろうと思う。
 
---
