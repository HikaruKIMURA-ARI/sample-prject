---
name: ui-workflow
description: UI 実装スキル。 主にデザイナーがコンポーネントとstories ファイルを実装するときに使う。
trigger: UI|frontend|component|storybook|implement|add feature|fix bug|create|build|修正|実装|追加|作成|構築
---

## ルール

### 新規追加の場合

1. atomic design 単位の UI を `components/atoms, molecules, organisms, templates` に実装すること
2. presentation / container パターンを採用し、純粋な UI コンポーネントを維持すること
3. 1〜2 の `stories.tsx` を作成すること
4. ディレクトリ構造は `.claude/rules/architecture`を参考にし、迷う部分があればユーザーに確認をすること
