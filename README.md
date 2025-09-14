# Conduit

このリポジトリは、[RealWorld](https://realworld-docs.netlify.app/) OSS プロジェクトを参考にした **Medium.com クローン（Conduit）** を Rails で実装したものです。  
フレームワークの実践的な学習を目的としています。

---

## 📌 概要

- Conduit は Medium.com のクローンサイトです。
- 本実装では **Rails** を用いて、フロント（HTML/CSS）から CRUD 機能までを実装しました。
- 学習課題として「見た目の再現」と「基本的な記事管理機能の実装」がゴールです。

---

## 🚀 ステップ 1: 静的ページ作成

RealWorld のドキュメントを参考に、以下のページを HTML / CSS で再現しました。

- Home
- Create / Edit Article
- Article

### 要件
- 各画面を ERB ファイルで作成  
- CSS を適用  
- `routes.rb` でルーティングを設定し、各ページにアクセス可能にする  

### 注意点
- Article ページの `<hr />` 以下は省略  
- 認証機能・お気に入り機能・フォロー機能は未実装  
- Home 画面の著者名・お気に入り数・ページネーションは省略  
- 読み込めない画像要素は削除  

---

## ⚙️ ステップ 2: 機能追加（CRUD）

静的ページに機能を追加し、動作する記事管理機能を実装しました。

### 必須要件
- Home 画面の記事一覧の下に「Create」ボタンを配置し、新規作成画面へ遷移できる  
- Create 画面で「Publish Article」を押すと、記事が DB に保存され、Home 画面に表示される  
- Home 画面の記事タイトルをクリックすると、記事詳細画面へ遷移する  
- Article 画面の「Edit Article」ボタンから編集画面に遷移し、入力済みでフォームが表示される  
- Edit 画面で内容を更新すると、DB が更新され、Home 画面の一覧にも反映される  
- 「Delete Article」ボタンを押すと記事が削除され、Home 画面のリストから消える  

---

## 🛠️ 技術スタック

- Ruby on Rails 8.0.2.1
- SQLite3（開発用 DB）
- Bootstrap (RealWorld テーマ)
- Turbo (Rails 7+ デフォルトの非同期ライブラリ)

---

## 📂 ディレクトリ構成（主要部分）
```text
app/
controllers/
articles_controller.rb
views/
articles/
index.html.erb
show.html.erb
new.html.erb
edit.html.erb
_form.html.erb
assets/
stylesheets/
home.css
articles.css
```

---

## 🎯 学習ポイント
- Rails におけるルーティングと CRUD 実装の流れ  
- `form_with` を使ったフォーム処理  
- `link_to` と `turbo_method` を利用した削除リンク  
- 部分テンプレート (`_form.html.erb`) の活用によるビューの共通化  

---

## 📖 参考
- [RealWorld ドキュメント](https://realworld-docs.netlify.app/specifications/frontend/templates/)  
- [Rails ガイド](https://guides.rubyonrails.org/)  

