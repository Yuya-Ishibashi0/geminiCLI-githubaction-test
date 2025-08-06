# 定期的なIssueトリアージ (`gemini-issue-scheduled-triage.yml`)

このワークフローは、ラベルがない、またはトリアージが必要とマークされたIssueを定期的にトリアージします。

## トリガー

- **スケジュール実行:** 毎時実行されます (`0 * * * *`)。
- **手動実行 (`workflow_dispatch`):** トリアージプロセスを手動で実行できます。

## 主な機能

- **未トリアージIssueの発見:** ラベルがない、または `status/needs-triage` ラベルが付いているIssueを特定します。
- **一括トリアージ:** 発見されたすべてのIssueを一度の実行で処理します。
- **Gemini連携:** `google-github-actions/run-gemini-cli` アクションを使用して、特定されたIssueに適切なラベルを適用します。
