# claude-md-experiment

CLAUDE.mdの設計がClaude Codeの挙動にどう影響するかを検証したBefore/After実験リポジトリです。

## 背景

半年以上Claude Codeを使い、機能追加のたびに後付けしてきたCLAUDE.mdを、[nogataka氏の設計原則](https://qiita.com/nogataka/items/1ad4e4ccaf47816c63e0)に基づいて体系的に再設計しました。

Vault構造は[akira_papa_IT氏の無料セミナー「Cursor×Obsidian エンジニア目線で使うObsidian知識管理術」](https://x.com/akira_papa_IT/status/1988025916333977810)で紹介された知識管理手法をベースにしています。

## 実験内容

同じ7つのタスクをBefore版/After版のCLAUDE.mdで実行し、5軸（構造・正確性・完全性・自律性・メタデータ）で比較しました。

### 結果

- 全体スコア: **3.66 → 4.86（+33%）**
- AIの「迷い」: **12回 → 1回（-92%）**

### Before版の問題点

- CLAUDE.mdに全ルールを1ファイルに詰め込み（ファット状態）
- `.claude/rules/` 未使用
- スコアリング基準の矛盾
- テンプレート不足
- セッション案内のフォーマット未定義

### After版の改善

- CLAUDE.mdを「意思決定情報」に絞り込み
- `.claude/rules/` に4つのルールファイルを分離
- スコアリング基準を一元化
- テンプレート・フォールバック戦略を追加

## コミット履歴

```
c210ea2 Before版: 後付けで積み上がったCLAUDE.md（ファット状態）
592562a After版: nogataka原則でCLAUDE.mdを3層分離
```

`git diff HEAD~1` でBefore→Afterの差分を確認できます。

## 実験結果レポート

- `experiment-results-before.md` — Before版の全タスク実行結果
- `experiment-results-after.md` — After版の全タスク実行結果（Before比較付き）

## 自分で試す

1. このリポジトリをクローン
2. `git checkout HEAD~1` でBefore版に切り替え
3. Claude Codeで7つのタスクを実行
4. `git checkout master` でAfter版に切り替え
5. 同じタスクを実行して比較

## 注意事項

- 本実験のスコアリングはAI（Claude Opus 4.6）による自己評価に基づいています
- 厳密な統計的測定ではなく、定性的な比較実験です
- LLMの出力は非決定的なため、再現時にスコアが多少変動する可能性があります

## クレジット

- **Vault構造**: [akira_papa_IT](https://x.com/akira_papa_IT) — 「Cursor×Obsidian エンジニア目線で使うObsidian知識管理術」セミナー
- **CLAUDE.md設計思想**: [nogataka](https://qiita.com/nogataka) — 「CLAUDE.mdを設計するとClaude Codeの生産性が別物になる」
- **Before/After実験**: [ayumu](https://github.com/hrtaym1114-github)

## License

MIT
