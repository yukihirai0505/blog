---
templateKey: blog-post
id: 280
title: 機械学習ですぐに使えるモデル集/インフラ参考
date: 2019-02-12T20:56:22+09:00
author: Yuki Hirai
layout: post
guid: https://yabaiwebyasan.com/?p=280
permalink: /ml-models-and-infra/
post_views_count:
  - "195"
image: /wp-content/uploads/2019/02/機械学習ですぐに使えるモデル集-125x125.png
categories:
  - テクノロジー
---
どうも、<a href="https://twitter.com/iamseninja" target="_blank" rel="nofollow noopener">Yuki Hirai</a>です。

今日は前回の続きで

<span class="sobig"><b>Google Developers ML Summit Tokyo 2018</b></span>

に参加してきた際のメモを書いていきます。

前回の記事はこちらからどうぞ

<blockquote class="wp-embedded-content" data-secret="r0Yh1RsdY1">
  <p>
    <a href="https://yabaiwebyasan.com/tensorflow-cloud-ml/">TensorFlow/Cloud ML の概要(機械学習・人口知能の活用例)</a>
  </p>
</blockquote>



## 機械学習はモデルの選定にセンスが必要

機械学習のモデルを一から構築できる専門家が少ないため

Googleでは

**AI(機械学習)の民主化がミッション**

となっている。

Googleを活用すれば  
機械学習モデル開発のライフサイクルはざっくり以下のような流れになる。

  1. 機械学習モデルの選定
  2. 機械学習モデルのカスタマイズ
  3. カスタムモデルの保守運用

1->2->3->2->1のサイクルを繰り返して開発していく。

特に1のモデルの選定にセンスが必要とされる。

様々な業界で様々な目的のために機械学習が使われていく。

  * 製造業 予測メンテナンス
  * 小売業 売り場での商品検索効率化
  * ヘルスケア 医療画像からの症状分析
  * メディア&エンターテイメント メディアコンテンツの検索性向上

目的に応じたモデルの選定が重要となる

## 機械学習ですぐ使えるサンプル・モデル集

TensorFlowが2015年にオープンソースとして世に公開されてから

様々な人々が独自に訓練したモデルのデータをオープンに公開していたりする。

そういったモデルをつかえば簡単に機械学習の恩恵を授かることができる。

以下のリンク集が役立つかも

  * <a href="https://ai.googleblog.com/" target="_blank" rel="noopener noreferrer">Google AI Blog</a>
  * <a href="https://www.kaggle.com/" target="_blank" rel="noopener noreferrer">Kaggle</a>
  * <a href="http://arXiv.org " target="_blank" rel="noopener noreferrer">http://arXiv.org </a>
  * <a href="https://cloud.google.com/whitepapers/" target="_blank" rel="noopener noreferrer">Google Cloud WHITEPAPERS</a>
  * <a href="https://cloud.google.com/ai-hub/" target="_blank" rel="noopener noreferrer">AI Hub(alpha)</a>
  * <a href="https://book.mynavi.jp/manatee/series/detail/id=65670" target="_blank" rel="noopener noreferrer">機械学習で遊ぼう! APIサービスやTensorFlowを使ったサンプルレシピ集</a>
  * <a href="https://kamujun.hatenablog.com/entry/2018/08/10/183201" target="_blank" rel="noopener noreferrer">Googleの事前学習済みモデルを手軽に利用出来るTensorFlow Hub</a>

なかでもAI Hubはワンストップカタログになろうとしているとのこと。  
今後はここにくれば期待しているモデルがみつかる、くらいにしたいとのことだ。

## 機械学習を学習する上で便利なツール

**Colaboratory**はとても便利。

1日を超える長時間のトレーニングはできないが  
オンラインである程度強力な機械学習の学習ができる。

またColaboratoryはローカルのRuntimeに接続することができる。  
Colaboratoryのフロントはそのまま使ってバックエンドを別に用意することができる。

Cloud Deep Learning VM Image(beta)も便利。  
GCEインスタンスで利用できるディープラーニング用イメージ。

  1. 有名な機械学習フレームワークが導入済み
  2. 設定が不要
  3. JupyterLabで開発時の試行錯誤にかかる時間を大幅に短縮

といったように前準備がほとんどいらない状態でインスタンスを利用できる。

=> <a href="https://cloud.google.com/deep-learning-vm/" target="_blank" rel="noopener noreferrer">https://cloud.google.com/deep-learning-vm/</a>

Google社内で利用されている機械学習プラットフォームとして

<a href="https://www.tensorflow.org/tfx/" target="_blank" rel="noopener noreferrer">https://www.tensorflow.org/tfx/</a>

がある。  
これを一般でも使えるようにしたのがKubeflow Pipeline。

機械学習パイプラインの作成・実行・管理、そしてモジュールの再利用が簡単にできるよういんある。

機械学習パイプラインの定期実行  
機械学習モデルの性能比較も簡単にできる優れもの。

デプロイ判断が迅速化する。

  * <a href="https://github.com/kubeflow/pipelines" target="_blank" rel="noopener noreferrer">pipelines</a>
  * <a href="https://github.com/dmlc/xgboost" target="_blank" rel="noopener noreferrer">xgboost</a>
  * <a href="https://github.com/TensorLab/tensorfx" target="_blank" rel="noopener noreferrer">TensorFX</a>

機械学習のインフラ周りを整備する際はぜひ使用したい。