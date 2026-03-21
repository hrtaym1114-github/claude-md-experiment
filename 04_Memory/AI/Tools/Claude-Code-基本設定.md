# Claude Code 基本設定

## 概要
Claude CodeはAnthropicの公式CLIツール。ターミナルから直接Claudeと対話しながら開発作業ができる。

## 基本コマンド
- `claude` — 対話モード起動
- `/cost` — トークン消費量確認
- `/help` — ヘルプ表示

## 設定ファイル
- `CLAUDE.md` — プロジェクト固有の設定
- `~/.claude/CLAUDE.md` — グローバル設定
- `.claude/commands/` — カスタムコマンド
- `.claude/rules/` — 条件付きルール

## メモ
- CLAUDE.mdはプロジェクトルートに配置
- サブエージェントでタスク並列化可能
- Hooksで自動処理を追加できる

#ai #tools #claude-code
