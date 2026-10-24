# 株式会社スタジオ燈路｜公式企業サイト

既存デザイン・提供ロゴ・トップ動画を維持したコンテンツ更新版。静的HTML/CSS/JavaScript。外部パッケージ・CDN・バックエンド不要。

## プレビュー

ZIPを展開し、preview.htmlを開くとPC（1280px）・スマートフォン（390px）表示を操作できます。サイト本体はdist/index.html。
推奨: フォルダー内で `python3 -m http.server 8000` → http://localhost:8000/preview.html

## 編集

Node.js 18以降で `npm run build`。依存インストール不要。`npm run check`で内部リンク等を確認。

- data.js: 公開する会社情報・作品・ニュース・現場記事。idは重複しない英数字にする。
- scripts/build.mjs: 共通部と各ページのテンプレート。ビルド時にworks/news/studio-lifeの旧ページを消し、現行データから再生成。
- style.css: 既存レイアウト・色・レスポンシブ。
- app.js: メニュー・絞り込み・動画操作・非動作ログイン。
- assets/: ロゴ・トップ動画・静止画。ビルドでdist/assetsへコピー。
- 作品画像: assetsへ画像を追加し、対象作品に `image:'assets/filename.jpg', imageAlt:'作品の説明'` を追加。画像がなければ既存の抽象図版を表示。
- 記事画像: storiesの各要素にもimage/imageAltを追加可能。記事本文・写真枠の変更はbuild.mjs。

## 設定管理

docs/CONTENT_STATUS.mdに採用済み・暫定・未設定を分類。管理文書はdistに含まれません。会社概要には未確定の代表者・社員数・詳細住所等を掲載していません。
NEWSは日付が確定した2026-10-02の4i制作情報のみ。作品一覧は2022→2027の昇順。4iは制作中で、星屑航路は一部話数の制作協力です。

## 動画・ポータル

トップ動画は既存の無音7.25秒ループ版を保持。動きを減らす設定ではポスター表示。再生・一時停止ボタンあり。
関係者ページは入力を保存・送信しないモック。認証・ポータル本体は未実装。

## GitHub Pages

公開URL: https://studio-touro.github.io/
mainのルートにビルド済みサイトを配置し、GitHub Pagesで配信。
編集用ソースはsite/、元素材はoriginals/。`site/`でnpm run buildとnpm run checkを実行し、dist/の内容をリポジトリのルートへ反映してください。
管理資料はsite/docs/に保管しています。
