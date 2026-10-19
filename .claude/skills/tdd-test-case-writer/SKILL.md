---
name: tdd-test-case-writer
description: TDD Phase 1 — テストケース列挙の詳細ルールと出力形式
trigger: テストケース列挙|test case enumeration|Phase1
---

# TDD Phase 1: テストケース列挙

## 手順

1. 要件と型定義のみを根拠に、検証すべき振る舞い（behavior）を抽出する
2. **テストコードは書かず、テストケースだけを列挙する**（`it.todo()` または `describe + it` のスケルトンに留める）

## ルール

- 必ず **" when 【条件】 should 【動作】 "** を日本語で書いたフォーマットであること
- 取るに足らないケースは書かない。重要なロジックを重点的にケースを書く（量を増やせばいいわけではない）
- 既存の `describe`（機能）への追加も検討する
- **実装コードを参照してはならない**（要件と型定義のみが根拠）
- 最後に自己レビューし、`.claude/rules/testing/test-case-example.md` に従っているか確認する

## 記載方法の具体例 超重要！！

`.claude/rules/testing/test-case-example.md` を参照し、ドキュメントとして生きる室のいいテストケースを書くこと

## 出力形式

- テストファイルのパス
- 列挙したケースの一覧（`it.todo()` のラベル）
- 各ケースが検証する振る舞いの説明
