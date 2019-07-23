---
templateKey: blog-post
id: 274
title: Googleが提供する機械学習モデルの種類について
date: 2019-02-12T20:42:57+09:00
author: Yuki Hirai
layout: post
guid: https://yabaiwebyasan.com/?p=274
permalink: /google-ml-types/
post_views_count:
  - "165"
image: /wp-content/uploads/2019/02/Googleが提供する機械学習モデルの種類について-125x125.png
categories:
  - テクノロジー
---
どうも、<a href="https://twitter.com/iamseninja" target="_blank" rel="nofollow noopener">Yuki Hirai</a>です。

今日は前回の続きで

<span class="sobig"><b>Google Developers ML Summit Tokyo 2018</b></span>

に参加してきた際のメモを書いていきます。

前回の記事はこちらからどうぞ

<blockquote class="wp-embedded-content" data-secret="ENYUvaR2a0">
  <p>
    <a href="https://yabaiwebyasan.com/tensorflow-cloud-ml/">TensorFlow/Cloud ML の概要(機械学習・人口知能の活用例)</a>
  </p>
</blockquote>



## Googleが提供する機械学習モデルの種類

Googleでは以下のようなモデルをそれぞれ用意している。

  * 独自モデル: Cloud Machine Learning Engine/Tensorflow
  * 学習済みモデル: Cloud Vision API
  * 自動モデル構築
  * 学習済みモデルのカスタム化ができるようなもの
  * 学習データだけ用意すれば勝手にモデルを構築してくれるサービス

<a href="https://cloud.google.com/vision/" target="_blank" rel="noopener noreferrer">Cloud Vision</a>はGoogleが訓練したモデルをもとに画像を判別してくれる。

Web Entitiesの項目では  
画像検索の結果から似たような写真がのってるサイトに含まれている重要度がたかそうなキーワードを引っ張ってくる

といったこともしているとのこと。

画像をアップするだけでうまくいけば名前までわかってしまうとかw

他にも学習済みモデルでいうと

<a href="https://cloud.google.com/speech-to-text/" target="_blank" rel="noopener noreferrer">Speech to Text</a>がある。

これは音声をテキストに変換してくれるもので

例えば

「とうきょうとっきょきょきゃきょく」

とかでも

ニューラルネットワークがいい感じに

「東京等特許許可局」

と変換してくれる

<a href="https://cloud.google.com/translate/" target="_blank" rel="noopener noreferrer">Cloud Translation</a>を使用すれば翻訳もできる。

Googleが提供している複数のAPIを組み合わせることで

面白いアプリが作れるようになる。

この<a href="https://quickdraw.withgoogle.com/" target="_blank" rel="noopener noreferrer">Quick Draw</a>というサービスは

お題に対して時間内に手書きでお題を描けるかどうか

というゲームで遊べるサービス。

お題にあった絵かどうかを機械学習で判別しているそう。

## 手動のラベルづけ

**自動モデル構築**の際には、学習データが必要となるが

それを手動でアウトソースできるサービスもGoogleは提供している。

GoogleのAutoML Visionでは  
有料で人間による手動のラベルづけもやってくれる。

5000枚なら1週間程度で出来るとのこと。

<a href="https://cloud.google.com/vision/automl/docs/human-labeling" target="_blank" rel="noopener noreferrer">human-labeling</a>

英文でリクエスト送ればその通りに人がラベルづけしてくれるとのこと

## PR曲線を知ろう

機械学習でモデルを訓練する際は

**PR曲線**

を意識するようにしたい。

PR曲線とは&#8230;  
PrecisionとRecallを用いた評価のこと。

ニューラルネットワークの出力は「確率値」となる。

本当に異常なものの中で、  
正しく以上を発見できた割合  
10の異常なもののうち異常と判断されたものが6 Recall = 60%

異常と判断したものの中で本当に異常だったものの割合  
異常なもの4/16 Precision = 30%

といった風になる。

ビジネスゴールによってどっちかを取捨選択していくことになるので

PR曲線を意識しながらモデルを学習させていく必要がある。

顧客満足度をあげたい場合 => Recallをあげたい  
生産効率をあげたい場合 => Precisionをあげたい

といった感じ。

機械学習をサービスに組み込むとなると

統計的な知識も必要になってくる。

次回:　機械学習ですぐに使えるモデル集/インフラ参考

<blockquote class="wp-embedded-content" data-secret="YRrfvlLgMn">
  <p>
    <a href="https://yabaiwebyasan.com/ml-models-and-infra/">機械学習ですぐに使えるモデル集/インフラ参考</a>
  </p>
</blockquote>