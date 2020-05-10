---
title: ProcessingでSQLiteを扱う
date: 2019-10-30 16:27:08
category: 技術ネタ
tags: Processing
---

過去記事の再掲です。

Processingでデータベースを扱うライブラリを使い、SQLiteにアクセスしてみる。

<!-- more -->

## 準備

まずはデータベース用のライブラリをスケッチに追加する。

メニューバーの「Sketch」→「Import Library」→「Add Library」と進み、ライブラリ検索画面を出す。

キーワードに「sql」と入力すれば一番上に「BezierSQLib」と出てくるのでそれをインストールしよう。 再びメニューバーから「Sketch」→「Import Library」と進むと先ほどインストールした「BezierSQLib」が追加されているので、これを選択すれば準備は完了である。

## SQLiteを扱ってみる

SQLiteオブジェクトを作成してクエリーを投げればok

<script src="https://gist.github.com/salmoncode/706d03ecf6b2858d537b.js"></script>

SQL文の中のクォーテーションマークはちゃんとエスケープしなければならないことに注意。

### 追記 06/26

返り値の取得の仕方が分からない場合や、数値の場合、13行目あたりで db.getColumnNames()を出力してやると、返り値のカラムが一覧で見れる