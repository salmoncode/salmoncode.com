---
title: Processingで動きのあるスケッチ
date: 2013-12-31 13:21:19
category: プログラミング
tags: Processing
---

## はじめに

今回は、変数をつかって動きのあるスケッチを描いてみようと思う。
大事な概念を扱うので、じっくり読んで欲しい。



## Processing における変数の使い方

Processing では変数を使う前に、これから何が（数値、文字など）入る変数を使うのかを宣言する必要がある。
具体的な方法は、

宣言

型   変数 ;
である。
変数の方は自分で決めた文字、例えば「ｘ」や「ｙ」を使う。「hoge」のように単語にしても問題はない。　ただし、2 単語以上使う場合は間にスペースを挟めないので、前述のとおり後ろの単語を大文字にしてつなげるのが一般的である。
型の方は既に用意されているものから選ぶことになる。Processing に用意されている主な型は、
float 　…　実数を扱う
int 　…　整数を扱う
cher 　…　文字を扱う
boolean 　…　真理値を扱う
他にもたくさんあるようだが、今回は十分である。
この中で最も見慣れないのは boolean 型ではないだろうか。boolean 型にはいる
データは二つしかなく、「true」と「false」である。yes と no と言い換えるとわかりやすいかもしれない。いずれプログラム中に出現するので、覚えておこう。



## 変数を使ったスケッチ

幸いにも、皆さんはすでに基本的な図形を数字を使って描くことができるので、あとはそこに変数を組み込むだけで動きのあるスケッチを描くことができる。
それをステップごとに解説していこう。
まず、変数を宣言して数字を代入、その座標に円を表示することからはじめてみよう。もちろん、setup,draw を使っていただきたい。
<span style="color: #00cccc;">void</span> <span style="color: #0000cc;">setup</span>() {<br />  <span style="color: #0000cc;">size</span>(400, 400);<br />  <span style="color: #990000;">int</span> x;<br />}
<span style="color: #00cccc;">void</span> <span style="color: #0000cc;">draw</span>() {<br /> <span style="color: #0000cc;"> ellipse</span>(x, 100, 50, 50);<br />}
どうだろう？<span style="color: #cc0000;">エラーが発生</span>しただろうか？
実は、このプログラムには間違いがある。
それは、変数を宣言する場所だ。

★ ローカル変数とグローバル変数
Processing において、変数には種類がある。
代表的なものはグローバル変数とローカル変数の区別である。
グローバル変数とは、<span style="color: #0000cc;">全体で共通に</span>使える変数である。
ローカル変数とは、<span style="color: #cc0000;">ある部分でのみ</span>使える変数である。
一つのプログラム中に両方つかわれても問題ない。
実際に使う際には、setup,draw など（これらをまとめてメソッドという）の外で宣言すればグローバル変数、中で宣言すればローカル変数である。
上記のプログラムの場合、setup 内でｘを宣言しているのでｘはローカル変数である。よって、この変数は setup 内でのみ使うことができる。そのため、draw 内の ellipse();で呼び出すことはできないのである。
このプログラムを正しく動かすには、draw 内でｘを宣言するか、外で宣言してやればいいのだ。今回は外で宣言してみよう。
<span style="color: #990000;">int</span> x;
<span style="color: #00cccc;">void</span> <span style="color: #0000cc;">setup</span>() {<br />  <span style="color: #0000cc;">size</span>(400, 400);<br />}
<span style="color: #00cccc;">void</span> <span style="color: #0000cc;">draw</span>() {<br />  <span style="color: #0000cc;">ellipse</span>(x, 100, 50, 50);<br />}
これでエラーはでないはずである。
ところで、皆さんは一つ疑問に思うことがないだろうか？ 
x に数字を代入していないのに自動で０ということになっている。
次はこのことについて解説しようと思う。



## 変数の初期化

変数は宣言しただけではまだ何のデータも入っていない。この「何もない」状態を「null」と表現する。int 型や、float 型の場合は、とりあえず 0 として扱う命令もあり先ほどのプログラムがその一例であるが、基本的には初期化をして扱う。
変数の初期化とは、簡単に言えば最初のデータを代入することである。
具体的には、int 型の場合
int x;
x=0;
と記述する。初期値を５にしたい場合は a=5;でよい。また、
int x= 0;
と記述することで宣言と初期化を同時に行うことができる。
Proessing の場合、グローバル変数は setup で初期かしておくのが無難だと思う。
以上のことを取り入れたプログラムを記述すると、
<span style="color: #990000;">int</span> x;
<span style="color: #00cccc;">void</span> <span style="color: #0000cc;">setup</span>() {<br />  <span style="color: #0000cc;">size</span>(400, 400);<br />  x = 0;<br />}
<span style="color: #00cccc;">void</span> <span style="color: #0000cc;">draw</span>() {<br />  <span style="color: #0000cc;">ellipse</span>(x, 100, 50, 50);<br />}<br />となる。



## Processing で図形を動かしてみる

それでは、いよいよ円を動かしてみよう。
方法は簡単で、draw の中の繰り返し処理を行う度に、x を増やしていけばよい。
<span style="color: #990000;">int</span> x;
<span style="color: #00cccc;">void</span> <span style="color: #0000cc;">setup</span>() {<br />  <span style="color: #0000cc;">size</span>(400, 400);<br />  x = 0;<br />}
<span style="color: #00cccc;">void</span> <span style="color: #0000cc;">draw</span>() {<br />  <span style="color: #0000cc;">ellipse</span>(x, 100, 50, 50);<br />  x = x+1;<br />}<br />以上のプログラムをコピペするか記述して動かしてみよう。
マウスを使った時とはまた違った感動がある。
ちなみに、初期値０を他の数に変えてあげれば開始地点が変わり、増加量を変えてあげれば速度が変わる。
ところで、プログラミングでは、a = a+1 というような処理が頻繁にでてくる。そのため、より簡潔に記述する方法が用意されている。
a += 1;
これで「足して代入」という意味になる。また、
a++;
これで「1 を足して代入」という意味になる。

## 様々な動きをつけてみる
上記のことを応用すると、図形に様々な動きをつけることができる。
int x;<br />int y;<br />int z;
void setup() {<br />  size(400, 400);<br />  x = 0;<br />  y = 15;<br />}
void draw() {<br />  background(0);<br />  fill(z);<br />  ellipse(x, y, x*5, y*5);<br />  x++;<br />  y++;<br />  z++;
  if (z &gt;= 255) {<br />    z = 255;<br />  }<br />}
上記のプログラムでは、図形を描くまえに background();をいれることで残像を消している。色の塗りつぶしはグレースケールにして変数に置き換え、最後の条件文で z が 255 以上にならないようにしている。
条件文の書き方については、今までの記事を見て欲しい。
<a href="https://salmon2073.hatenablog.com/entry/2013/12/24/163913">プログラミングにおける演算・条件・繰り返し - 鮭の水槽</a>



## 終わりに

今回までの知識で、いろんなアニメーションをつくれるようになる。
皆さんは既に基本一通り（人によるが）を終えており、あとは組み合わせ方や便利な機能を使って好きなプログラムを組んでいくことが大事である。
Processing のリファレンスもページには、このブログで扱わなかった命令などがたくさん乗っているので、ぜひ確認して欲しい。
<a href="https://processing.org/reference/">Language Reference (API) \ Processing 2+</a>
