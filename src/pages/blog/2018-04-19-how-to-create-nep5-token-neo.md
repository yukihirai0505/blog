---
templateKey: blog-post
id: 102
title: NEO(ネオ・ニオ)でNEP5に準拠した独自トークンを実装する方法
date: 2018-04-19T15:08:55+09:00
author: Yuki Hirai
layout: post
guid: https://yabaiwebyasan.com/?p=102
permalink: /how-to-create-nep5-token-neo/
post_views_count:
  - "305"
image: /wp-content/uploads/2018/11/how-to-create-nep5-token-neo-125x125.png
categories:
  - テクノロジー
---
どうも、 エンジニア向けの記事もちょくちょく書いている<a href="https://twitter.com/iamseninja" target="_blank" rel="nofollow noopener">Yuki Hirai</a>です。

今日は

<span class="big"><b>NEO(ネオ/ニオ)でNEP5に準拠した独自トークンを実装する手順</b></span>

について書いていきます

## NEO(ネオ/ニオ)とは？

まず、**NEO(ネオ/ニオ)**について簡単に説明します

ちなみに、日本人はNEOのことを**&#8220;ネオ&#8221;**と発音してるけど

海外の人は

<span class="sobig"><b>&#8220;ニオ&#8221;</b></span>

って発音してます

日本では間違った発音で広まっちゃってるから

<span class="big"><b>&#8220;ニオ&#8221;って呼ぶと玄人感がでます！←</b></span>

このNEOは

<span class="sobig"><b>中国版イーサリアム</b></span>

なんて呼ばれていて

中国を中心に開発が進められてる

<span class="big"><b>スマートコントラクトのプラットフォーム</b></span>

のことを指します。

NEOを使用して独自トークン・dAppsの実装ができます。

イーサリアムの独自トークン実装については以前  
別の記事で書いてます

<blockquote class="wp-embedded-content" data-secret="IU5DkxygRY">
  <p>
    <a href="https://yabaiwebyasan.com/how-to-deploy-erc20-token-to-testnet/">イーサリアム(Ethereum)で独自トークンを作ってテストネットにデプロイするまで</a>
  </p>
</blockquote>



イーサリアムの開発には専用のプログラミング言語である

**Solidity**

っていう言語を勉強する必要がありますが

NEO(ネオ)は特定のプログラミングに依存せずに開発できる環境を整えていっていて

いまだと以下の言語のサポートが比較的充実してます

<div class="sng-box box31">
  <div class="box-title">
    サポート言語
  </div>
  
  <div class="ol-circle li-mainbdr main-bc-before">
    <ol>
      <li>
        .NET
      </li>
      <li>
        Java
      </li>
      <li>
        Kotlin
      </li>
      <li>
        VB
      </li>
      <li>
        Javascript
      </li>
      <li>
        TypeScript
      </li>
      <li>
        Python
      </li>
      <li>
        Go
      </li>
    </ol>
  </div>
</div>

なかでもいまは**C#**の開発環境が充実してるっていう印象を受けました

JavaやPythonの対応も進んできてるけど  
他の言語はまだまだこれからサポートされていく！って感じです

ちなみに、NEOのdAppsは以下のサイトから確認できるよー！

▶︎ <a href="http://ndapp.org/" target="_blank" rel="nofollow noopener">NEO dApp List</a>

## NEP5に準拠したトークンの実装

NEOで独自トークンを実装するときは

**NEP5**に準拠したトークンを実装する必要があります

**NEP5**っていうのはトークンを標準化するための仕様のことで

イーサリアムでいう**ERC**のようなものです

5番目の仕様だからNEP5といいます

現時点ではこれがスタンダードのようです

詳しい内容は以下のリンクからみれます

▶︎ <a href="https://github.com/neo-project/proposals/blob/master/nep-5.mediawiki" target="_blank" rel="nofollow noopener">nep-5.mediawiki</a>

ざっくり以下を実装する必要があります

これらは<span class="big"><b>必ず実装しなければいけない</b></span>メソッドです

