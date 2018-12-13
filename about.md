---
layout: page
title: About - このブログについてと自己紹介
comments: true
---

このブログはプログラミングの知識ゼロで、既存のWebサービスを使ってスタートアップのMVPを作る方法や、副業を手軽かつ簡単にスタートする方法を紹介するブログです。

私がゼロからプログラミングを習得してWebアプリを作成した際の失敗談から得た教訓や、これからアプリを作成して起業する人に向けたアドバイス、無料または安価にコードを書かず（または簡単なコードをコピペするだけで）サービスが開始できたり、アプリに機能を追加する方法等々書いていきます。

このブログを読んでいただいた方が、プログラミングの時間を大幅に削減して、浮いた時間をサービス向上やユーザー獲得に使えるようになれば幸いです。

![jekyll template mediumish]({{site.baseurl}}/assets/images/mediumish-jekyll-template.png){: .shadow}

### 自己紹介

- 新卒から約10年間一貫して金融業界で勤務し、サラリーマン時代のプログラミング知識はゼロ。
- 2017年に起業を決意しエンジニアを募るも、誰一人として協力者が現れず。(つД`)ノ　結局自らがエンジニアになることを決意。^^;
- Ruby on railsを約8ヶ月独学して2つのWebアプリをローンチ。


### Features

- Built for Jekyll
- Compatible with Github pages
- Featured Posts
- Index Pagination
- Post Share
- Post Categories
- Prev/Next Link
- Category Archives (this is not yet compatible with github pages though)
- Jumbotron Categories
- Integrations:
    - Disqus Comments
    - Google Analaytics
    - Mailchimp Integration
- Design Features:
    - Bootstrap v4.x
    - Font Awesome
    - Masonry
- Layouts:
    - Default
    - Post
    - Page
    - Archive
    
### How to Use

If you aren't familiar with Jekyll yet, you should know that it is a static site generator. It will transform your plain text into static websites and blogs. No more databases, slow loading websites, risk of being hacked...just your content. And not only that, with Jekyll you get free hosting with GitHub Pages! This page itself is free hosted on Github with the help of Jekyll and Mediumish template that you're currently previewing. If you are a beginner we recommend you start with [Jekyll's Docs](https://jekyllrb.com/docs/installation/){:target="_blank"}. Now if you know how to use Jekyll, let's move on to using Mediumish template in Jekyll:

#### Using Mediumish

Download or Fork *Mediumish for Jekyll*. 
- In your local project, open <code>_config.yml</code>. If your site is in root, for <code>baseurl</code>, make sure this is set to <code>baseurl: /</code>. Also, change your Google Analytics code, disqus username, authors, Mailchimp list etc.
- Mediumish requires 2 plugins: 
    - <code>$ gem install jekyll-paginate</code>
    - <code>$ gem install jekyll-archives</code>.
- Edit the menu and footer copyrights in <code>default.html</code>
- Start by adding your .md files in <code>_posts</code>. Mediumish already has a few as an example. 
- YAML front matter
    - featured post - <code>featured:true</code>
    - exclude featured post from "All stories" loop to avoid duplicated posts - <code>hidden:true</code>
    - post image - <code>image: assets/images/mypic.jpg</code>
    - external post image - <code>image: "https://externalwebsite.com/image4.jpg" </code>
    - page comments - <code>comments:true</code>
    - meta description (optional) - <code>description: "this is my meta description"</code>
    
YAML Post Example:
<pre>
---
layout: post
title:  "We all wait for summer"
author: Tatsuya
categories: [ Jekyll, tutorial ]
image: assets/images/5.jpg
featured: true
---
</pre>

YAML Page Example
<pre>
---
layout: page
title: Mediumish Template for Jekyll
comments: true
---
</pre>

#### Contribute

- [Clone the repo](https://github.com/wowthemesnet/mediumish-theme-jekyll).
- Create a branch off of master and give it a meaningful name (e.g. my-new-mediumish-feature).
- Open a pull request on GitHub and describe the feature or fix.
