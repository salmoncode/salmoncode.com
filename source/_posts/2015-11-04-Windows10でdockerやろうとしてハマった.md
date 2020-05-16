---
title: Windows10でdockerやろうとしてハマった
date: 2015-11-04 14:20:31
---

ローカルでの開発にdocker使ってみようと思ってハマったのでメモ．

Windowsでdockerを直接使うことはできないので，dockerが動いている仮想環境にアクセスして間接的に操作することになる．

dockerが入った仮想マシンを用意してくれるboot2dockerというものを見つけたのでインストールしてみたが，これは既に非推奨らしくdocker-machineを使えとのこと．

というわけでdocker-machineをインストール chocolateyなら簡単である

```
choco install docker-
```

以下のコマンドで仮想環境はが作れるはず

```
docker-machine create -d virtualbox dev
```

さてマシンを作るぞー とコマンドを打つとなにやらエラーが

```
Error creating machine: exit status 1
```

このままでは何が悪いのか分からないので、とりあえずググってみたところ、デバッグ用のオプションがあるらしい

そして見つけたエラーがこれ

```
error: Failed to create the host-only adapter
```

ネットワークがなんか悪いのかなーと思ってしばらくvbox弄ってみたりバージョンを落としたりしたけど変わらず…

しょうがないのでまたググってみるとこの記事にたどり着いた

<iframe src="//hatenablog-parts.com/embed?url=http%3A%2F%2Fd.hatena.ne.jp%2Fkobarn%2F20150805" title="Vagrantでのhost-only adapterのエラーを回避する方法 on Windows10" class="embed-card embed-webcard" scrolling="no" frameborder="0" style="display: block; width: 100%; height: 155px; max-width: 500px; margin: 10px 0px;"></iframe><cite class="hatena-citation"><a href="https://d.hatena.ne.jp/kobarn/20150805">d.hatena.ne.jp</a></cite>

Windows10が悪いんか…
解決法はあるようなので、その通りにexeファイルをダウンロード、起動したままさっきのコマンドを打ったら見事にエラーは消え去った

