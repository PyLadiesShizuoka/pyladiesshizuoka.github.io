---
layout: post
title: "GitHub Pagesって何回更新しても無料なの？気になったので調べてみました！"
date: 2026-11-07
---
こんにちは、PyLadies Shizuokaです！

PyLadies ShizuokaのWebサイトは、GitHub Pagesを使って公開しています。
普段はGitHub上でファイルを編集し、変更を保存（コミット）することでWebサイトを更新しています。
そんな中、ふと疑問が浮かびました。

**「GitHub Pagesって、何度も更新していたら無料の利用枠を使い切ってしまうのでは？」**

無料で使えるのはありがたいけれど、どこまで無料なのか、実はよく分かっていませんでした。
そこで、GitHubの公式ドキュメントを調べてみました！

---
## 目次
{: .no_toc }

* TOC
{:toc}

---

## 実は「トークン」を消費すると思っていました {#token}

今回調べるきっかけになったのは、私自身の勘違いでした。

GitHub PagesでWebサイトを更新するたびに、**何かしらの「トークン」を消費している**と思っていたのです。
生成AIのサービスでは、文章の処理量を「トークン」という単位で表すことがあります。
そのイメージから、

- GitHub Pagesも更新するたびに無料枠を消費して、一定量を超えると有料になるのでは？
- ブログを何度も書き直していたら、いつの間にか無料枠を使い切ってしまうのでは？

と考えたり、心配したりしていました。
ところが、調べてみると、GitHub Pagesの更新は**生成AIのようにトークンを消費する仕組みではありません**でした。

GitHub Pagesには、

- 「ビルド回数」の制限がある
- GitHub Actionsには「実行時間」などに応じた利用枠や料金の仕組みがある

ことが分かりました。
つまり、私が心配していた「更新するたびにトークンが減って、なくなったら有料になる」という理解は間違っていたのです。
同じGitHubのサービスでも、何を利用するかによって制限や料金の考え方が違うのですね。

では、実際にGitHub Pagesは何回まで更新できるのでしょうか？

---
## GitHub Pagesには更新回数の制限がある？ {#build-limit}

調べてみると、GitHub Pagesには次の制限がありました。

**1時間あたり10回のビルドがソフトリミット**

「ビルド」とは、Webサイトを公開できる状態にするための処理です。

PyLadies Shizuokaでは、GitHub Pagesの「Deploy from a branch」という方法でサイトを公開しています。
これは、指定したブランチに変更を反映すると、GitHubがWebサイトを更新してくれる仕組みです。
つまり、ブログ記事を追加したり、ページを修正したりすると、公開のための処理が行われます。

なお、10回というのは「ソフトリミット」であり、必ず10回目で停止するという意味ではありません。
また、1日に10回までという制限でもありません。
例えば、1つのブログ記事であっても、誤字脱字の修正やデザインの調整などで何度もコミットすると、
その都度ビルドが行われるのが通常です。

そのため、同じ記事を1時間以内に何度も更新した場合、10回のソフトリミットに達する可能性があります。

PyLadies Shizuokaでは、誤字脱字やデザインの修正は、できるだけまとめてコミットするようにしています。

---
## 10回を超えたら有料になるの？ {#pricing}

ここが一番気になっていたところです。
結論からいうと、

**10回を超えたからといって、自動的に有料になるわけではありません。**

GitHub Pagesのビルド回数の制限は、料金の境界ではなく、サービスを安定して提供するための制限です。
そのため、料金を支払えば単純に更新回数を増やせる、という仕組みではありません。

---
## ほかにも制限はあるの？ {#other-limits}

GitHub Pagesには、更新回数以外にもいくつかの制限があります。

| 項目 | 制限 |
|---|---|
| ビルド回数 | 1時間あたり10回（ソフトリミット） |
| 公開サイトの容量 | 最大1GB |
| 月間通信量 | 100GB（ソフトリミット） |
| デプロイ処理時間 | 10分以内 |

通信量とは、訪問者がWebサイトを閲覧した際などに送受信されるデータ量のことです。
画像が多いサイトやアクセス数の多いサイトでは、通信量も増えます。

---
## GitHub Actionsとは何が違うの？ {#actions}

GitHubには「GitHub Actions」という自動化の仕組みもあります。
GitHub Pagesでは、独自のGitHub Actionsワークフローを使ってサイトを公開する方法も選べます。
この方法でビルド・公開する場合、GitHub Pagesの「1時間10回」というビルド制限は適用されません。
ただし、GitHub Actionsには別の利用制限や料金の仕組みがあります。

標準のGitHubホストランナーを使う場合、公開リポジトリでは無料で利用できます。
一方、非公開リポジトリなどでは、プランに含まれる利用枠を超えると追加料金が発生する場合があります。
つまり、GitHub PagesとGitHub Actionsでは、確認するべき制限が異なるのですね。

---
## PyLadies Shizuokaでは大丈夫？ {#pyladies}

現在、PyLadies Shizuokaでは、ブログ記事の追加やイベント情報の修正などを必要に応じて行っています。
普段の運用で、1時間に10回もサイトを公開し直すことは多くありません。
そのため、現状の更新頻度であれば、ビルド回数の制限を過度に心配する必要はなさそうです。
ただし、今後サイトの規模が大きくなったり、更新方法を変更したりする場合には、改めて確認したいと思います。

---
## おわりに {#summary}

今回調べてみて、GitHub Pagesには無料で使える範囲だけでなく、更新回数や通信量などの制限もあることが分かりました。
また、GitHub Pagesの制限とGitHub Actionsの料金は、別々に考える必要があることも学びました。
普段何気なく使っているサービスでも、仕組みを調べてみると新しい発見がありますね。

PyLadies Shizuokaでは、これからも実際の運営や学習の中で気になったことを、少しずつ紹介していきたいと思います！

---
## 参考資料

- [GitHub Pages limits（公式ドキュメント）](https://docs.github.com/en/pages/getting-started-with-github-pages/github-pages-limits)
- [Configuring a publishing source for your GitHub Pages site](https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site)
- [GitHub Actionsの料金と利用状況](https://docs.github.com/en/actions/concepts/billing-and-usage)

---

**PyLadies Shizuoka Meetup #3**

**[▶ イベントのお申し込みはこちら（connpass）](https://pyladies-shizuoka.connpass.com/event/408134/)**

---
## Slackへのお誘い

PyLadies Shizuokaでは、チャットツールSlackを使ってメンバー同士コミュニケーションをとっています。
PyLadies Shizuokaの活動に興味のある方は、この機会にぜひSlackチームに参加してみませんか？
PyLadies Shizuokaだけではなく、東京をはじめ、日本全国の女性Pythonistaと交流することもできます。

[Slackアカウント申請 – PyLadies Japan](https://docs.google.com/forms/d/e/1FAIpQLSelRdBGus7o6MsijTZiTt1kFAoFYQlwYgrBPQOrGVwGlAmHNg/viewform)
