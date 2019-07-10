---
templateKey: blog-post
id: 189
title: 綺麗なcommitは良いコードを書くことにつながり、良い仕事をもたらす
date: 2018-12-01T14:04:18+09:00
author: Yuki Hirai
layout: post
guid: https://yabaiwebyasan.com/?p=189
permalink: /good-commit-for-great-job/
post_views_count:
  - "264"
image: /wp-content/uploads/2018/11/good-commit-for-great-job-125x125.png
categories:
  - テクノロジー
---
どうも、<a href="https://twitter.com/yabaiwebyasan" target="_blank" rel="nofollow noopener">Yuki Hirai</a>です。

エンジニアのみなさん

<span class="sobig"><b>綺麗なcommitしてますか？</b></span>

今日は11月5日に

「<a href="https://supporterzcolab.com/event/583/" target="_blank">きれいなcommit, pull requestを知りたい/作りたい方のためのgit勉強会</a>」

に行ってきたのでそのときのことをメモ程度に残しておきます。

## gitのcommitは5w1hで書こう

gitのコミットメッセージは出来るだけ具体的に書くと

**&#8220;git log&#8221;**

したときに

「どこで何をしたっけ？」

っていうのが見つけやすくなる

つまり、

「**検索しやすくなる**」

とのことでした。

## 良いコードが書けるといい仕事ができる

良いコミットを意識すると

自然とコード自体もよくなっていくので

結果、いい仕事ができますよね

っていう話が面白かったです。

そのコミットは同じ目的のためにされたコミットなのか

いろんなものが入り混じったコミットになっていないのか

という考え方は

このクラスはちゃんと目的に即してつくられているか

いろんな処理をひとつのクラスに詰め込みすぎて

本来の目的からずれていないか

といった思考と同じような思考なので

プログラマとしてよりよい思考を育んでいくことにもつながりますね

## 綺麗なコミットをするためのgitの小技

ちなみに資料はこちらのリンクから一通り確認できます。

=> <a href="https://speakerdeck.com/imaizume/zuo-ritaifang-falsetamefalsegitmian-qiang-hui" target="_blank">(再演)きれいなcommit, pull requestを知りたい/作りたい方のためのgit勉強会</a>

その中でもとくにやっといたほうがいいなと個人的に思ったのは

  * git add -p(pacth) 行単位でgit add => sでさらに詳細に/tigで簡単にできる
  * git rebase -i => 結合、順番入れ替え、分割

といったところですかね

まぁ、資料がとても綺麗にまとまってるので一通りみるのがよいですw