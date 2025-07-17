# 執筆ガイドライン改善計画

## 概要

Cursorが理解しやすい執筆ガイドラインに改善する。

## 必ず守ること

- [Conventional Commits](https://www.conventionalcommits.org/ja/v1.0.0/)を行う
- `plan.md`のチェックリストを一つずつ行っていく。一度に2つまとめて行うなどしない
- `writing-guide-cursor.md`の1見出し分ずつ改善していく。一度に2つの見出し分の改善をまとめて行うなどしない
- 良いお手本の例が必要なときは、`sample`フォルダから探す
- `sample`フォルダの内容は変更しない

## 背景
私はプロの編集者です。
プログラミング系の雑誌や書籍の編集を20年以上にわたって行っています。

私が編集者として著者に提示する執筆ガイドラインが `writing-guide-cursor.md` です。
著者には、 `writing-guide-cursor.md` に則って執筆してもらいます。

## 目的
著者が書いた原稿が `writing-guide-cursor.md` に則っているかどうかをCursorでチェックし、修正を提案してほしいです。

ただ、 `writing-guide-cursor.md` のままだと、Cursorは則っているかどうかのチェックや修正提案を上手に行ってくれません。

Cursorが理解しやすいように変更したいです。

## 目標

- Cursorが自動チェックしやすい形式にする
- 著者が自己チェックしやすくする
- 修正提案を具体的にする

## 改善タスクリスト

### Phase 1: 現在のファイルの分析・整理
- [x] 現在の`writing-guide-cursor.md`の内容をカテゴリ別に分類する
- [x] 自動検出可能なパターンを抽出する
- [x] 正規表現パターンを整理する
- [x] チェック項目を明確化する

### Phase 2: ディレクトリ構造の作成
- [x] `cursor-rules/`ディレクトリを作成する
- [x] `checklists/`ディレクトリを作成する
- [x] 各ファイルの役割を定義する

### Phase 3: ルールファイルの作成
- [x] `cursor-rules/outline-rules.md`を作成（見出し構造ルール）
- [x] `cursor-rules/sentence-rules.md`を作成（文章構成ルール）
- [x] `cursor-rules/notation-rules.md`を作成（表記・約物ルール）
- [x] `cursor-rules/patterns.md`を作成（検出・修正パターン）

### Phase 4: チェックリストの作成
- [x] `checklists/outline-checklist.md`を作成（見出しチェック）
- [x] `checklists/sentence-checklist.md`を作成（文章チェック）
- [x] `checklists/notation-checklist.md`を作成（表記チェック）

### Phase 5: 自動検出パターンの実装
- [x] 冗長表現の検出パターンを実装
- [x] 見出し構造の検出パターンを実装
- [x] 文章構成の検出パターンを実装
- [x] 表記・約物の検出パターンを実装

### Phase 6: 修正提案システムの構築
- [x] エラー・警告レベルの分類を定義する
- [x] 具体的な修正例を豊富に追加する
- [ ] Before/After形式の例文を作成する

### Phase 7: 統合・テスト
- [ ] 各ファイル間の整合性を確認する
- [ ] サンプルファイルでの動作確認を行う
- [ ] チェックリストの動作確認を行う

### Phase 8: ドキュメント整備
- [ ] 使用方法の説明を追加する
- [ ] トラブルシューティングガイドを作成する
- [ ] 更新履歴を記録する

### Phase 9: 最終確認
- [ ] 全体の構造をレビューする
- [ ] 必要に応じて調整を行う
- [ ] 完成版として確定する
