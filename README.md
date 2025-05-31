# GitHub Slack File Watcher

特定ディレクトリの変更を検知してSlackに通知するGitHub Actionsワークフローです。

## ワークフロー

### target-changes-notification.yml
- **トリガー**: mainブランチへのpush時
- **動作**: `target`ディレクトリ配下のファイルに変更があった場合のみSlackに通知
- **通知内容**: 
  - 変更されたファイルの一覧
  - リポジトリ情報、コミット情報、実行者

### push-notification.yml（無効化中）
- Claudeを使用してコミット内容を要約してSlackに通知する機能

## セットアップ

GitHub Secretsに以下を設定：
- `SLACK_URL`: SlackのWebhook URL
- `ANTHROPIC_API_KEY`: Claude APIキー（push-notification用、現在無効化中）

## 使用方法

1. `target`ディレクトリ配下にファイルを配置
2. mainブランチにpushすると自動的に通知が送信されます