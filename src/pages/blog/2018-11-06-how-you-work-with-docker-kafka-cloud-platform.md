---
templateKey: blog-post
id: 76
title: How you work with Docker, Kafka and Cloud platforms~エンジニア英語面接対策~
date: 2018-11-06T20:23:07+09:00
author: Yuki Hirai
layout: post
guid: https://yabaiwebyasan.com/?p=76
permalink: /how-you-work-with-docker-kafka-cloud-platform/
post_views_count:
  - "219"
image: /wp-content/uploads/2018/11/how-you-work-with-docker-kafka-cloud-platform-125x125.png
categories:
  - エンジニア英語面接対策
---
どうも、<a href="https://twitter.com/iamseninja" target="_blank" rel="nofollow noopener">Yuki Hirai</a>です。

さて、前回の記事から

<span class="sobig"><b>エンジニアの英語面接対策</b></span>

を自分用メモ程度に記事にしております。

今日もざっくり

<span class="big"><b>想定質問とその回答</b></span>

を書いていこうかなと思ってます！

前回の記事はこちらをご覧ください。

↓

<blockquote class="wp-embedded-content" data-secret="4uaEqH3VJM">
  <p>
    <a href="https://yabaiwebyasan.com/prepare-english-engineer-interview/">エンジニアの英語面接対策〜Your latest and greatest project you&#8217;ve developed in [Java, Scala, PHP etc]〜</a>
  </p>
</blockquote>



ではさっそく想定質問とその回答を書いていきます。

## DockerやKafka,クラウドプラットフォームフォームについての取り組みについて

この質問は英語で

**&#8220;Your story on how you work with Docker, Kafka and Cloud platforms&#8221;**

と聞かれたりします。

この質問では

  * Docker
  * Kafka
  * Cloud Platform

それぞれについて、どのくらいノウハウがあるのか？を

聞いてるのかなと思います。

ただ、捉えようによっては

**DockerとKafka、クラウドサービスをどのように組み合わせて使いますか？**

ともとれる？むしろそっち？？？ですかね？w

ちょっとわからないので実際の面接では確認したほうがいいかもです。

今回はそれぞれの経験について答えてみたいと思います。

その前に、今回の質問内容に含まれているそれぞれの技術スタックについて簡単に説明します。

### Dockerとは

ちなみにDockerは

> インフラ関係やDevOps界隈で注目されている技術の一つで、Docker社が開発している、コンテナ型の仮想環境を作成、配布、実行するためのプラットフォームです。 

=> <a href="https://knowledge.sakura.ad.jp/13265/" target="_blank">Docker入門（第一回）～Dockerとは何か、何が良いのか～</a>

最近のオープンソースプロジェクトは

ローカル開発環境をDockerを使用して構築したりします。  
Kubernetesと組み合わせて実稼働するアプリケーションを管理したりするのにも使われます。

個人的に感じたメリットとしては

  * ローカル環境を汚さなくても開発可能になり、開発環境の共有が楽になる
  * アプリの動作環境に必要なものをDockerfileを書くことで持ち運びがしやすくなる
  * インフラのメンテナンスや整備が楽になる(nginx, supervisor とかをそれぞれコンテナにすることで使い回しもしやすい)
  * docker-composeとかで別々のコンテナを結びつける(リンクする)ことも簡単

などがあります。

また、AWSのECRやECSと組み合わせて使ってみたこともあります。

ECRとECSについて簡単に説明しておきます。

#### ECRについて

DockerHubみたいなもの。

DockerHubはお金払えばプライベートDockerイメージをプライベートで登録できるが  
AWSのECRでもAWS認証で同じようにプライベートなDockerイメージの登録ができる。

GitHubでリポジトリをつくるような感じでプライベートなDockerイメージリポジトリをつくっておき  
そこにローカルから各サービスをdocker pushしていくことで 内容を更新できるイメージ。

#### ECSについて

ECSとは Elastic Container Service の略で Dockerのマネージドサービス。  
これがないと自分でEC2でサーバーを立てて、docker入れて 複数コンテナの管理を独自に頑張らなければいけないが  
ECSを使えば簡単に管理できる。

ECRで管理しているリポジトリを  
docker-composeの要領でひとつのタスクにひとまとめにして管理・更新できる。

ロードバランサーにいれたいサービスやオンデマンドバッチ処理  
コンテナが落ちたら自動復旧させたい  
などの用途で使用できて便利。

### Kafkaとは

Kafkaはオープンソースのビッグデータ処理ツールで  
正式名称は「Apache Kafka(アパッチ カフカ)」といいます。

以下のサイトから説明を引用すると

> Apache Kafkaは、分散環境において「高スループット」かつ「低レイテンシ」で、  
> 大規模データ(ログデータ/イベントデータなど)を高速に取り込み、配信できるメッセージングシステムです。  
> オンライン/オフライン両方のメッセージ取得に対応します。  
> 「リアルタイムストリーミングデータパイプライン構築」や  
> 「データストリームを変換するリアルタイムストリーミングアプリケーション」などを構築できます。 

とあります。

=> <a href="https://www.ossnews.jp/oss_info/Apache_Kafka" target="_blank">オープンソースのビッグデータ処理ツール／Apache Kafkaとは<br /> </a>

簡単に体験してみたい場合は以下の記事が参考になりそうです。

=> <a href="https://qiita.com/tic40/items/92cd3801b3f2d281b38d" target="_blank">Apache Kafkaインストールからチュートリアルまで</a>

### A. &#8220;Your story on how you work with Docker, Kafka and Cloud platforms&#8221;

Cloud Platformについてはメジャーなところだと

  * AWS(Amazon Web Services)
  * GCP(Google Cloud Platform)

なんかがあります。

というわけで自分の経験を英語で書いてみます。

> First of all, I will explain about Docker.  
> I have used it in the project I have developed.  
>     That project is a simple crawler and API.  
>     Then, I realized the following four merits.
> 
>     1. It becomes possible to develop without having to pollute the local environment, making it easy to share the development environment  
>     2. It becomes easier to carry around by writing a Dockerfile that is necessary for the operating environment of the application  
>     3. Easier maintenance of infrastructure => nginx, supervisor and so on as containers make it easy to use  
>     4. It is easy to link different containers such by using docker-compose
> 
>     In that project, I used Amazon Web Service and managed it with ECR and ECS.
> 
>     Next, about kafka  
>     I have not used it in the project.  
>     There was no particular requirement for processing large-scale data at high speed.  
>     However, since I am interested in personally handling large-scale data, I&#8217;ve tried out a simple tutorial.
> 
>     Finally, about the cloud platform  
>     I have used AWS.
> 
>     &#8211; Creating instances with EC2  
>     &#8211; Create lambda function using Serverlss, create sns topic, link with DynamoDB  
>     &#8211; Use of RDS  
>     &#8211; Routing configuration using Route 53  
>     &#8211; Deploy automation using CodeDeploy  
>     &#8211; Use of ECR ​​or ECS
> 
> and so on
> 
> I have used it for various purposes such as etc. 

んー、とりあえず自分の経験をざっと書いてみましたが  
いまいちインパクトにかけますねw

Apache Kafkaを実務で使用したことがないので

「簡単なチュートリアルをやってことがある」

といった回答に留めてますが  
この質問をしてくるということは

募集要項でApache Kafkaの経験を求めている可能性が高いので

未経験だと少しきついかもしれません。

実務で使用したことないツールも  
どんどん個人で試していかないといけないなと改めて感じました。