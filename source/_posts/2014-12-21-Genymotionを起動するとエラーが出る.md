---
title: Genymotionを起動するとエラーが出る
date: 2014-12-21 12:00:25
category: 技術ネタ
tags: Android
---

12 月頃に PC を買い換えた。ちょうど Android Studio の 1.0(正式版)がリリースされていたのでインストールしてみた。
デフォルトのエミュレーターでは起動に時間がかかりすぎるので Genymotion を使おうとしたのだが、いざ起動してみると

```
Warning: CPU number has been forced to 1.
```

というエラーが出た。

## 解決法

BIOS の設定から「Virtualization technologies」というのを enable にすればいいらしい。

## BIOS の設定方法

BIOS のメニューといえば PC の起動のときにファンクションキーのどれかを押して入れるものだと記憶していたのだが、windows8 では違うらしい。
「設定」->「PC の設定の変更」->「保守と管理」->「回復」と辿り、「PC の起動をカスタマイズする」の「今すぐ再起動」を選び、再起動する。

<img src="https://salmon2073.net/wp/wp-content/img/setting2.png">

再起動すると見慣れない画面が表示される。
「トラブルシューティング」->「詳細設定」と辿り、「UEFI ファームウェアの設定」を選ぶ。
ここでも「再起動」選ぶとようやく BIOS 設定画面が立ち上がる。
ここから先は BIOS によって設定方法が違うが、「Virtualization technologies」という項目を見つけて enable にすればよい。
設定を変えたら保存することを忘れないように。
