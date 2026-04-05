# ゲーム

## 概要

団体戦の1対戦（`TeamMatchResult`）を構成する1試合の単位。
バドミントンでは1対戦が複数ゲームで構成され、取得ゲーム数の多い方が勝利となる。

コード上は **rubber**（`RubberResult`）という名前で管理される。

## データ構造

```
RubberResult
├── team1PairMemberIds: List<String>?  ← チーム1のペア（メンバーID 2名）
├── team2PairMemberIds: List<String>?  ← チーム2のペア（メンバーID 2名）
└── gameScores: List<GameScore>        ← セットごとのスコアリスト
    └── GameScore = ({int p1, int p2}) ← チーム1得点 / チーム2得点
```

## このアプリでの扱い

- 1対戦は **3ゲーム固定**。`TeamMatchResult.rubbers` は長さ3のリスト。
- 未入力のゲームは `null` で管理される。
- 各ゲームの勝敗は `gameScores` の合計で決まり、チームスコアに集計される。
- ゲームスコアの入力はオーダーが済んでいないと不可。

## 用語対応

| 日本語 | コード上 |
|--------|---------|
| ゲーム | rubber |
| ゲーム結果 | `RubberResult` |
| ゲームのリスト | `TeamMatchResult.rubbers` |
| セットスコア | `GameScore` (`{p1, p2}`) |
