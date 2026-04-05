# Rally Docs

[Rally](https://github.com/tetsumaru/rally) の公開ドキュメントリポジトリです。

Rally は private リポジトリのため、API 仕様や用語集など外部に公開したいドキュメントをこのリポジトリで管理しています。
ソースリポジトリの `docs/` ディレクトリが更新されると、このリポジトリに自動で同期されます。

## 構成

```
docs/
└── api/
    ├── openapi.yaml   # REST API 仕様 (OpenAPI 3.1)
    └── index.html     # API リファレンス UI
```

## API 仕様

Rally Cloud Functions API の仕様は OpenAPI 3.1 形式で定義されています。

- **認証**: Bearer トークン
- **リクエスト形式**: Firebase Callable 形式 (`{"data": {...}}`)
- **リージョン**: `asia-northeast1`

## ライセンス

Rally プロジェクトのドキュメントです。詳細は Rally 本体リポジトリを参照してください。
