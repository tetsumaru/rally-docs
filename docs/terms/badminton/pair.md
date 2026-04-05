# ペア

## 概要

1ゲームに出場する2名1組の選手。
オーダー入力時に各ゲームへ割り当てる。

## データ構造

各ゲーム（`RubberResult`）にチームごとのペアが格納される。

```
RubberResult
├── team1PairMemberIds: List<String>?  ← チーム1のペア（メンバーID 2名）
└── team2PairMemberIds: List<String>?  ← チーム2のペア（メンバーID 2名）
```

- `null` はペア未選択（オーダー未入力）を意味する。
- 両チームのペアが揃って初めて「オーダー済」と判定される。

## UI 上の扱い

- オーダー入力ダイアログ（`_TeamOrderDialog`）で、3ゲーム × 2チーム分のペアを選択する。
- 各ペアは2つのドロップダウンで構成され、チームメンバー（`TeamMember`）から選ぶ。
- 結果入力ダイアログではペアは読み取り専用で表示される。

## 用語対応

| 日本語 | コード上 |
|--------|---------|
| ペア | pair |
| ペアのメンバーID | `pairMemberIds` |
| チーム1のペア | `team1PairMemberIds` |
| チーム2のペア | `team2PairMemberIds` |
