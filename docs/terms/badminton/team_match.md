# 団体戦

## 概要

チーム対チームで行う試合形式。複数のゲームで構成され、取得ゲーム数の多い方が勝利となる。
個人戦（`League`）とは異なり、チームとしてエントリーし、各ゲームにペアを割り当てる。

## データ構造

```
TeamMatchResult
├── id              ← leagueId + team1Id + team2Id から生成（辞書順ソート）
├── tournamentId
├── teamLeagueId    ← 所属リーグの ID
├── team1Id
├── team2Id
├── rubbers[]       ← ゲームのリスト（長さ3、未入力は null）
├── teamScore1      ← チーム1の取得ゲーム数
└── teamScore2      ← チーム2の取得ゲーム数
```

## 判定ロジック

| フラグ | 内容 |
|--------|------|
| `hasOrder` | いずれかのゲームにペア選択が入力されている |
| `hasResults` | いずれかのゲームにスコアが入力されている |
| `winnerTeamId` | teamScore が2以上のチームの ID（未確定は null） |

## このアプリでの扱い

- 総当たりの組み合わせは `generateTeamRoundRobin()` で自動生成される。
- 入力フロー: オーダー入力 → 結果入力 の順。オーダーなしでは結果入力不可。
- オーダー削除時は結果も合わせて削除される。
- 結果削除時はオーダーを残してスコアのみクリアされる。

## 用語対応

| 日本語 | コード上 |
|--------|---------|
| 団体戦 | TeamMatch |
| 対戦結果 | `TeamMatchResult` |
| チームスコア | `teamScore1` / `teamScore2` |
| 結果入力済フラグ | `TeamMatchResult.hasResults` |
