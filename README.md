# My Report

技術レポートを GitHub Pages で公開するリポジトリです。

- OSSの解説記事は、このチャットで依頼されたときだけ手動追加します（自動定期生成なし）。
- 記事のHTMLは `oss/YYYY-MM-DD-slug.html` に保存します。
- 記事を追加したら `reports.json` の `reports` 配列にもメタデータを追加します。
- `index.html` は `reports.json` を読み込み、公開記事へのリンクを一覧表示します。
- `main` へのpushをきっかけに `.github/workflows/pages.yml` でGitHub Pagesへ公開します。
- 初回のみ Settings → Pages → Build and deployment → Source を **GitHub Actions** に設定してください。
