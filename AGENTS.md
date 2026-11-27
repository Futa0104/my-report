# AIエージェント向け運用メモ

README.mdも参照してください。my-reportは複数カテゴリのレポート集です。

## サイト構成・仕様

- ルートの `index.html` はカテゴリ一覧とし、個別記事は直接掲載しません。
- 各カテゴリの `index.html`（`<category>/index.html`）は、そのカテゴリの記事一覧とします。
- 個別記事は所属カテゴリの配下に配置し、戻りリンクはそのカテゴリの `index.html` に向けます。
- `reports.json` でカテゴリと記事のメタデータを管理します。
  - `categories`：カテゴリ情報（`id`, `title`, `path`, `description`）
  - `reports`：記事情報（`date`, `category`, `title`, `path`, `description`）
  - 記事の `category` は所属カテゴリの `id` と一致させます。

## 運用

- 記事の追加・更新はユーザーの依頼に応じて行います。明示的な依頼がない限り、自動定期生成は行いません。
- カテゴリを追加する場合は、カテゴリの `index.html` を作成し、`reports.json` の `categories` とルートの `index.html` を更新します。
- 記事を追加する場合は、記事のHTMLを作成し、`reports.json` の `reports` と所属カテゴリの `index.html` を更新します。
- カテゴリや記事の情報を更新する場合は、関連するメタデータと一覧の整合性を維持します。
- 既存のカテゴリ・記事は、削除の依頼がない限り維持します。
