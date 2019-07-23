---
templateKey: blog-post
id: 263
title: TensorFlow/Cloud ML の概要(機械学習・人口知能の活用例)
date: 2019-02-10T20:57:53+09:00
author: Yuki Hirai
layout: post
guid: https://yabaiwebyasan.com/?p=263
permalink: /tensorflow-cloud-ml/
post_views_count:
  - "120"
image: /wp-content/uploads/2019/02/機械学習活用例-125x125.png
categories:
  - テクノロジー
---
どうも、<a href="https://twitter.com/iamseninja" target="_blank" rel="nofollow noopener">Yuki Hirai</a>です。

先日、

<span class="sobig"><b>Google Developers ML Summit Tokyo 2018</b></span>

に参加してきました。

アジェンダはざっとこんな感じです。

<blockquote class="twitter-tweet" data-width="550" data-dnt="true">
  <p lang="ja" dir="ltr">
    本日のアジェンダ
  </p>
  
  <p>
    &#8211; TensorFlowとCloudMLの概要<br />&#8211; MobileMLの概要<br />&#8211; ML APIとAutoMLで始める実践MLアプリ開発<br />&#8211; ML Kitの概要<br />&#8211; EdgeTPU<br />&#8211; Actions on Google<br />&#8211; BigQuery MLではじめる予測分析<br />&#8211; 機械学習プロジェクトにおけるCloud AI Platformの使い方　
  </p>
  
  <p>
    など<a href="https://twitter.com/hashtag/GoogleMLSummit?src=hash&ref_src=twsrc%5Etfw">#GoogleMLSummit</a>
  </p>
  
  <p>
    &mdash; Yuki Hirai👨‍💻 (@yabaiwebyasan) <a href="https://twitter.com/iamseninja/status/1073398380942962688?ref_src=twsrc%5Etfw">December 14, 2018</a>
  </p>
</blockquote>



ref: <a href="https://events.withgoogle.com/google-developers-ml-summit-tokyo-2018/" target="_blank">Google Developers ML Summit Tokyo 2018</a>

一部時間が被っていて参加できないものがありましたが、

自分が参加してところについて簡単にまとめていきますw

## TensorFlow と Cloud ML の概要

まずはTensorFlowとGoogleが提供している便利な機械学習のクラウドツールについて書いていきます。

## TensorFlowについて

TensorFlowとは機械学習開発のためのオープンソースツールです。  
これを用いて独学でセルフレジをつくった例もあります。

<span class="embed-youtube" style="text-align:center; display: block;"></span>

画像2万5千枚を手作業で撮影して学習データを蓄積したとのことです。

他にも機械学習によるタクシーの最適な配置を実現したり、

カタログショッピングでTPOのベクトルを抽出してレコメンドしたら  
コンバージョンレートがあがったなどの例もあります。

## 人工知能というバズワードについて

IT業界に関連する**バズワード**はいくつかあります

近年、機械学習や人工知能はまさにバズワードでしたね

いろんな意味でこれらのバズワードが使用されているので

まずは簡単に人工知能というワードについて整理しておくと

Googleの場合は**弱いAI**を開発しているとのことでした。

人間みたいな強いAIは実現できていないとのことです。

ちなみに強いAIや弱いAIという言葉は

強いAI => 人間の知能に迫るようになるか、人間の仕事をこなせるようになるか、幅広い知識と何らかの自意識を持つようになる  
弱いAI => 人間がその全認知能力を必要としない程度の問題解決や推論を行うソフトウェアの実装

といった意味合いで使われます。

ref: <a href="https://ja.wikipedia.org/wiki/%E5%BC%B7%E3%81%84AI%E3%81%A8%E5%BC%B1%E3%81%84AI" target="_blank">強いAIと弱いAI</a>

## りんごとみかんをどう分類するか？

弱いAIでは

**りんごとみかんをどう分類するか**

といった内容のことを自動化できないか実装します。

例えば

**ピクセルの色の平均値をとればプログラムでも分類できます**

ただ

**グレースケールされたりんごとみかんはどう判断する?**

という問題にぶつかります。

これまでのソフトウェア開発では

**ルールを人が決める**

というのが基本になっていました。

機械学習ではこれを計算機がルールをみるけてくれるようになります。

例えばGoogleが開発した**Cloud Vision API**では

過去の学習データからあらゆる画像データを判別することができるようになります。

現在の精度は1000枚中2,3枚は間違える程度とのことです。

完璧な判別ではないにしろ  
AIが怪しいところをいくつか提案することで  
人間が選択する上で効率化できるので  
生産性をあげることができます。

これらは

  * ニューラルネットワーク: 学習できる関数
  * ディープラーニング: 階層化により知識を得る

など2012年ごろから話題になっている技術を用いて実現することができるようになりました。

## Googleが提供するクラウド機械学習サービス

Googleではそれらを専門知識がなくても使えるようなツールを提供しています。

  * AutoML and CloudML APIs => 誰でも使える
  * BigQuery ML => SQLが使える人向けの機械学習 ロジスティック回帰など
  * TensorFlow and CloudML Engine => まぁまぁ専門家向け(入門書読んだ人もok)のツール

Wantedlyでは  
ユーザーのプッシュ通知を送るかどうかを  
BigQuery MLを使用して  
判定しているという実例があるそうです。

Cloud AutoMLでは  
カスタムモデル開発における煩雑な作業を自動化することもできます。

データの前処理、機械学習モデルのデザイン、機械学習モデルの最適化など

数百枚だけでもいいし  
精度をたけめたければ数千枚といった画像データを準備することで自動化が可能になります。

実際にCloud AutoMLで  
ラーメン二郎のラーメン画像が41店舗のどこで撮影されたものなのか  
を95%の精度で判定できるようになったとのことです。

他にも  
ライフルで物件画像のカテゴリ分類を大幅に改善した例もあるそうです。  
=> 物件画像の分類(外観、キッチン、バスルーム)など

次回: Mobile ML の概要について

<blockquote class="wp-embedded-content" data-secret="AZYknStyTK">
  <p>
    <a href="https://yabaiwebyasan.com/mobile-ml/">MobileMLの概要~アメリカでは3分の2の企業がアプリで機械学習を使用~</a>
  </p>
</blockquote>