<div class="sng-box box31">
  <div class="box-title">
    NEP5トークン
  </div>
  
  <div class="ol-circle li-mainbdr main-bc-before">
    <ol>
      <li>
        totalSupply: 合計供給量
      </li>
      <li>
        name: トークン名
      </li>
      <li>
        symbol: トークンのシンボル
      </li>
      <li>
        decimals: トークンの桁数
      </li>
      <li>
        balanceOf: アカウントの残高を返す
      </li>
      <li>
        transfer: 送金メソッド
      </li>
    </ol>
  </div>
</div>

他にも任意で実装するメソッドもいくつか用意されてます

<div class="sng-box box31">
  <div class="box-title">
    任意で実装できるメソッド
  </div>
  
  <div class="ol-circle li-mainbdr main-bc-before">
    <ol>
      <li>
        allowance
      </li>
      <li>
        transferFrom
      </li>
      <li>
        approve
      </li>
    </ol>
  </div>
</div>

これらを実装してブロックチェーンにプログラムをアップすることで

NEOバーチャルマシン(VM)でプログラムが動作するようになります

開発環境の設定は以下のリンクを参考にすればうまくいくかとおもいます

C#の開発環境が一番整備されてるから

C#にの環境設定についてのリンクを紹介します

Macの人はこちら

▶︎ <a href="http://docs.neo.org/ja-jp/sc/getting-started-csharp-mac.html" target="_blank" rel="nofollow noopener">macOSにおいてC#を使用してNeoスマートコントラクトを作成する方法<br /> </a>

Windowsの人はこちら

▶︎ <a href="http://docs.neo.org/ja-jp/sc/getting-started-csharp.html" target="_blank" rel="nofollow noopener">C#を使用してNeoスマートコントラクトを作成する方法</a>

ざっくりこのチュートリアルで使用するツールを  
リストアップするとこんな感じです

<div class="sng-box box31">
  <div class="box-title">
    開発で使用するツール
  </div>
  
  <div class="ol-circle li-mainbdr main-bc-before">
    <ol>
      <li>
        <a href="https://www.visualstudio.com" target="_blank" rel="nofollow noopener">Visual Studio</a>
      </li>
      <li>
        <a href="https://github.com/neo-project/neo-compiler" target="_blank" rel="nofollow noopener">neo-compiler</a>
      </li>
      <li>
        <a href="https://www.microsoft.com/net/download/dotnet-core/runtime-2.0.5" target="_blank" rel="nofollow noopener">.NET Core Runtime 2.0.5</a>
      </li>
    </ol>
  </div>
</div>

チュートリアルをそのまま進めていけば  
開発環境自体は比較的簡単に整います

<a href="https://www.visualstudio.com" target="_blank" rel="nofollow noopener">Visual Studio</a>はプログラムの実装・コーディングに使用します

<a href="https://github.com/neo-project/neo-compiler" target="_blank" rel="nofollow noopener">neo-compiler</a>はプロジェクトのダウンロードが完了したら `neo-compiler.sln` ファイルをVisual Studioで開いてビルド

ビルドが完了すれば `neo-compiler/neon/bin/Debug/netcoreapp2.0` ディレクトリに  
`.ddlファイル`ができるます

<a href="https://www.microsoft.com/net/download/dotnet-core/runtime-2.0.5" target="_blank" rel="nofollow noopener">.NET Core Runtime 2.0.5</a>のインストールが完了していれば

`dotnet`コマンドを使用できるようになっているはずです

<a href="https://www.visualstudio.com" target="_blank" rel="nofollow noopener">Visual Studio</a>で簡単なサンプルを実装して

プロジェクトをビルドすると同じように `.ddlファイル` ができるので

そのファイルを `neo-compiler/neon/bin/Debug/netcoreapp2.0` ディレクトリにコピーして

サンプルで作ったファイルを `neo_practice.dll` とすると

こんな感じでコンパイルできるようになる

`dotnet neon.dll neo_practice.dll`

コンパイル結果は以下のようになります

> Neo.Compiler.MSIL console app v2.0.3.1  
> Find entrypoint:System.Boolean Class1::Main()  
> convert succ  
> gen abi succ  
> write:neo_practice.avm  
> write:neo_practice.abi.json  
> SUCC 

