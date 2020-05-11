---
title: Processingから外部プログラム・他のスケッチを起動する
date: 2019-10-30 16:35:50
category: 技術ネタ
tags: Processing
---

過去記事の再掲です。

Processingから他のプログラムを起動する話。

<!-- more -->

## Proessingから外部プログラムを起動する

Processingではjavaのコードが動くので、簡単に外部のプログラムを起動できる。

<script src="https://gist.github.com/salmoncode/19eae2b4874ea5ac3574.js"></script>

起動して何かキーを押すと「メモ帳」が立ち上がる。
<h3>他のスケッチを起動する</h3>
上記のように記述することでcmdのように外部コマンドを使用することができる。 これを利用することでProcessingからProcessingを起動できる。そのためには、Processingを起動するコマンドが必要だ。

## Processingをコマンドから起動する

Processingをダウンロードすると、「processing.exe」と一緒に「processing-java.exe」という実行ファイルもついてくる。環境変数にこいつのパスを通すことでコマンドからProcessingを起動することができるようになり、他のエディタでのコーディングが便利になったりする。これを利用してみよう。 Processingのスケッチを直接実行するコマンドは以下である
<script src="https://gist.github.com/salmoncode/3549394ec39b47716458.js"></script>