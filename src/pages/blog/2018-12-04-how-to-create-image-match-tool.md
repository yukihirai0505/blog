---
templateKey: blog-post
id: 205
title: 類似画像検索システムを作成する上で知っておきたいワードやツール
date: 2018-12-04T20:02:08+09:00
author: Yuki Hirai
layout: post
guid: https://yabaiwebyasan.com/?p=205
permalink: /how-to-create-image-match-tool/
post_views_count:
  - "1049"
image: /wp-content/uploads/2018/11/how-to-create-image-match-tool-125x125.png
categories:
  - テクノロジー
---
どうも、<a href="https://twitter.com/iamseninja" target="_blank" rel="nofollow noopener">Yuki Hirai</a>です。

先日、「<a href="https://supporterzcolab.com/event/623/" target="_blank">類似画像検索システムを作る</a>」という勉強会に参加してきました。

今日はそこで知った

<span class="sobig"><b>類似画像検索関連のワード・ツール</b></span>

をメモ程度に残していこうと思います。

## pHash(Perceptual Hash)とは

pHashは

**画像などのメディアデータのハッシュを計算するアルゴリズム群**

のことをさします。

つまり、文字をハッシュ化して一意の文字列にするのと同じように  
画像のようなメディアデータを一意の文字列=ハッシュで表現できるようにしているアルゴリズム

といったところでしょうかw

Pythonだと

**pip install imagehash**

で使用できます。

64bitの特徴量が出力されて16進数で表示されます。

誤検出が少ないので

  * 著作権侵害画像検出
  * 重複画像発見

でよく使われているとのことです。

**ハミング距離**

が近い画像を検出できるとのことで

例えば

  * 色が異なる
  * トリミングされている

とかでも検出できるようです。

ハミング距離については以下のリンクが参考になります。

ref: <a href="https://kotobank.jp/word/%E3%83%8F%E3%83%9F%E3%83%B3%E3%82%B0%E8%B7%9D%E9%9B%A2-7458" target="_blank">ハミング距離</a>

pHashを利用した類似度の計算をしている記事があるので

よければ参考にしてみてください。

ref: <a href="https://tech.unifa-e.com/entry/2017/11/27/111546" target="_blank">Perceptual Hashを使って画像の類似度を計算してみる</a>

## TBIRとCBIRについて

画像検索については

  * TBIR (Text-Based Image Retrieval)
  * CBIR（Content Based Image Retrieval）

というものがあります。

TBIRは画像のメタ情報にあるテキストを確認して  
テキスト検索するものです。

対して、CBIRは画像の画素情報から特徴を抽出して検索を行うものです。

詳しくは以下の記事が参考になります。

ref: <a href="http://www.enigmo.co.jp/blog/tech/%E9%A1%9E%E4%BC%BC%E7%94%BB%E5%83%8F%E6%A4%9C%E7%B4%A2%E3%81%AB%E3%81%A4%E3%81%84%E3%81%A6%E3%81%AE%E8%AA%BF%E6%9F%BB%E7%B5%90%E6%9E%9C/" target="_blank">類似画像検索についての調査結果</a>

## 画像の特徴量の抽出について

画像の特徴量を抽出するのに使用されるアルゴリズムはいくつかあります。

  * SIFT (Scale-invariant feature transform)
  * SURF (Speed-Upped Robust Feature)
  * ORB（Oriented-BRIEF）
  * AKAZE( Accelerated KAZE)
  * BRISK

などなど

これらにいては以下の記事でざっくりまとまってました。

ref: <a href="https://qiita.com/shu223/items/fa3cf693296e5641f771" target="_blank">iOS / OpenCV 3.0 で画像の特徴点を検出する（AKAZE, SIFT, SURF, ORB）</a>

他にも

  * <a href="http://www.asahi-net.or.jp/~ax2s-kmtn/ref/histogram.html" target="_blank">カラーヒストグラム</a>
  * <a href="https://qiita.com/tuttieee/items/f55c7e2613862ce123ae" target="_blank">GIST 特徴量</a>
  * <a href="https://jp.techcrunch.com/2018/02/23/2018-02-22-feature-labs-launches-out-of-mit-to-speed-up-building-machine-learning-algorithms/" target="_blank">Deep Feature Synthesis</a>

などのキーワードについても少し触れておくといいかもです。

SHIFTやSURFについては以下のスライドにわかりやすく

まとめられています

ref: <a href="https://www.slideshare.net/lawmn/siftsurf" target="_blank">画像認識の初歩、SIFT,SURF特徴量</a>

## 近似最近傍探索

近似最近傍探索は

検索対象のベクトルからもっとも近いベクトルを検索する技術です。

Faissといったお手軽なツールも存在します。

ref: <a href="https://qiita.com/sugiyamath/items/858a5d60bc93d3f787ba" target="_blank">Facebook Researchのfaissで類似検索</a>

メルカリはこちらのFaissを使用して類似画像検索システムを構築しているようです。

<blockquote class="twitter-tweet" data-width="550" data-dnt="true">
  <p lang="ja" dir="ltr">
    メルカリは類似画像検索システムを構築するにあたって<br />Facebook AI ResearchのFaissを使ってるみたい<br />オープンソースの機械学習ライブラリ🙋‍♂️<a href="https://t.co/gh7sXSNItx">https://t.co/gh7sXSNItx</a>
  </p>
  
  <p>
    &mdash; SEKAI NO HIRAI👨‍💻Programmer (@yabaiwebyasan) <a href="https://twitter.com/iamseninja/status/1069817126620295168?ref_src=twsrc%5Etfw">December 4, 2018</a>
  </p>
</blockquote>



他にもFLANNやAnnoy,NMSLIBなどがあります。

ref: <a href="https://myenigma.hatenablog.com/entry/2016/04/19/214813" target="_blank">高速最近傍点探索ライブラリFLANNを使ってみる</a>  
ref: <a href="https://qiita.com/ta7uwtaka/items/9301eef7dd74a249d5ea" target="_blank">Chainer とAnnoyを使った 類似画像検索 【入門】</a>

このimage-matchというオープンソースライブラリがお手軽に使えるそうです。

ref: <a href="https://github.com/EdjoLabs/image-match" target="_blank">EdjoLabs/image-matc</a>

あと少しインフラ構築に力をいれれば

以下のソースコードが類似画像検索機能の構築の参考になります。

ref: <a href="https://github.com/alexklibisz/elastik-nearest-neighbors" target="_blank">alexklibisz/elastik-nearest-neighbors</a>

画像検索まわりはほぼ未知なので、

新しい発見がたくさんあって楽しかったですw

自分でも簡単にOpenCVを使って類似画像検索ツールをつくったりしてみました。

だれでもお手軽に画像をつかってあれこれできる時代になってきてますね