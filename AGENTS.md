# AIエージェント向け運用メモ

README.mdも参照してください。my-reportはOSSに限定しない、複数カテゴリのレポート集です。

## 構成と運用

- トップの `index.html` は大項目（カテゴリ）の一覧です。個別記事をトップに直接並べないでください。カテゴリリンクはHTMLに直接記述し、JavaScriptでの動的描画に依存させないでください。
- `reports.json` の `categories` 配列にカテゴリ情報（`id`, `title`, `path`, `description`）を、`reports` 配列に記事情報（`date`, `category`, `title`, `path`, `description`）を記載します。記事の `category` はカテゴリの `id` と一致させます。
- 各カテゴリに `<category>/index.html` を置き、そのカテゴリの記事へのリンク集とします。現在の `oss/index.html` はOSS記事のリンクを静的HTMLで表示します。
- OSSの解説記事は、このチャットで依頼されたときだけ手動追加します（自動定期生成なし）。
- OSS記事のHTMLは `oss/YYYY-MM-DD-slug.html` に保存します。
- 記事を追加したら `reports.json` の `reports` 配列にメタデータを追加し、該当カテゴリの `index.html` にも記事リンクを追加します。カテゴリ追加時は `reports.json` の `categories` とルート `index.html` の両方を更新します。既存記事・カテゴリの情報を消さないでください。
- OSS記事の戻りリンクは `oss/index.html` に向けます。
- `main` へのpushをきっかけに `.github/workflows/pages.yml` でGitHub Pagesへ公開します。
- 初回のみ Settings → Pages → Build and deployment → Source を **GitHub Actions** に設定してください。
- READMEは人間とAI双方に向けた概要、AGENTS.mdはエージェントの具体的な作業手順とします。
