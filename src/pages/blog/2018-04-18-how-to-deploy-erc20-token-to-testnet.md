---
templateKey: blog-post
id: 96
title: イーサリアム(Ethereum)で独自トークンを作ってテストネットにデプロイするまで
date: 2018-04-18T14:52:09+09:00
author: Yuki Hirai
layout: post
guid: https://yabaiwebyasan.com/?p=96
permalink: /how-to-deploy-erc20-token-to-testnet/
post_views_count:
  - "349"
image: /wp-content/uploads/2018/04/etherum-testnet-deploy-125x125.png
categories:
  - テクノロジー
---
どうも、仮想通貨はすべて損切りした<a href="https://twitter.com/iamseninja" target="_blank" rel="nofollow noopener">Yuki Hirai</a>です。

今日は

<span class="big"><b>イーサリアム(Ethereum)で独自トークンを作成</b></span>して

<span class="big"><b>テストネットにデプロイするまでの流れ</b></span>

ついて書いていきます

簡単に説明しておくとイーサリアムは

<span class="big"><b>通貨ではなく、プログラム(スマートコントラクト)をブロックチェーン上で動作させるためのプラットフォーム</b></span>

のことです

誰でもイーサリアム(Ethereum)の独自のプログラミング言語である

**Solidity**

を用いてプログラムを書けば

それをイーサリアム(Ethereum)のブロックチェーンに取り込むことで

誰でもそのプログラムを実行できるようになります

ちなみに先日説明したネム(NEM)は書いたプログラムを

ブロックに取り込む必要がないのはイーサリアム(Ethereum)と大きくことなるところです

ネム(NEM)の開発について知りたい人は

下のリンクから記事読んでみてください

<blockquote class="wp-embedded-content" data-secret="gKF3Or1IHW">
  <p>
    <a href="https://yabaiwebyasan.com/how-to-develop-nem-app/">ネム(NEM)のアプリケーション開発の始め方</a>
  </p>
</blockquote>



## イーサリアム(Ethereum)の開発で参考になるドキュメント

まず、最初に**イーサリアム(Ethereum)の開発で参考になるドキュメント**について説明します  
定番はイーサリアム(Ethereum)の公式サイトです

▶︎ <a href="https://ethereum.org/" target="_blank" rel="nofollow noopener">https://ethereum.org/</a>

で、次に参考になるのはこのWebthereum(ウェブサリアム)と呼ばれるページです

▶︎ <a href="https://happyfuncorp.com/whitepapers/webthereum" target="_blank" rel="nofollow noopener">WEBTHEREUM</a>

これは以下の記事にもあるとおり、  
WEBプログラマーのために作られた**Ethereumプログラミング入門**ページです

▶︎ <a href="https://jp.techcrunch.com/2018/01/16/2018-01-15-a-modest-proposal-for-ethereum-programming/" target="_blank" rel="nofollow noopener">WebプログラマーのためのEthereumプログラミング入門</a>

ただ英語で書かれてるから、英語に抵抗のある人には以下の本が圧倒的におすすめです

<a target="_blank"  href="https://www.amazon.co.jp/gp/product/4839965137/ref=as_li_tl?ie=UTF8&#038;camp=247&#038;creative=1211&#038;creativeASIN=4839965137&#038;linkCode=as2&#038;tag=yabaiwebya0b7-22&#038;linkId=e503fdf7b02cbb3512eaab494f89c152"><img border="0" src="//ws-fe.amazon-adsystem.com/widgets/q?_encoding=UTF8&#038;MarketPlace=JP&#038;ASIN=4839965137&#038;ServiceVersion=20070822&#038;ID=AsinImage&#038;WS=1&#038;Format=_SL250_&#038;tag=yabaiwebya0b7-22" /></a><img src="//ir-jp.amazon-adsystem.com/e/ir?t=yabaiwebya0b7-22&#038;l=am2&#038;o=9&#038;a=4839965137" width="1" height="1" border="0" alt="" style="border:none !important; margin:0px !important;" />

<a target="_blank" href="https://www.amazon.co.jp/gp/product/4839965137/ref=as_li_tl?ie=UTF8&#038;camp=247&#038;creative=1211&#038;creativeASIN=4839965137&#038;linkCode=as2&#038;tag=yabaiwebya0b7-22&#038;linkId=c94b390fa2a08b92ef3355d0d689ea66">ブロックチェーンアプリケーション開発の教科書</a><img src="//ir-jp.amazon-adsystem.com/e/ir?t=yabaiwebya0b7-22&#038;l=am2&#038;o=9&#038;a=4839965137" width="1" height="1" border="0" alt="" style="border:none !important; margin:0px !important;" />

これ読めば、普通にWEBプログラミングやってきてる人なら

<span class="big"><b>独自トークンの実装</b></span>と

<span class="big"><b>トークンのテストネットへのデプロイ</b></span>

までが比較的スムーズにできるようになります

この記事ではテストネットへのデプロイまでの手順をざっくり説明していきます

## 独自トークン作成の手順

まずは、ERC20に準拠したトークンを実装する必要があります

ERC20っていうのは

<span class="sobig"><b>イーサリアム上のトークンを標準化する仕様の20番目</b></span>

のことをいいます。

以下のページで実装に必要な仕様を知ることが出来るます

