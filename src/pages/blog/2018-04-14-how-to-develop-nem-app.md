---
templateKey: blog-post
id: 90
title: ネム(NEM)のアプリケーション開発の始め方
date: 2018-04-14T14:43:25+09:00
author: Yuki Hirai
layout: post
guid: https://yabaiwebyasan.com/?p=90
permalink: /how-to-develop-nem-app/
post_views_count:
  - "671"
image: /wp-content/uploads/2018/11/how-to-develop-nem-app-125x125.png
categories:
  - テクノロジー
---
どうも、絶賛ささみばっかり食べるダイエット中の<a href="https://twitter.com/iamseninja" target="_blank" rel="nofollow noopener">Yuki Hirai</a>です。

今日は

<span class="big"><b>ネム(NEM)のアプリケーション開発の始め方</b></span>

について書いていきます

ちなみに先日、ネム(NEM)の勉強会に参加してきました。

そのときの資料が参考になります。

<span class="sankou">参考</span> <a href="https://drive.google.com/file/d/1m_328StAyJ4-2cAqe-6DjmAuALXh7cGe/view" target="_blank" rel="nofollow noopener">ブロックチェーン:NEMを学ぼう</a>

## そもそもネム(NEM)とは？ネム(NEM)ってなに？

ネム(NEM)は

<span class="sobig"><b>New Economic Movement</b></span>

を由来としていて、

<span class="sobig"><b>新しい経済活動の構築</b></span>

を目的とする暗号通貨です

もともとは、ビットコイン2.0のひとつである<a href="https://jpbitcoin.com/bitcoin2/nxtcoin" target="_blank" rel="nofollow noopener">Nxt</a>の改良プロジェクトとして位置付けられて2014年から始まりました。

ビットコインはもともとP2Pでの決済を目的として作られたデジタル通貨なんですが

ここで使われてる技術が<span class="big">ブロックチェーン技術</span>と呼ばれ

このビットコインのブロックチェーンを通貨以外に活用するような技術のこと「ビットコイン2.0」って呼びます。

ブロックチェーンの技術をうまく応用して、  
**独自通貨の発行**であったり**メッセージの送信**、**投票**なんかの機能を提供するプラットフォームとしてできたのが<a href="https://jpbitcoin.com/bitcoin2/nxtcoin" target="_blank" rel="nofollow noopener">Nxt</a>です。

この<a href="https://jpbitcoin.com/bitcoin2/nxtcoin" target="_blank" rel="nofollow noopener">Nxt</a>は**Proof of Stake(PoS)**っていうアルゴリズムを採用してて  
ネム(NEM)では**Proof of Stake(PoS)**を改良した

<span class="sobig"><b>Proof of Importance(PoI)</b></span>

っていうアルゴリズムを実現することを目指してます

簡単に**Proof of Importance(PoI)**について説明しておくと

<span class="big"><b>長期間保持するほど重要度が下がり</b></span>

<span class="big"><b>コインを多く利用するほど重要度があがる仕組み</b></span>

みたいなロジックです

<span class="big"><b>コインの流動性を高めて富の偏りを防ぐ</b></span>

といったことを実現したいなどの独自のアイデアがあります

<span class="big"><b>貧富の格差が広がることを防ごうとしている</b></span>

暗号通貨です

ネム(NEM)のソースコードの一部はすでに公開されていて  
ゆくゆくはOSSとして全部公開していくようにするとのことです

> NEMのソースコードも一部はnem.coreとして公開されており 

<blockquote class="twitter-tweet" data-width="550" data-dnt="true">
  <p lang="ja" dir="ltr">
    ご存知だったらごめんなさい。<br />NEMのソースコードも一部はnem.coreとして公開されており<a href="https://t.co/xiqRkna6O8">https://t.co/xiqRkna6O8</a><br />改善のためのプルリクエストも可能です。
  </p>
  
  <p>
    現在カタパルトというコードネームのプロジェクトが進行しており、その公開とともに順次オープンソースにするとアナウンスされています。
  </p>
  
  <p>
    &mdash; XEMBook (@xembook) <a href="https://twitter.com/xembook/status/973753378311303173?ref_src=twsrc%5Etfw">March 14, 2018</a>
  </p>
