---
title: Genymotionを起動するとエラーが出る
date: 2014-12-21 12:00:25
category: Android
---

12月頃にPCを買い換えた。ちょうどAndroid Studioの1.0(正式版)がリリースされていたのでインストールしてみた。
デフォルトのエミュレーターでは起動に時間がかかりすぎるのでGenymotionを使おうとしたのだが、いざ起動してみると

```
Warning: CPU number has been forced to 1.
```

というエラーが出た。

## 解決法

BIOSの設定から「Virtualization technologies」というのをenableにすればいいらしい。

## BIOSの設定方法

BIOSのメニューといえばPCの起動のときにファンクションキーのどれかを押して入れるものだと記憶していたのだが、windows8では違うらしい。
「設定」->「PCの設定の変更」->「保守と管理」->「回復」と辿り、「PCの起動をカスタマイズする」の「今すぐ再起動」を選び、再起動する。

<img src="https://salmon2073.net/wp/wp-content/img/setting2.png">

再起動すると見慣れない画面が表示される。
「トラブルシューティング」->「詳細設定」と辿り、「UEFIファームウェアの設定」を選ぶ。
ここでも「再起動」選ぶとようやくBIOS設定画面が立ち上がる。
ここから先はBIOSによって設定方法が違うが、「Virtualization technologies」という項目を見つけてenableにすればよい。
設定を変えたら保存することを忘れないように。