▶︎ <a href="https://theethereum.wiki/w/index.php/ERC20_Token_Standard" target="_blank" rel="nofollow noopener">ERC20 Token Standard</a>

この仕様書にも書いてありますが

以下のメソッドとイベントをそれぞれ実装する必要があります

**実装するメソッド**

> function totalSupply() public constant returns (uint);  
> function balanceOf(address tokenOwner) public constant returns (uint balance);  
> function allowance(address tokenOwner, address spender) public constant returns (uint remaining);  
> function transfer(address to, uint tokens) public returns (bool success);  
> function approve(address spender, uint tokens) public returns (bool success);  
> function transferFrom(address from, address to, uint tokens) public returns (bool success); 

**実装するイベント**

> event Transfer(address indexed from, address indexed to, uint tokens);  
> event Approval(address indexed tokenOwner, address indexed spender, uint tokens); 

ちなみに、ローカルで開発するときはプライベートネットを使用するのが一般的です

プライベートネットは**Geth**を使用するのが簡単です

インストール方法や使用方法は以下のページが参考になります

▶︎ <a href="https://book.ethereum-jp.net/first_use/installing_geth.html" target="_blank" rel="nofollow noopener">Gethをインストールする。</a>

この「<a href="https://book.ethereum-jp.net/first_use/" target="_blank" rel="nofollow noopener">まずはEthereumに触れてみる</a>」を一通りやってみると

Gethの簡単な使用方法がつかめます

スマートコントラクトの実装からデプロイに関してはTruffle(トリュフ)っていうフレームワークを使用します

Truffleの使用方法については以下のページを参考になります

▶︎ <a href="https://qiita.com/toshikase/items/d313b7c28bf16b940b12" target="_blank" rel="nofollow noopener">Truffle チュートリアル</a>

トークンの実装には以下の記事が参考になります

▶︎ <a href="https://qiita.com/kyrieleison/items/a5c049097c165cd792bf" target="_blank" rel="nofollow noopener">ERC-20 Token Standard に準拠した独自トークンを自前実装する</a>

## ERC20トークンをテストネットへのデプロイ

ERC20トークンが実装できたら、次はテストネットへのデプロイです。

実際にテストネットにデプロイすることでMetaMaskを使用して

メインネット(本番環境)と同じような環境で動作テストをすることができるようになります

ちなみにMetaMaskは**Google Chrome**で利用できる

**イーサリアム(Ethereum)のウォレット**のことです

以下のリンクからインストールできます

▶︎ <a href="https://chrome.google.com/webstore/detail/metamask/nkbihfbeogaeaoehlefnkodbefgpgknn" target="_blank" rel="nofollow noopener">MetaMaskのインストール</a>

テストネットにはいくつか種類があって

以下のものがあげられます

<div class="sng-box box31">
  <div class="box-title">
    テストネットの種類
  </div>
  
  <div class="ol-circle li-mainbdr main-bc-before">
    <ol>
      <li>
        Ropsten
      </li>
      <li>
        Kovan
      </li>
      <li>
        Rinkeby
      </li>
    </ol>
  </div>
</div>

自分は**Ropsten**をデプロイ先に選びました

ちなみにこれらはそれぞれコンセンサスアルゴリズムが違ってて

Ropstenの場合はビットコインと同じ

**Proof of Work**を採用してます

実際に、Truffle(トリュフ)で作成してERC20に準拠したトークンを

Ropstenにデプロイするのに以下の記事が参考になります

▶︎ <a href="https://tech.pepabo.com/2017/12/06/erc20-token-on-ropsten/" target="_blank" rel="nofollow noopener">Ropstenのテストネット上でERC20トークンを作成・送付してみる</a>

このリンク先にもあるけど、

テストネットへのデプロイをするときは**Infura(インフラ)**っていうサービスを使用すると

ローカル開発環境に大きな負荷をかけることなく

簡単にデプロイすることができるようになります

▶︎ <a href="https://infura.io/" target="_blank" rel="nofollow noopener">https://infura.io/</a>

## ブロックチェーンアプリケーション開発の教科書を読むのが一番早い

今回は、**イーサリアム(Ethereum)で独自トークンを作成**して  
**テストネットにデプロイするまでの流れ**について簡単に説明してみました

まとめるとこんな感じです

<div class="sng-box box31">
  <div class="box-title">
    テストネットデプロイの流れ
  </div>
  
  <div class="ol-circle li-mainbdr main-bc-before">
    <ol>
      <li>
        ERC20準拠トークンを実装する
      </li>
      <li>
        Infura(インフラ)を使用してRopstenにデプロイする
      </li>
    </ol>
  </div>
</div>

イーサリアム(Ethereum)はプログラムの実装からデプロイまでのツールが

<span class="sobig"><b>かなり充実している</b></span>

っていう印象を感じました

実際、自分もそんなにつまづくことなく独自トークンの実装からテストネットへの

デプロイまでやることができました

もっと深く知りたい人は最初に紹介した公式ページや、Webthereumのドキュメントを読みましょう

でも、一番おすすめなのはこの本です

この本はイーサリアム(Ethereum)で

独自トークンを実装してデプロイするだけでなく

ビットコインの仕組みやいままでの歴史、

その背景などを深く体系的に知ることができる本です！

分厚いけど読むに値する名書です