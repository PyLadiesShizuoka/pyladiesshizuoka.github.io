# PyLadies Shizuoka Website

PyLadies Shizuokaの公式Webサイトを管理するリポジトリです。

PyLadies Shizuoka is a Python community for women and gender minorities in Shizuoka, Japan.

## Webサイト

https://shizuoka.pyladies.com/

## PyLadies Shizuokaについて

PyLadies Shizuokaは、静岡県を中心に活動する、女性およびジェンダーマイノリティを
対象としたPythonコミュニティです。

Pythonを学び始めた方から経験者まで、交流や学習を通じてつながれる場を目指しています。

## 使用している仕組み

- GitHub Pages
- Jekyll
- Liquid
- HTML
- CSS
- JavaScript
- Markdown
- JSON
- Google Analytics 4
- Font Awesome

HTMLとCSSを中心に、GitHub PagesとJekyllを利用して制作・運営しています。
メニューの開閉やヘッダーの表示など、一部にJavaScriptを使用しています。

## 主なフォルダとファイル

```text
├─ _includes/       Google Analyticsの計測コード
├─ _layouts/        通常ページとブログ記事の共通レイアウト
├─ _posts/          ブログ記事
├─ blog/            ブログ一覧ページ
├─ coc/             Code of Conduct
├─ images/          サイトで使用する画像
├─ privacy/         プライバシーポリシー
├─ CNAME            独自ドメインの設定
├─ README.md        このリポジトリの説明
├─ _config.yml      Jekyllとサイト全体の設定
├─ events.json      イベント情報
├─ index.html       トップページ
└─ style.css        サイト全体のスタイル
```

## ページが表示される仕組み

`_layouts/default.html`は、サイト全体の共通レイアウトです。次の内容を管理しています。

- ページタイトル、説明、OGP、X用メタ情報
- Font Awesome、ファビコン、CSSの読み込み
- Google Analyticsの読み込み
- ヘッダーとナビゲーション
- 各ページの本文
- フッター
- コピーライト年、ヘッダー表示、メニュー開閉のJavaScript

ブログ記事では、`_posts`の記事本文を`_layouts/post.html`で整え、
更に`_layouts/default.html`へ組み込んで表示します。

```text
_postsの記事
    ↓
_layouts/post.html
    ↓
_layouts/default.html
    ↓
完成したブログページ
```

Google Analyticsの計測コードは、`_includes/google-analytics.html`から
`_layouts/default.html`へ読み込んでいます。

## 主な更新箇所

### トップページ

`index.html`を編集します。

### ブログ記事

`_posts`フォルダにMarkdown形式で記事を追加します。

ブログ記事では、タイトル、投稿日、本文のほか、必要に応じて記事画像を設定します。
記事画像が設定されている場合は、OGPとXの共有画像にも使用されます。

### ブログ記事の表示

`_layouts/post.html`で、次の内容を管理しています。

- パンくずリスト
- 投稿日
- 記事タイトル
- 記事画像
- 記事本文
- 前後の記事へのリンク
- ブログ一覧へ戻るボタン

### ヘッダー、ナビゲーション、フッター

`_layouts/default.html`を編集します。

このファイルの変更はサイト内の複数ページに反映されるため、
編集時はトップページ、ブログ、Code of Conduct、プライバシーポリシーなどの表示を確認します。

### サイトのデザイン

`style.css`を編集します。

### 画像

`images`フォルダに画像を保存します。

記事ごとの画像が設定されていない場合、OGPとXの共有画像には`/images/blog/ogp.png`を使用します。

### イベント情報

`events.json`にイベント情報を登録します。

各イベントでは、次の項目を管理しています。

- `title`：イベント名
- `url`：connpassのイベントURL
- `started_at`：開始日時
- `ended_at`：終了日時
- `place`：会場
- `source`：情報元

日時は、次のように日本時間を含む形式で記載します。

```json
"started_at": "2026-09-13T13:00:00+09:00"
```

### Google Analytics

`_includes/google-analytics.html`でGA4の計測コードを管理しています。

サイトでアクセス解析を行っているため、`privacy/`にプライバシーポリシーを掲載しています。

## 更新時の確認

更新後は、必要に応じて次の項目を確認します。

- パソコンとスマートフォンで表示が崩れていないか
- ナビゲーションのリンクが正しく動くか
- ブログの画像と前後の記事へのリンクが表示されるか
- OGP・Xの共有画像が正しく設定されているか
- Code of Conductとプライバシーポリシーが表示されるか

## 運営について

このサイトは、PyLadies Shizuokaの活動案内やイベント記録を掲載するために運営しています。

サイトもコミュニティとともに、少しずつ改善しています。

