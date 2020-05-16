---
title: MinecraftサーバのログをSlackに流す
date: 2016-08-05 22:51:07
thumbnail: https://cdn-ak.f.st-hatena.com/images/fotolife/s/salmon2073/20160805/20160805234813.png
---

## はじめに

自前でマイクラ鯖を建ててマルチプレイをしていると，24時間出入りできて楽しい．

鯖内のログイン履歴やチャット履歴は自分がログインしてないときでも残る．
これを共有できれば，自分がいない間にあった出来事や鯖にログインしているメンバーの確認などがマイクラを起動しなくても可能になる．
また，ゲーム中にメモした座標などがログアウトしたあとにも残るので大変便利なのだ．

ログを共有するにはチャットサービスのbotにしてしまうのがよい．
ある程度のセキュリティに期待できるし，お気に入り機能や通知機能などが最初からそろっている．
ちょうど鯖メンバー用のSlackチームを作っていたので，今回はそれを利用することにした．

## 実装

Rubyのslack-ruby-clientを用いて書いてみた．
まずはgemのインストール．

```
gem install slack-ruby-client
```

minecraft_server.jarを設置しているディレクトリと同じ階層に以下のプログラムを設置．

<script src="https://gist.github.com/salmon2073/5e745965f9b936cb086bdf19df2a8a65.js"></script>

slackのアクセストークンを取得してきて書き換える．アクセストークンの取得方法は例えば以下の記事を参考にするとよい．
<iframe src="//hatenablog-parts.com/embed?url=http%3A%2F%2Fjoesbar.blog.jp%2Farchives%2F1059092482.html" title="Slackでボットを作る　カスタムボット連携編 : じょえずブログ" class="embed-card embed-webcard" scrolling="no" frameborder="0" style="display: block; width: 100%; height: 155px; max-width: 500px; margin: 10px 0px;"></iframe><cite class="hatena-citation"><a href="https://joesbar.blog.jp/archives/1059092482.html">joesbar.blog.jp</a></cite>

チャンネル名を書き換えよう．結構な量のログが流れるので，専用のチャンネルを新しく作るのがおススメ．
通知したいチャンネルにbotがいるか確認することを忘れずに．

あとは実行すれば鯖内の入退出や会話，死因や称号の情報がSlackに流れてくる．エラーが疑われる場合は4行目をコメントアウトしてデバッグしよう．

## おわりに

そのままの状態だとサーバの警告なども拾ってしまうので，運用する際にはある程度フィルタリングするのがよい．

うちの鯖のメンバーには今のところ好評である．メモ機能としても活躍している．
他の人がプレイしている情報を見るとついつい自分もやりたくなってしまうので，時間を溶かしすぎないようにしなければ．

<span itemscope itemtype="https://schema.org/Photograph"><img src="https://cdn-ak.f.st-hatena.com/images/fotolife/s/salmon2073/20160805/20160805235700.png" alt="f:id:salmon2073:20160805235700p:plain" title="f:id:salmon2073:20160805235700p:plain" class="hatena-fotolife" itemprop="image"></span>

