# Issueの自動トリアージ (`gemini-issue-automated-triage.yml`)

このワークフローは、新しくオープンまたは再オープンされたIssueをGemini CLIを使用して自動的にトリアージします。

## トリガー

- **Issues:** Issueがオープンまたは再オープンされたとき。
- **Issueへのコメント:** 権限のあるユーザーによって`@gemini-cli /triage`を含むコメントが作成されたとき。
- **手動実行 (`workflow_dispatch`):** 特定のIssueを手動でトリアージできます。

## 主な機能

- **自動ラベリング:** Issueのタイトルと本文を分析し、リポジトリに既存のラベルから関連するものを適用します。
- **トリアージの効率化:** Issueの処理後、`status/needs-triage` ラベルを削除します。
- **Gemini連携:** `google-github-actions/run-gemini-cli` アクションを使用してトリアージを実行し、Geminiの自然言語理解能力を活用します。
- **エラーハンドリング:** トリアージ処理が失敗した場合、デバッグのためにアクションログへのリンクを含むコメントをIssueに投稿します。
