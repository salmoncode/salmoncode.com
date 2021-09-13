---
title: W32TeXとTeXstudioでWindowsにTeX環境を構築する
date: 2016-07-10 20:39:13
category: 技術ネタ
---

所要時間：約 30 分

TeX で文章を書いて PDF を出力できるようにするには，

- TeX ディストリビューション
- TeX エディタ

の二つのインストール作業を行う必要がある．

「TeX インストーラ 3」を使うとこの作業を全自動で行ってくれるので大変便利．

以下のサイトにインストール方法が詳しく書いてある．

<a href="https://did2memo.net/2016/04/24/easy-latex-install-windows-10-2016-04/">&#x7C21;&#x5358;LaTeX&#x30A4;&#x30F3;&#x30B9;&#x30C8;&#x30FC;&#x30EB;Windows&#x7DE8;&#xFF08;2016&#x5E74;4&#x6708;&#x7248;&#xFF09;</a>

※2016 年 7 月現在，W32TeX のダウンロード元が上から 2 番目になっているが，そのままだと情報取得に失敗するので 3 番目に変更する．

この方法だとエディタとして TeXWorks がインストールされる．個人的にはもうちょっと IDE っぽいやつが使いたかったので，
あえて TexWorks のチェックを外し，TeXstudio をインストールすることにした．

以下のリンクから最新版をダウンロードして手順通りに進めれば ok．

<a href="https://www.texstudio.org/">TeXstudio</a>

TeXstudio はインストール後にすこしだけ設定を変える必要がある．

「オプション」→「TeXstudio の設定」から，

- 「コマンド」の一番上「LaTeX」の latex.exe を platex.exe に書き換える．
- 「ビルド」の「ビルド&amp;表示」を「DVI->PDF チェーン」に変更，「既定のコンパイラ」を LaTeX に変更する．

これで ipsj のテンプレートからビルドを行うことができるようになる．
