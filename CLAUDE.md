# CLAUDE.md

## プロジェクト概要

このディレクトリはタスクボードアプリケーションのプロジェクトです。

---

## Git 運用ルール

### コード変更のたびに GitHub へプッシュすること

- コードを変更・保存するたびに、必ず以下の手順でコミット＆プッシュを行う
- リモートリポジトリ: GitHub

```
git add <変更ファイル>
git commit -m "変更内容の要約"
git push origin <ブランチ名>
```

### コミットメッセージ規約

- 変更の「なぜ」を中心に簡潔に記述する（1〜2文）
- 日本語・英語どちらでも可

### ブランチ運用

- メインブランチ: `main`
- 機能追加・バグ修正は原則としてフィーチャーブランチを作成してから作業する
- `main` への直接プッシュは避け、Pull Request を使用する

### 禁止事項

- `--no-verify` でフックをスキップしない
- `--force` プッシュは明示的な指示がない限り行わない
- `.env` や認証情報ファイルをコミットしない

---

## デプロイ先

- **本番URL**: https://ysato-crypto.github.io/task-board/
- **デプロイ方法**: `main` ブランチへのプッシュで GitHub Actions が自動ビルド＆デプロイ
- **ワークフロー**: [.github/workflows/deploy.yml](.github/workflows/deploy.yml)

---

## 技術スタック

| カテゴリ | 技術 |
|---|---|
| UIライブラリ | React 18 |
| ビルドツール | Vite 6 |
| スタイリング | CSS Modules |
| 状態管理 | React `useState` / `useEffect` |
| データ永続化 | `localStorage` |
| デプロイ | GitHub Pages + GitHub Actions |

---

## コンポーネント命名規約

- **ファイル名**: PascalCase（例: `App.jsx`, `TaskItem.jsx`）
- **CSSモジュール**: コンポーネントと同名に `.module.css` を付ける（例: `App.module.css`）
- **コンポーネント関数**: PascalCase（例: `export default function TaskItem()`）
- **ローカル関数・変数**: camelCase（例: `addTask`, `toggleTask`）
- **定数**: UPPER_SNAKE_CASE（例: `STORAGE_KEY`）

---

## 開発ガイドライン

- コードは変更最小限に留め、不要なリファクタリングは行わない
- コメントは「なぜそうするか」が非自明な場合のみ記述する
- セキュリティ上の脆弱性（SQLインジェクション、XSS 等）を絶対に導入しない

---

## 問い合わせ先

- 担当: y.sato@lifefactoryink.com
