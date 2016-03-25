---
layout: post
title:  "オブジェクト指向のこころ"
date:   2016-03-24 20:59:37
---

## オブジェクト指向のこころ

タイトル名の本を1週間ぐらいかけて読んだ。いろいろと学びが多かったので整理してみる。

<div class="booklog_html"><table><tr><td class="booklog_html_image"><a href="http://www.amazon.co.jp/%E3%82%AA%E3%83%96%E3%82%B8%E3%82%A7%E3%82%AF%E3%83%88%E6%8C%87%E5%90%91%E3%81%AE%E3%81%93%E3%81%93%E3%82%8D-SOFTWARE-PATTERNS-SERIES-%E3%82%A2%E3%83%A9%E3%83%B3%E3%83%BB%E3%82%B7%E3%83%A3%E3%83%AD%E3%82%A6%E3%82%A7%E3%82%A4/dp/4621066048%3FSubscriptionId%3D0AVSM5SVKRWTFMG7ZR82%26tag%3Dtakuma510-22%26linkCode%3Dxm2%26camp%3D2025%26creative%3D165953%26creativeASIN%3D4621066048" target="_blank"><img src="http://ecx.images-amazon.com/images/I/510uRnu%2BbYL._SL160_.jpg" width="116" height="150" style="border:0;border-radius:0;" /></a></td><td class="booklog_html_info" style="padding-left:20px;"><div class="booklog_html_title" style="margin-bottom:10px;font-size:14px;font-weight:bold;"><a href="http://www.amazon.co.jp/%E3%82%AA%E3%83%96%E3%82%B8%E3%82%A7%E3%82%AF%E3%83%88%E6%8C%87%E5%90%91%E3%81%AE%E3%81%93%E3%81%93%E3%82%8D-SOFTWARE-PATTERNS-SERIES-%E3%82%A2%E3%83%A9%E3%83%B3%E3%83%BB%E3%82%B7%E3%83%A3%E3%83%AD%E3%82%A6%E3%82%A7%E3%82%A4/dp/4621066048%3FSubscriptionId%3D0AVSM5SVKRWTFMG7ZR82%26tag%3Dtakuma510-22%26linkCode%3Dxm2%26camp%3D2025%26creative%3D165953%26creativeASIN%3D4621066048" target="_blank">オブジェクト指向のこころ (SOFTWARE PATTERNS SERIES)</a></div><div style="margin-bottom:10px;"><div class="booklog_html_author" style="margin-bottom:15px;font-size:12px;;line-height:1.2em">著者 : <a href="http://booklog.jp/author/%E3%82%A2%E3%83%A9%E3%83%B3%E3%83%BB%E3%82%B7%E3%83%A3%E3%83%AD%E3%82%A6%E3%82%A7%E3%82%A4" target="_blank">アラン・シャロウェイ</a></div><div class="booklog_html_manufacturer" style="margin-bottom:5px;font-size:12px;;line-height:1.2em">丸善出版</div><div class="booklog_html_release" style="font-size:12px;;line-height:1.2em">発売日 : 2014-03-11</div></div><div class="booklog_html_link_amazon"><a href="http://booklog.jp/item/1/4621066048" style="font-size:12px;" target="_blank">ブクログでレビューを見る»</a></div></td></tr></table></div>

## 複雑さとの戦い

ソフトウェア設計/実装パラダイムはオブジェクト指向のみではない。幾つかの設計/実装パラダイムがある中での一つの選択肢としてオブジェクト指向を据えることは大切だと思う。
なぜオブジェクト指向設計等の設計/実装パラダイムがあるのかというその存在意義だが，自分の理解では，大規模で複雑なソフトウェアをいかにコントローラブルに作っていくかという問題を解くためのものである。

ソフトウェア開発において，要求や仕様は常に変化していくものである。
変化していく内容は予測することは難しいが，変化していく箇所をコントロールしていくことは可能であり，このコントロールの仕方が一つの観点である。

## 凝集度を高くし，結合度を低くする

メンテナンスしやすい，コントローラブルなソフトウェアとはどのようなものであろうか。いくつかの指標があるが，その中でもよく知られているのが，凝縮度と結合度である。

本書ではそれぞれをCode Completeを拝借して以下のように説明している。

> 凝集度とは「ルーチン内の演算がどれだけ密接に関係しているのか」を表す尺度である。
> McConnell, S. Code Complete: A Practical Handbook of Software Contruction, Redmond: Microsoft Press 1993, p81

> 結合度とは「2つのルーチン間の関連の強さ」を表す尺度であり，凝集度を補完するものである。凝集度はルーチン内の中身がどれだけ強く関連しあっているのかを示すものであり，結合度はあるルーチンが他のルーチンとどれだけ強く関連試合っているのかを示すものである。その目標は，内部が完全であり（高い凝集度），小さく，直接的であり，視認性が高く，他のルーチンとの関係が柔軟になる（低い結合度）ルーチンを作ることにある。
> 同 p87

この凝集度と結合度を設計の良し悪しの主な判断材料として様々なパターンを考察している。

## 概念，仕様，実装という観点を意識する

物事を考える際，今の自分の観点はどのような観点かを意識することは重要である。

オブジェクトを設計する際にも，この観点を意識することは有用である。主に以下の3つの観点で考えると整理しやすい。

概念。

> この観点は，調査対象領域における概念を表現したものです。そして概念モデルは，概念を実装するソフトウェアとは関係なく導き出されるべきものです。この観点は「私は何に対して責任があるのか？」という質問に答えるものです。