</blockquote>



▶︎ <a href="https://github.com/NemProject/nem.core" target="_blank" rel="nofollow noopener">NemProject/nem.core</a>

英語ですが動画での紹介もあります

<span class="embed-youtube" style="text-align:center; display: block;"></span>

通貨名は**XEM(ゼム)**で国内の取引所だと<a href="https://zaif.jp?ac=kv0eo8m3w2" target="_blank" rel="nofollow noopener">Zaif(ザイフ)</a>や<a href="https://coincheck.com/?c=yU_pr0rsOKI" target="_blank" rel="noopener">Coincheck(コインチェック)</a>で購入することができます

## ネム(NEM)で出来ること

まずネム(NEM)で出来ることをざっくりこの3つとりあげて説明します

<div class="sng-box box31">
  <div class="box-title">
    NEMの特徴
  </div>
  
  <div class="ol-circle li-mainbdr main-bc-before">
    <ol>
      <li>
        モザイクと呼ばれる独自通貨の発行
      </li>
      <li>
        マルチシグ
      </li>
      <li>
        NEM Apostille Serviceと呼ばれる公証機能
      </li>
    </ol>
  </div>
</div>

ネム(NEM)でアプリケーションを作成したい場合は、  
上記についてざっくり知っておくとアプリケーション開発に役立ちます。

簡単にそれぞれ説明していきます

### モザイクと呼ばれる独自通貨の発行

ネム(NEM)では<a href="https://nem.io/downloads/" target="_blank" rel="nofollow noopener">Nano Wallet(ナノウォレット)</a>を使用することで  
プログラミングの知識なしに独自通貨を発行することができます

モザイクの発行者は

<div class="sng-box box31">
  <div class="box-title">
    モザイクについて
  </div>
  
  <div class="ol-circle li-mainbdr main-bc-before">
    <ol>
      <li>
        モザイクの送金に手数料を設定して徴収
      </li>
      <li>
        モザイクを第三者間で取引することを制限する
      </li>
    </ol>
  </div>
</div>

などの設定もできます。

これをプログラミングなしでぽちぽち設定して作れちゃうのは  
かなり魅力的ですね。

### マルチシグ

マルチシグっていうのはめちゃ簡単に言えば

<span class="big"><b>送金するのに複数の秘密鍵が必要になる</b></span>

っていう仕組みです

NEM(ネム)ではこのマルチシグっていう機能を取り入れてます

詳しくは以下の記事が参考になります

▶︎ <a href="http://vtuka.jp/maltishigu" target="_blank" rel="nofollow noopener">NEM（ネム）マルチシグ設定方法と落とし穴｜xemを安全に保管する</a>

### NEM Apostille Service(ネムアポスティーユサービス)と呼ばれる公証機能

このNEM Apostille Service(ネムアポスティーユサービス)っていうのは

<span class="big"><b>任意のデジタルデータの存在証明や正当性の保証をブロックチェーンにより実現</b></span>

する仕組みです

要するにデジタルなデータ(ファイルや画像など)がちゃんと不正な改ざんを受けないように  
存在しているかどうかをチェックする仕組みがあります

これがうまく応用できれば  
国や特定の期間に依存することなく非中央集権的に不動産登記や戸籍登録なんかを証明することができます

ネム(NEM)についてもっと知りたい！  
っていう人は下の記事で詳しく紹介さてます

▶︎ <a href="https://ja.wikipedia.org/wiki/NEM_(%E6%9A%97%E5%8F%B7%E9%80%9A%E8%B2%A8)" target="_blank" rel="nofollow noopener">NEM (暗号通貨)</a>

## ネム(NEM)でWEBアプリケーションを開発！参考になるドキュメントも紹介！

ネム(NEM)はプロトコルベースでアプリケーション開発を行うことができます

ネムはアプリケーション開発のために

<span class="sobig"><b>独自のAPI</b></span>

を提供してくれてて

開発者は目的に応じて

<span class="sobig"><b>APIのエンドポイントを叩くだけ</b></span>

でアプリが作れてしまいます

<span class="big"><b>特定のプログラミング言語に依存しなくても開発できちゃう</b></span>

