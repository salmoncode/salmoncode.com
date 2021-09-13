---
title: Windows10でdockerやろうとしてハマった
date: 2015-11-04 14:20:31
category: 技術ネタ
---

ローカルでの開発に docker 使ってみようと思ってハマったのでメモ．

Windows で docker を直接使うことはできないので，docker が動いている仮想環境にアクセスして間接的に操作することになる．

docker が入った仮想マシンを用意してくれる boot2docker というものを見つけたのでインストールしてみたが，これは既に非推奨らしく docker-machine を使えとのこと．

というわけで docker-machine をインストール chocolatey なら簡単である

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

ネットワークがなんか悪いのかなーと思ってしばらく vbox 弄ってみたりバージョンを落としたりしたけど変わらず…

しょうがないのでまたググってみるとこの記事にたどり着いた

<iframe src="//hatenablog-parts.com/embed?url=http%3A%2F%2Fd.hatena.ne.jp%2Fkobarn%2F20150805" title="Vagrantでのhost-only adapterのエラーを回避する方法 on Windows10" class="embed-card embed-webcard" scrolling="no" frameborder="0" style="display: block; width: 100%; height: 155px; max-width: 500px; margin: 10px 0px;"></iframe><cite class="hatena-citation"><a href="https://d.hatena.ne.jp/kobarn/20150805">d.hatena.ne.jp</a></cite>

Windows10 が悪いんか…
解決法はあるようなので、その通りに exe ファイルをダウンロード、起動したままさっきのコマンドを打ったら見事にエラーは消え去った