仕様。

> ここではソフトウェアを考慮することになります。しかし考慮する対象はソフトウェアの実装ではなく，ソフトウェアのインターフェースです。この観点は，「私はどのように使用されるのか？」という質問に答えるものです。

実装。

> この時点ではソースコド自体を考慮することになります。これが最もよく使用される観点ですが，多くの場合はしようという観点の方が優れています。この観点は「私はどのようにして自身の責任を全うするのか？」という質問に答えるものです。


## 概念と実装のポリモーフィズム

クライアントは概念レベルの内容でオブジェクトにメッセージを送り，その処理の詳細や具体的なオブジェクトの型については感知しない。
この型を渡すのは他のオブジェクトの責務。ファクトリであることも多い。


## 流動的要素を見つけ出し，カプセル化する

具体的な設計の考え方として，共通性/可変性分析というもの紹介されている。

> 振る舞いやデータに存在する流動的要素は，共通性/可変性分析によって抽象化する。

流動的要素は具体的な実装方法であったり（Strategy）概念であったりする。

## デザインパターンの原則と戦略

オブジェクト指向の原則，考え方を実践する具体例として以下のようなパターンの導出がある。
Facade，Adapter，Strategy，Bridge，Abstract Factory，Decorator，Observer，Template Method，Singleton，Double-Checked Locking，Object Pool，Factory Method。

実装レベルでのデザインパターンはさほど重要ではなく，本質なのなデザインパターンを生じせしめるコンテキストであると考えている。

## おわりに

この本を読んでオブジェクト指向についての理解がだいぶ深まった。実践でこれらの概念を血肉としていきたい。

オブジェクト指向に関しては以下の本が専門的に，より詳細に，しっかり書かれているそうなので，ちまちま読み進めていきたい。

<div class="booklog_html"><table><tr><td class="booklog_html_image"><a href="http://www.amazon.co.jp/%E3%82%AA%E3%83%96%E3%82%B8%E3%82%A7%E3%82%AF%E3%83%88%E6%8C%87%E5%90%91%E5%85%A5%E9%96%80-%E7%AC%AC2%E7%89%88-%E5%8E%9F%E5%89%87%E3%83%BB%E3%82%B3%E3%83%B3%E3%82%BB%E3%83%97%E3%83%88-Architect%E2%80%99Archive-%E3%82%AF%E3%83%A9%E3%82%B7%E3%83%83%E3%82%AF%E3%83%A2%E3%83%80%E3%83%B3%E3%83%BB%E3%82%B3%E3%83%B3%E3%83%94%E3%83%A5%E3%83%BC%E3%83%86%E3%82%A3%E3%83%B3%E3%82%B0/dp/4798111112%3FSubscriptionId%3D0AVSM5SVKRWTFMG7ZR82%26tag%3Dtakuma510-22%26linkCode%3Dxm2%26camp%3D2025%26creative%3D165953%26creativeASIN%3D4798111112" target="_blank"><img src="http://ecx.images-amazon.com/images/I/41A2yC7UpOL._SL160_.jpg" width="105" height="150" style="border:0;border-radius:0;" /></a></td><td class="booklog_html_info" style="padding-left:20px;"><div class="booklog_html_title" style="margin-bottom:10px;font-size:14px;font-weight:bold;"><a href="http://www.amazon.co.jp/%E3%82%AA%E3%83%96%E3%82%B8%E3%82%A7%E3%82%AF%E3%83%88%E6%8C%87%E5%90%91%E5%85%A5%E9%96%80-%E7%AC%AC2%E7%89%88-%E5%8E%9F%E5%89%87%E3%83%BB%E3%82%B3%E3%83%B3%E3%82%BB%E3%83%97%E3%83%88-Architect%E2%80%99Archive-%E3%82%AF%E3%83%A9%E3%82%B7%E3%83%83%E3%82%AF%E3%83%A2%E3%83%80%E3%83%B3%E3%83%BB%E3%82%B3%E3%83%B3%E3%83%94%E3%83%A5%E3%83%BC%E3%83%86%E3%82%A3%E3%83%B3%E3%82%B0/dp/4798111112%3FSubscriptionId%3D0AVSM5SVKRWTFMG7ZR82%26tag%3Dtakuma510-22%26linkCode%3Dxm2%26camp%3D2025%26creative%3D165953%26creativeASIN%3D4798111112" target="_blank">オブジェクト指向入門 第2版 原則・コンセプト (IT Architect’Archive クラシックモダン・コンピューティング)</a></div><div style="margin-bottom:10px;"><div class="booklog_html_author" style="margin-bottom:15px;font-size:12px;;line-height:1.2em">著者 : <a href="http://booklog.jp/author/%E3%83%90%E3%83%BC%E3%83%88%E3%83%A9%E3%83%B3%E3%83%89%E3%83%BB%E3%83%A1%E3%82%A4%E3%83%A4%E3%83%BC" target="_blank">バートランド・メイヤー</a></div><div class="booklog_html_manufacturer" style="margin-bottom:5px;font-size:12px;;line-height:1.2em">翔泳社</div><div class="booklog_html_release" style="font-size:12px;;line-height:1.2em">発売日 : 2007-01-10</div></div><div class="booklog_html_link_amazon"><a href="http://booklog.jp/item/1/4798111112" style="font-size:12px;" target="_blank">ブクログでレビューを見る»</a></div></td></tr></table></div>
