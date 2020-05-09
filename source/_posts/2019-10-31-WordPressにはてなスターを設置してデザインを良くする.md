---
title: WordPressにはてなスターを設置してデザインを良くする
date: 2019-10-31 16:18:44
tags:
---
このブログは更新するたびにTwitterで流すようにしてるのですが、ある日こんなことを言われました。

<blockquote class="twitter-tweet"><p lang="ja" dir="ltr">記事にいいねがつけたい！</p>&mdash; pvcresin (@pvcresin) <a href="https://twitter.com/pvcresin/status/1184079040056938497?ref_src=twsrc%5Etfw">October 15, 2019</a></blockquote> <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>

というわけで、はてなスターを設置することにしました。

<!-- more -->

## はてなスターの設置

いままで「はてなスター」は「はてなブログ」限定の機能だと思っていたのですが、どうやら外部のブログにも貼り付けることができるようです。

http://developer.hatena.ne.jp/ja/documents/star/misc/hatenastarjs

参考記事の手順に沿ってはてなスターを設置します。
wordpressの場合、トークン設定を`header.php`に記述して、`Hatena.Star.SiteConfig`は`single.php`に記述すると、記事のページのみに表示できます。

## デザインを良くする

めでたく設置されたスターを見ると、なんだか古いデザインになっています。
こんな感じ↓

![](https://lh3.googleusercontent.com/lhTwIvyXVMSJGyDsMc9aXAOJoDy8Z3rRLbdlkrx9qIJEvURD-K_ZRIAZ-TGb6VxKefenxybjvGcy5pWOPf2ZQKeBweQEB4ys8AlBDrNA0_r1YgUK_WJbDC8ZrjAOfcu8k9YXCzRFQj68rFqaKaVqglIdQBNWPA2FHsOeIQizp-VD76825kI9OCP84BYUxlPA7Hk55NbnKcYhjUrx4Y0HKrs_AkpclIAo8i_ubIcb4C5jhMUqyd9OW1by1nUCP7XfYIGMCLtm4hNpBCz3eG6VQmU4BSm8qAf2FhXBVHdJfCHZJwT-v0fSJoz1IB-5dexsY53IwnD5mBkH_kwOAPbLY-Jf6uQbSgyD4Hqlnxy4JNsYSGjxCAscrk-44e6wtB1nvAPRXxSx53Ae0-kti1QHcKJVg2g-Mkd2HZPv2Xr6j5Mq91P_gWX4DMt12Hh6z9P9iaaUa83W-F5ovE9mrjDr0uCpfu64riN5iDV7sY2B_zDVGJ2O3dZJil0U46vJKKl3aMzY23O3IWzH2k6gAQIOHGIK_8KQy75OootT7JvMUmYj9eU5copYVNQoxIFG4rE5As6TSLmToJ-vG5SSYTmd0wFSLbOlA7vVmGQP3xEvis_S9QqrnS1bPK18Ryr7jp_b0YEJS5EMfNtrkLurX-rXZP2GXx2GSSy8QzloCipKqDSUd0IXJnd0h8EXTp2F4y-YR2dmE7q3oqRVox7XhISYW-xSnyMRHVX1y2NjWEn2f-meJFQ=w64-h40-no)

ちょっとイケてないので、デザインを直してみます。

`single.php`のどこかに、以下のスクリプトをscriptタグで挿入します。WordPressの管理画面から「外観」-&gt;「テーマエディタ」と進むと、各テーマのPHPファイルを編集できます。
<script src="https://gist.github.com/salmoncode/08dde225da03ccbc1b7aea5cc152554d.js"></script>

続いて、WordPressの管理画面から「外観」-&gt;「カスタマイズ」と進み、「追加CSS」を選択します。

そこに以下のcssを記述しましょう。
<script src="https://gist.github.com/salmoncode/dcbc88cc4641578c71cee33e4e846662.js"></script>

これによって、ボタンが今のはてなブログっぽくなり、スターの背景にユーザアイコンが出るようになります。
こんな感じ↓

![](https://lh3.googleusercontent.com/YLPTDt6rncD_zDVC2dRuUZE8PWP61Lktf3WVFvp1DMjfL8mf-3vp2MXlh_rixR7rkH6_Uli-zV8vUXV5q0gextSWL4ilUxJXoq1we0t126ywRLqJMtF1HxhewaB4YIccwJCC0JkHz8ZdlUFI3ZUV8633t-kwHUMuiTRkWxoqmiN28Jky1YxjY18DImK_4kFupC2Axu8DaNGbTvrHULrvgtbggK-Dy4Fh8fxeQLkarxaLpk4txtadi0YKq4wdN1T_7tJBr6sxYAIkqNWeRq-t4IFJ7TDcaZWMEdLpP-6N0nflmHIfuNgY3ohxCEnF-Dd812DPsDhIT4rBQx8QDCsQinFZqiyr3kWUyB-lOqHMhLleBrLysq229Z_3ZFrS6EpNS0ey-6Z5tI9EjDuMmSqNBP0ZNVz5LIXHP8DO9U1bpJw5io0MDQkb3_MaS4kMVmPVV4Sz0J09nT3bfCqZzssbHb5XgPlq5fuqx83sPKGwXIjcbTRefXoGjhKyo5ruJWPyg3EhipzxYBKT0ZOeBDYOQW0lYPuEvO4JUdvAzkHS4YgU8aWsR3RNuoeiG5_w7wA4--QkBtQG_IpNabSmmOxvcT0jpLlHrzX9uNXwipPaKWIw-i2adYcWIVI2uD26fAspwUQPWl2PNDDD7msdbDFCLbtevHVRHP5fXsUTWqozkorkTTTJO5-vjO9WRS3EhCZQLFrefSM2sVQD6iWxR97dxQv55THAIdSjefTtLRxxX8o7jBA=w104-h43-no)

いい感じですね！
というわけで、イイねと思ったら押してくださいw
