---
name: tdd-workflow
description: テスト駆動開発ワークフロー
trigger: implement|add feature|fix bug|create|build|修正|実装|追加|作成|構築
---

# TDD ワークフロー

このファイルは TDD ワークフロー全体の **オーケストレーション** だけを担う。各 Phase の詳細ルール・命名規則・AAA・モック方針・禁止事項・出力形式は、対応する Phase 別 skill を **必ず READ** すること。

`.claude/rules/testing/test-philosophy.md` を **必ず READ** し、テスト思想に従うこと。

## 進行ルール

1. **Phase 1** — `tdd-test-case-writer` skill を READ し、テストケースを列挙する。完了後、ユーザーのレビューゲートを挟む。勝手に Phase 2 へ進まない。
1. **Phase 2** — `tdd-test-code-writer` skill を READ し、Phase 1 のケースから 1 つ選んで失敗するテストを書く。`mise run test` で失敗を確認後、ユーザーのレビューゲートを挟む。
1. **Phase 3** — `tdd-implementer` skill を READ し、テストを通す最小実装を書く。`mise run test` でパスを確認する。
1. **Phase 4** — `tdd-refactorer` skill を READ し、テストを保ったままリファクタリングする。完了後、ユーザーのレビューゲートを挟む。

## 制約（全 Phase 共通）

- Phase N を完了するまで Phase N+1 に進まない
- 各 Phase でテスト実行を必ず行う
- テストが失敗したまま次のテストを追加しない
- 各 Phase でレビューゲートが指示されている場合、それに従い勝手に次に進まないこと