っていうのはかなりハードルが低いですね

イーサリアム(Ethereum)も同じようにブロックチェーン技術を使用した  
プログラムを実装することができますが

イーサリアム(Ethereum)の場合は

<span class="sobig"><b>Solidity</b></span>

っていう独自のプログラミング言語

を使用して開発します

イーサリアム(Ethereum)の場合、  
自分で実装したプログラムをイーサリアム(Ethereum)のプロックチェーンに取り込んでもらって  
ようやく実行可能になりますが

ネム(NEM)の場合は

<span class="sobig"><b>アプリケーションサーバー</b></span>

は自分で用意する必要があります

### ネム(NEM)のアプリケーション開発で参考になるドキュメント・ツール

まず、開発する際は一通り以下のドキュメントに目を通すとよいです。

<div class="sng-box box31">
  <div class="box-title">
    NEMの参考ドキュメント
  </div>
  
  <div class="ol-circle li-mainbdr main-bc-before">
    <ol>
      <li>
        <a href="https://nemproject.github.io/" target="_blank" rel="nofollow noopener">NEM NIS API Documentation(英語)</a>
      </li>
      <li>
        <a href="https://www.pr1sm.com/crypto-coin/nem-nis-api-documentation-in-japanese/" target="_blank" rel="nofollow noopener">New Economy Movement(NEM) APIマニュアル和訳</a>
      </li>
    </ol>
  </div>
</div>

実際の開発にはNode.jsのSDKが用意されていて  
これを使えばスムーズに開発できます

SDK: <a href="https://github.com/QuantumMechanics/NEM-sdk" target="_blank" rel="nofollow noopener">QuantumMechanics/NEM-sdk</a>

また、<a href="https://nem.io/downloads/" target="_blank" rel="nofollow noopener">Nano Wallet(ナノウォレット)</a>を使用して  
テストネットでの動作確認テストなんかもできるので  
ダウンロードしておくようにすると開発がスムーズです

詳しいやり方なんかは以下の記事が参考になります

▶︎ <a href="https://wakuwaku-currency.com/virtual-currency/nem/test-faucet-coin.html" target="_blank" rel="nofollow noopener">NEMのテストネットワークで独自通貨を試す</a>

## ネム(NEM)のグローバルハッカソン！ネムアプリを作るときに参考になるソースコード

ちなみに、ネム(NEM)は

<span class="sobig"><b>NEM Global Hackathon(ネムグローバルハッカソン)</b></span>

を開催していて

そこにいろんなサービスの応募がありました

応募サービスは以下のURLからみることができます

▶︎ <a href="https://hackathon.nem.io/app-submission/" target="_blank" rel="nofollow noopener">Qualifiers Archive &#8211; NEM Global Hackathon</a>

例えば**SOCIALCAKE**は

> アーティスト、ミュージシャン、作家、そしてあらゆる種類のコンテンツ制作者が、  
> いつも共有していたどこにいても、ファンに直接コンテンツを簡単に販売できるようにする。 

といった内容です。

<span class="embed-youtube" style="text-align:center; display: block;"></span>

で、なんとこれらの応募作品はオープンソースで開発されてるから  
そのコードをアプリケーション開発するときに参考にすることができます

例えばSOCIALCAKEの場合だとソースコードは以下のリンクに公開されてます

▶︎ <a href="https://github.com/SocialCake/SocialCake" target="_blank" rel="nofollow noopener">SocialCake/SocialCake </a>

## ネム(NEM)のアプリケーション開発の始め方

以上、ざっくりですが  
**ネム(NEM)のアプリケーション開発の始め方**についてまとめると

<div class="sng-box box31">
  <div class="box-title">
    まとめ
  </div>
  
  <div class="ol-circle li-mainbdr main-bc-before">
    <ol>
      <li>
        APIの仕様書を読む
      </li>
      <li>
        実際にNANOWalletを触ってテストネットで動かしてみる
      </li>
      <li>
        グローバルハッカソンの応募サービスのソースコードを読んで参考にしてみる
      </li>
    </ol>
  </div>
</div>

っていう流れが個人的にはいいんじゃないかなぁ！って思ってます