---
layout: post
title:  "Nocode startupというブログタイトルにも関わらず自己矛盾を抱えてブログを自作した経緯"
description: なぜNocode startupというブログタイトルにも関わらず自己矛盾を抱えてあえてブログを自作したのか？その経緯についてまとめた。
author: Tatsuya
categories: [ Jekyll, Netlify, プログラミング, 雑談 ]
image: assets/images/self-contradiction.jpg
featured: true
hidden: true
---

はてなブログや、アメブロ、note、Medium等、単にブログ始めるだけなら自作せずとも、無料で利用できて誰でもかっこいいブログが開設できる素晴らしいサービスが今の世の中にはごまんとある。その気になればFacebookやTwitterのようなSNSもブログのように使うことができる。　　

コーディングやSEO対策等煩わしいので、これらを利用して情報発信することも前向きに考えた。むしろ当初はてなブログを利用しようとnocode-startupのアカウントまで取得していた。　　

記念すべき第1回目の投稿は、[Aboutページ](https://www.nocode-startup.com/about){:target="_blank"} で"究極的にはコードを書かないのが一番だ"とか言っておきながら、なぜNocodeというポリシーに反して既存サービスの利用を見送り、このブログを自作するに至ったのかについて記していきたい。　　

### 知識のさらなる活用術を模索したい ###
---
全くもって身も蓋もなく非合理的ではあるが、要するに知的好奇心が一番の理由だ。  

自分の知識を資産とするなら、Webアプリ開発で得た諸々の知識をRailsにしか使わないのはROAが低く、レバレッジが効いているとは言えないだろう。

せっかくそれなりの手間をかけて得た知識であるならば、もっとフル活用してRails以外にも色々できるようになった方が広がりがあって楽しいと個人的には思った次第だ。  

### 利用規約を気にせず自分の好きなように情報発信したい ###
---
今後際どい過激な文章を発信するつもりは毛頭ないが、既存のブログサービスでは些細な内容でも規約に引っかかり、十分な説明もないまま記事が削除されることもある。そういった突然記事を削除された時のストレスに加えて何でも自分でやってみたい性分もあり、結局自作がベストであろうという結論になった。  

もちろんやるからには炎上（するのかな？）などのネガティブな反応も含め、全てにおいて自身の裁量と責任の元でこれから情報発信していきたい。

### Rails + Heroku以外の安上がりなサイト公開方法が知りたかった ###
---
以前からなるべく年間1,000円程度のドメイン代のみで簡単にそれなりの独自サイトを構築する方法を探していた。  
ちなみにこれまでに開発したWebアプリはRails + Herokuの組み合わせで独自ドメイン代+Heroku月額使用料（無料利用できるが独自ドメイン使用の場合は有料）+その他API月額使用料がかかっていた。  

重要なプロジェクトであれば上記の費用は必要経費として止む無しと受け入れることができるし、開発に時間とコストをかけるのも納得ができる。しかし今回の一サイドプロジェクトのブログのためにRailsを使うのはやや過剰だし、WordPressもメンテナンスが面倒だから嫌い（笑）。加えて出来ることならお金をかけてサーバーを借りたり、PaaSの有料プランを契約したくないといった駄々をこねる子供のような思考が巡っていたところ、ちょうど知り合いのShunさんがブログで[高速でメンテナンスが簡単な静的サイトを作る方法](https://workabroad.jp/posts/2225){:target="_blank"}を公開していて、内容が正に私の求めるものだったので渡りに船と言わんばかりに真似をすることに決めた。
### サイト構築と公開 ###
---
私の場合、お名前.comのタイムセールで年間500円+消費税で取得した。もちろん他のサイトでドメインを取得しても問題ない。  
その他は全て無料で以下のサービスを利用した。ここでは各種サービスのインストール方法や設定方法を順を追って説明していきたい。

#### Jekyll ####
静的サイトジェネレーター  
[https://jekyllrb.com/](https://jekyllrb.com/){:target="_blank"}

Macユーザーの方や、一度でもRubyやRailsの開発環境を構築された方なら以下のコマンドを叩けば即利用可。そうでない方は[こちら](https://www.sejuku.net/blog/3958#Ruby-3){:target="_blank"}を参照いただきRubyをインストールする必要あり。

```ruby
# Jekyllインストール
gem install jekyll bundler

# 例としてmyblogというタイトルのサイトを作成
jekyll new myblog

# ディレクトリの変更
cd myblog

# 動作確認 http://localhost:4000
jekyll serve

```  
#### Jekyll Themes ####
ブログテンプレートを多数公開しているサイト  
[http://jekyllthemes.org/](http://jekyllthemes.org/){:target="_blank"}  

コーディングが面倒な方はここからお好みのものを選んで使えばOK。ただし使用時のライセンスには注意が必要。  


#### Github ####
ここにレポジトリを作って、公開したいサイトのJekyllソースコードをpushしましょう。


```git
$ git init
$ git add .
$ git commit -m "Initial commit"
$ git remote add origin my-github-repository-url
$ git push -u origin master
```  

#### Netlify ####
無料で利用できるホスティングサービス  
[https://www.netlify.com](https://www.netlify.com){:target="_blank"}   

しかも独自ドメインの設定とサイトの常時SSL接続（https）が無料！！💗  

まずはSign Upから無料登録（メールアドレスでの登録の他、Githubアカウントの認証可能。）  
アカウントを作成したら、Continuous Developmentの項目で、ソースコードをpushしたGithubレポジトリを選択。  
これでpushされる都度、内容が自動更新されるようになる。
![create_new_site]({{site.baseurl}}/assets/images/create_new_site.jpg)  

<br />
次に各自ドメインを購入したサイトの設定方法でDNSをNetlifyに設定する。
![cname]({{site.baseurl}}/assets/images/cname.jpg)  

<br />
最後にDomain Settingから購入したドメインを設定したら完了。私の場合だいたい5分くらいで独自ドメインが適用された。
![custom_domain]({{site.baseurl}}/assets/images/custom_domain.jpg)

<br />
---
以上。私はデザインテンプレートを使ったので、作成から公開まで30分くらいでできた！  
爆速！！！
    
<br />     
### 参考 ###
---
Jekyll + Netlify + Cloudinary で高速なウェブサイトを無料で公開する  
[https://workabroad.jp/posts/2225](https://workabroad.jp/posts/2225){:target="_blank"}  