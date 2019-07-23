---
templateKey: blog-post
id: 226
title: Your story on what is the advantage of Continuous Integration and Continuous Delivery~エンジニアの英語面接対策~
date: 2018-12-05T23:48:00+09:00
author: Yuki Hirai
layout: post
guid: https://yabaiwebyasan.com/?p=226
permalink: /your-story-on-what-is-the-advantage-of-continuous-integration-and-continuous-delivery/
post_views_count:
  - "309"
image: /wp-content/uploads/2018/12/your-story-on-what-is-the-advantage-of-continuous-integration-and-continuous-delivery-125x125.png
categories:
  - エンジニア英語面接対策
---
どうも、<a href="https://twitter.com/iamseninja" target="_blank" rel="nofollow noopener">Yuki Hirai</a>です。

さて、このブログではたまーに

<span class="sobig"><b>エンジニアの英語面接対策</b></span>

を自分用メモ程度に記事にしております。

このシリーズの記事はこちらをご覧ください。

↓

=> <a href="https://yabaiwebyasan.com/category/technology/english-engineer-interview/" target="_blank">「エンジニア英語面接対策」の記事一覧</a>

今日の想定質問はこちら

**&#8220;Your story on what is the advantage of Continuous Integration and Continuous Delivery&#8221;**

ではその回答を書いていきます。

## あなたが考えるCIやCDのメリットを教えてください

今回の質問は直訳すると

「あなたが考えるCIやCDのメリットを教えてください」

といった感じになるかなと思います。

この質問は実際に

<a href="https://blueharvest.io/careers/2/senior-software-engineer--back-end-" target="_blank">BLUE HARVEST</a>という会社の面接で聞かれる質問とのことです。

まず、今回の質問で聞かれている

CIとCDについて簡単に説明しておきます。

## CI(Continuous Integration)とは

CIは日本語で

**継続的インテグレーション**

と呼ばれます。

いまだとCI用の便利なツールがあり

  * <a href="https://circleci.com/" target="_blank">CircleCI</a>
  * <a href="https://travis-ci.com/" target="_blank">TravisCI</a>
  * <a href="https://app.wercker.com" target="_blank">Wercker</a> 

などなどこの他にも色々あります。

最近だと、

<a href="https://jp.techcrunch.com/2018/10/17/2018-10-16-github-launches-actions-its-workflow-automation-tool/" target="_blank">GitHub Actions</a>

が発表されたのも記憶に新しいですね。

これらのツールを使うことで  
例えばGitHubで開発している場合

GitHubのリポジトリにソースコードの変更をpushする度に

それをトリガーにして

ソースコードの

  * ビルド
  * テスト

などを自動で実行してくれるようになります。

もしテストでエラーがあればすぐにエラーに気づけるようになります。

こういうのは手元でテストし忘れた場合などによく起こりやすいですね。

人間はミスをする生き物なので

小さいサイクルの中でも機械的に常時チェックしてくれる仕組みは大変ありがたいです。

## CD(Continuous Delivery)とは

CDは日本語で

**継続的デリバリ**

と呼ばれます。

> 継続的デリバリーとは、DevOps ソフトウェア開発手法の 1 つで、  
> コード変更が発生すると、  
> 自動的にビルド、テスト、および本番へのリリース準備が実行されるというものです。  
> 継続的デリバリーは継続的インテグレーションを拡張したもので、  
> すべてのコード変更が、ビルド段階の後にテスト環境または本番環境、  
> あるいはその両方にデプロイされます。  
> 継続的デリバリーを適切に実装することにより、  
> 開発者は、標準化されたテストプロセスに合格し、  
> デプロイ準備の整ったビルドの成果物を常に手元に持つことになります。 

ref: <a href="https://aws.amazon.com/jp/devops/continuous-delivery/" target="_blank">継続的デリバリーとは?</a>

このようにCDはCIの拡張で、

ビルドやテストだけでなく

本番環境やステージング環境へのリリース準備も実行されるものであるということがわかります。

実際に、リリースまで行うことで

単体テストだけでなくUIテストやロードテスト、統合テスト、APIテストなどなど

リリース後のテストまで検証することが可能になります。

CIと同じく、CDを用いることで

  * 問題の早期発見
  * リリースプロセスの自動化

などが可能になります。

## A. &#8220;Your story on what is the advantage of Continuous Integration and Continuous Delivery&#8221;

というわけでこちらの質問に回答していきます。

> I have used some CI Tool such as CircleCI, TravisCI.
> 
> There are two major advantages.  
> Firstly, we can discover and address bugs earlier.  
> We can automate build and test processing for source code by using CI tool such as CircleCI.  
> If there is a error while CI process, we can share the error message easily.
> 
> Secondly, we can automate the software release process so that the software delivery is more efficient and rapid.  
> We can also automate UI testing, load testing, integration testing, API reliability testing, etc. 

以上ですw

今回は出来るだけシンプルに答えるようにしてみました。

今までは質問に対して出来るだけ長く答えるようにしてましたが、

実際の面接だと長々話すよりも会話のような感じで進んで行くと思うので

今後は要点だけしっかり自分の中で抑えておくという意味もこめて

シンプルに回答できるようにしていければなと思います。