ひとまずチュートリアルでここまでできればOKです

## NEP5トークンの実装で参考になるドキュメントやコード

NEP5トークンの実装で参考になるドキュメントや  
ソースコードについて書いていきます

まずドキュメントはこちら

▶︎ <a href="http://docs.neo.org/ja-jp/sc/tutorial.html" target="_blank" rel="nofollow noopener">NEO スマートコントラクト チュートリアル</a>

このチュートリアルを順に進めていけばコントラクトのデプロイまでできるようになります

その際に、<a href="https://github.com/neo-project/neo-gui/releases" target="_blank" rel="nofollow noopener">neo-gui</a>っていうツールのダウンロードが必要になります

このツールを使用すれば

NEO VMへのデプロイを容易に行うことができるようになります

次に参考になるソースコードですが

NEP5に準拠した実装例があります

このコードを読んで

実際に独自トークンを実装するときの参考にできます

▶︎<a href="https://github.com/neo-project/docs/blob/master/ja-jp/sc/tutorial/assets/examples/Woolong/Woolong/Woolong.cs" target="_blank" rel="nofollow noopener">Woolong.cs</a>

あと、ICO用の実装サンプルも用意してくれてます！

▶︎ <a href="https://github.com/neo-project/examples-csharp/blob/master/ICO_Template/ICO_Template.cs" target="_blank" rel="nofollow noopener">ICO_Template/ICO_Template.cs</a>

これに関しては以下の部分を書き換えるだけで

テストネットにデプロイすれば

実際にトークンセール参加のテストなんかもできたりします

ここでNameやSymbol、オーナーのウォレットアドレスを変更

> public static string Name() => &#8220;name of the token&#8221;;  
> public static string Symbol() => &#8220;SymbolOfTheToken&#8221;;  
> public static readonly byte[] Owner = &#8220;ATrzHaicmhRj15C3Vv6e6gLfLqhSD2PtTr&#8221;.ToScriptHash(); 

ICOの参加日時をunixtimestampで指定する

> private const int ico\_start\_time = 1506787200;  
> private const int ico\_end\_time = 1538323200; 

あとはこれをテストネットへデプロイして動作確認

ここまで用意してくれてるのは嬉しいですね(個人的には使わないですがw)

### テストネットでテスト用のNEO・GASを受け取る方法

NEOで実際にトークンを実装してテストネットへのデプロイや

動作確認をしたい場合に

テスト用のNEOやGASが必要になります

それらに関しては以下のURLから

申請することで指定してウォレットで受け取ることができます

▶︎ <a href="https://neo.org/Testnet/Create" target="_blank" rel="nofollow noopener">Apply For TestNet NEO&GAS</a>

## NEOのウォレットアプリや開発まわりのドキュメント

NEOにはいくつかウォレットアプリがあって  
以下のURLからそれぞれ確認することができます

▶︎ <a href="https://neo.org/client" target="_blank" rel="nofollow noopener">Get Client</a>

自分は実際に**Neon Wallet**を使用して

トークンセール参加のテストをしてみましたが

なかなか使いやすかったです

▶︎ <a href="https://github.com/CityOfZion/neon-wallet/releases" target="_blank" rel="nofollow noopener">Neon Wallet</a>

また、NEOについてや開発周りのドキュメントはこの&#8221;<a href="https://github.com/CityOfZion/awesome-neo" target="_blank" rel="nofollow noopener">awesome-neo</a>&#8220;っていうGitHubリポジトリで確認することができます

例えば、SDKの対応状況なんかも確認できます

▶︎ <a href="https://github.com/CityOfZion/awesome-neo#sdks" target="_blank" rel="nofollow noopener">awesome-neo#sdks</a>

ソースコードの例なんかもここから確認できます

▶︎ <a href="https://github.com/CityOfZion/awesome-neo#code-examples" target="_blank" rel="nofollow noopener">awesome-neo#code-examples</a>

以上、ざっくりやけどNEP5トークンの実装に役立つ情報を書いてました

公式ドキュメントが豊富で

ちゃんと読み込んでいけば

そんなに実装には困らないかなぁって感じです