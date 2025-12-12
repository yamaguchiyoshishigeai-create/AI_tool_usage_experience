---
layout: default
title: 使い方
lang: ja
---

# 使い方（HowToUse）

このファイルは、docs/ 以下に追加した Jekyll サイト（AIツール使用感レポート）の基本的な使い方をまとめたものです。

## 目的
- 新しいツールレポートの追加方法
- 多言語（日本語・英語）対応の運用方法
- GitHub Pages での公開手順
- ローカルでの確認方法

## 推奨ディレクトリ構成（概要）
- docs/
  - index.md
  - _config.yml
  - _layouts/
  - _includes/
  - tools/
    - <tool-slug>.md        ← 日本語ページ
    - <tool-slug>.en.md     ← 英語ページ（任意）
  - assets/

## 新しいツールページを追加する手順
1. docs/tools/ にファイルを作成します。
   - 日本語: docs/tools/<tool-slug>.md
   - 英語: docs/tools/<tool-slug>.en.md  （必要な場合）
2. ファイル先頭に front matter を追加します（例）:
   ---
   layout: default
   title: ツール名（日本語）
   lang: ja
   ---
3. ページ本文に以下の項目を含めると見やすくなります。
   - ツール名
   - バージョン / 実施日
   - 利用目的
   - 手順
   - 感想（良かった点 / 改善点）
   - 総合評価（★）
   - スクリーンショット（assets に配置）
4. 追加後、docs/index.md や docs/_includes/header.html にツールへのリンクを手動で追加してください（自動化は未実装）。

## 多言語対応について（簡易方式）
- 現在はファイル単位で言語を分ける方式です（例: sample-tool.md / sample-tool.en.md）。
- 各ページで front matter の lang を設定してください（ja / en）。
- 将来的に自動切替やより高度な多言語対応を希望する場合は、テンプレートやナビゲーションを拡張します。

## GitHub Pages で公開する手順
1. リポジトリの Settings → Pages を開く。
2. Source を "main branch / docs folder" に設定する。
3. 保存すると数分でサイトが公開されます（URL は Settings に表示されます）。

## ローカルで確認する方法（Jekyll）
1. Ruby と Bundler、Jekyll をインストールしてください。環境により手順が異なります。
2. ローカルで docs をビルド／サーブする場合の一例:
   - cd docs
   - bundle init（まだ Gemfile がない場合）
   - Gemfile に jekyll を追加して bundle install
   - bundle exec jekyll serve --watch
3. ブラウザで http://localhost:4000 を開いて確認します。

## リンクの更新・管理
- ヘッダーのメニューは docs/_includes/header.html を編集してください。
- index.md の一覧も手動で更新してください。

## コミット／ブランチ運用
- まずは main に直接コミットして問題ありませんが、複数人で運用する場合は feature ブランチを切って Pull Request を利用してください。

## 例（日本語ページの最小例）
---
layout: default
title: Example Tool（サンプル）
lang: ja
---

## ツール名
Example Tool

(ここにレポート本文)

## 問い合わせ
- 変更や追加のリクエストがあれば Issue を作成してください。
