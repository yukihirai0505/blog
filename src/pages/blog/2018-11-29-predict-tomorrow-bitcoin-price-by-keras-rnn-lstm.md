---
templateKey: blog-post
id: 176
title: Keras(ケラス)のRNN-LSTMを使用して明日のビットコイン価格を予想する
date: 2018-11-29T20:24:18+09:00
author: Yuki Hirai
layout: post
guid: https://yabaiwebyasan.com/?p=176
permalink: /predict-tomorrow-bitcoin-price-by-keras-rnn-lstm/
post_views_count:
  - "1344"
image: /wp-content/uploads/2018/11/predict-tomorrow-bitcoin-price-125x125.png
categories:
  - テクノロジー
---
どうも！最近、機械学習について学ぶのにハマってる<a href="https://twitter.com/yabaiwebyasan" target="_blank" rel="nofollow noopener">Yuki Hirai</a>です。

今日ははじめてKeras(ケラス)のRNN-LSTMを使用して

時系列データの将来予測をやってみたので

簡単に勉強したことをメモしておこうかと思います。

  * Keras(ケラス)
  * RNN
  * LSTM

↑機械学習やったことない人からすればなんのこっちゃって単語ですねw

## Keras(ケラス)とは

Keras(ケラス)は簡単にデープラーニング処理ができるようにつくられた  
機械学習ライブラリです。

機械学習に詳しくない人でも  
少ないコード量で機械学習を活用することができます。

Kerasを使用すれば  
難しい数学的理論の部分を自分で実装する必要がなくなります。

参考①: <a href="https://products.sint.co.jp/aisia/blog/vol1-3" target="_blank">機械学習のライブラリ (Vol.3)</a>  
参考②: <a href="https://udemy.benesse.co.jp/ai/keras.html" target="_blank">【入門者でもわかる】Kerasとは？基礎から丁寧に解説！</a>

例えば、Kerasを利用すれば

  * 文章の自動生成
  * 画像認識

などを簡単に実装することができます。

## RNNとは

**&#8220;RNN&#8221;**は正式名称を**&#8220;Recurrent Neural Network&#8221;**といいます。

RNNは時系列データの予測で  
よく使用されるディープランニングの代表的手法です。

過去の時系列データをもとに未来のデータを予測するときに使われます。

詳しくは以下の記事が参考になります。

参考: <a href="https://deepinsider.jp/tutor/introtensorflow/whatisrnn" target="_blank">RNN（Recurrent Neural Network）の概要を理解しよう（TensorFlow編）</a>

## LSTMとは

**&#8220;Long short-term memory&#8221;**を略して**&#8220;LSTM&#8221;**といいます。

LSTMはRNNの拡張として登場しました。

RNNは長時間前のデータを利用しようとするとうまく機能しない  
場合があるので短時間のデータ処理に向いています。

LSTMはRNNでは学習できなかった長期の時系列データ(long-term dependencies)を学習することができます。

参考①: <a href="https://qiita.com/t_Signull/items/21b82be280b46f467d1b" target="_blank">わかるLSTM ～ 最近の動向と共に</a>  
参考②: <a href="http://gagbot.net/machine-learning/ml4" target="_blank">やさしい深層学習の原</a>

## 機械学習の簡単な流れについて

さて、今回使用するツールについて簡単に説明しましたが

もうひとつ

**機械学習の流れ**

について整理しておきます。

なにをやりたいのかにもよりますが

大雑把にこんな感じになります

  * データ収集
  * データクレンジング(データの重複や欠損データなどを取り除く)
  * アルゴリズムの選択
  * 機械学習とチューニング
  * サービス化

これらは機械学習の区分(教師あり学習や教師なし学習、強化学習)によって  
多少フローに変化があるかもしれません。

また、目的によって選択するアルゴリズムは変わってきます。

  * 分類 ex) テキストのカテゴリ分類がしたい, ある画像が犬か猫かに分類したい etc
  * 回帰 ex) 過去のデータから今後のレポートの数値の予測をしたい, 株価を予測したい etc

といった具合です。

この流れを把握しておけば、  
他の人が書いてる機械学習関連の記事も

「あ、この部分はこのフェーズのことを書いてるんだな」

と意識しながら読んでいくことができるので

すんなり中身を理解しやすくなります。

## KerasのRNN-LSTMを使用してビットコイン価格を予想してみる

今回、

機械学習を使用したビットコインの価格予測プログラムを実装するのに

こちらの記事を参考にしました。

参考①: <a href="https://medium.com/@siavash_37715/how-to-predict-bitcoin-and-ethereum-price-with-rnn-lstm-in-keras-a6d8ee8a5109" target="_blank">How to predict Bitcoin and Ethereum price with RNN-LSTM in Keras</a>  
参考②: <a href="https://www.creationline.com/lab/dataanalytics/20922" target="_blank">ディープラーニングでBitcoinの価格を予測して見る #Deep Learning #Keras</a>  
参考③: <a href="https://towardsdatascience.com/using-recurrent-neural-networks-to-predict-bitcoin-btc-prices-c4ff70f9f3e4" target="_blank">Predict Tomorrow’s Bitcoin (BTC) Price with Recurrent Neural Networks</a>

実際につくってみて試した結果はこのような感じですw

<blockquote class="twitter-tweet" data-width="550" data-dnt="true">
  <p lang="ja" dir="ltr">
    そういえば昨日、ビットコインの時系列データをもとにKerasでLSTMつかってモデルを構築後<br />今日のビットコイン価格予想やってみたんだけど
  </p>
  
  <p>
    そのとき<br />$4,028って出てきて
  </p>
  
  <p>
    いま$3,690だから<br />何もしなくてよかったって思ってる😂
  </p>
  
  <p>
    せっかく作ったから延々と明日の価格を予想し続けるボットにしようかなw
  </p>
  
  <p>
    &mdash; SEKAI NO HIRAI👨‍💻Programmer (@yabaiwebyasan) <a href="https://twitter.com/yabaiwebyasan/status/1067418266316955650?ref_src=twsrc%5Etfw">November 27, 2018</a>
  </p>
</blockquote>



個人的には3つめに参考にしたこちらの記事が非常にわかりやすかったです。

<a href="https://towardsdatascience.com/using-recurrent-neural-networks-to-predict-bitcoin-btc-prices-c4ff70f9f3e4" target="_blank">Predict Tomorrow’s Bitcoin (BTC) Price with Recurrent Neural Networks</a>

ソースコードはほぼそのまま使用しているので  
よければお試しくださいw