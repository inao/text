# 使用方法ガイド

執筆ガイドライン改善システムの詳細な使用方法を説明します。

## 目次

1. [システム概要](#システム概要)
2. [著者向け使用方法](#著者向け使用方法)
3. [編集者向け使用方法](#編集者向け使用方法)
4. [システム管理者向け使用方法](#システム管理者向け使用方法)
5. [段階別チェック手順](#段階別チェック手順)
6. [Cursorでの自動チェック](#cursorでの自動チェック)
7. [トラブルシューティング](#トラブルシューティング)

## システム概要

このシステムは、Cursorが理解しやすい執筆ガイドラインを提供し、著者の原稿を自動チェック・修正提案することを目的としています。

### 主要コンポーネント

- **cursor-rules/**: Cursorが参照するルールファイル
- **checklists/**: 著者が自己チェックするためのチェックリスト
- **writing-guide-cursor.md**: 元の執筆ガイドライン

### ファイル構成

```
cursor/
├── cursor-rules/
│   ├── outline-rules.md      # 見出し構造ルール
│   ├── sentence-rules.md     # 文章構成ルール
│   ├── notation-rules.md     # 表記・約物ルール
│   ├── patterns.md           # 自動検出・修正パターン
│   ├── error-levels.md       # エラーレベル分類
│   ├── correction-examples.md # 修正例
│   ├── before-after-examples.md # Before/After例
│   └── README.md             # ルールファイル説明
├── checklists/
│   ├── outline-checklist.md  # 見出しチェック
│   ├── sentence-checklist.md # 文章チェック
│   ├── notation-checklist.md # 表記チェック
│   └── README.md             # チェックリスト説明
├── plan.md                   # 改善計画
├── test-results.md           # テスト結果
├── test-sample.md            # テストサンプル
├── checklist-test-results.md # チェックリストテスト結果
├── writing-guide-cursor.md   # 元の執筆ガイドライン
└── USAGE.md                  # このファイル
```

## 著者向け使用方法

### 基本的な使用手順

1. **執筆開始前**: チェックリストを確認
2. **執筆中**: 段階的にチェック
3. **推敲時**: 全チェックリストを実行
4. **最終確認**: 表記・約物の最終チェック

### 執筆段階別チェック

#### 1. アウトライン作成時

```bash
# 見出し構造のチェック
cat checklists/outline-checklist.md
```

**確認ポイント:**
- 見出しのストーリー性
- 説明的見出しの命名
- 見出しの連続回避
- 不適切な見出し命名の回避

#### 2. 本文執筆時

```bash
# 文章構成のチェック
cat checklists/sentence-checklist.md
```

**確認ポイント:**
- 語順・読点のルール
- トピックセンテンス
- 段落構成
- 冗長表現の簡略化
- 指示代名詞の使用

#### 3. 推敲時

```bash
# 全チェックリストの実行
cat checklists/*.md
```

**確認ポイント:**
- 全チェックリストの自動検出項目
- 冗長表現の簡略化
- 約物・記号の使用基準

#### 4. 最終確認時

```bash
# 表記・約物の最終チェック
cat checklists/notation-checklist.md
```

**確認ポイント:**
- 約物使用基準の確認
- 表記統一のチェック
- 法人表記の統一確認
- 数字表記の統一確認

### Cursorでの自動チェック

1. **Cursorで原稿ファイルを開く**
2. **ルールファイルを参照**
   ```bash
   # ルールファイルの確認
   cat cursor-rules/patterns.md
   ```
3. **自動チェックを実行**
   - エラー・警告・情報レベルの修正提案を確認
4. **具体的な修正例を参考に修正**
   ```bash
   # 修正例の確認
   cat cursor-rules/before-after-examples.md
   ```

## 編集者向け使用方法

### チェックリストによる確認

```bash
# 著者の原稿をチェックリストで確認
# 各チェックリストの項目を順番に確認
cat checklists/outline-checklist.md
cat checklists/sentence-checklist.md
cat checklists/notation-checklist.md
```

### サンプルファイルとの比較

```bash
# 良いお手本との比較
# sampleフォルダの例文を参考にする
```

### エラーレベルの確認

```bash
# エラーレベルの分類を確認
cat cursor-rules/error-levels.md
```

**エラーレベル:**
- **エラー**: 必ず修正が必要
- **警告**: 可能な範囲で修正推奨
- **情報**: 参考程度

## システム管理者向け使用方法

### ルールの更新

```bash
# ルールファイルの更新
vim cursor-rules/patterns.md
vim cursor-rules/*-rules.md
```

### チェックリストの更新

```bash
# チェックリストの更新
vim checklists/*-checklist.md
```

### テストの実行

```bash
# サンプルファイルでの動作確認
# テスト結果の確認
cat test-results.md
cat checklist-test-results.md
```

## 段階別チェック手順

### 高優先度（執筆中）

1. **見出し構造の基本ルール**
   - ストーリー性の確保
   - 説明的見出しの命名

2. **文章構成の基本ルール**
   - 語順・読点のルール
   - トピックセンテンス

3. **冗長表現の簡略化**
   - 自動検出可能なパターン

### 中優先度（推敲時）

1. **約物・記号の使用基準**
   - カギカッコの使用基準
   - クエスチョンマークの使用基準

2. **表記・用語の統一**
   - 法人表記の統一
   - 数字表記の統一

3. **自動検出可能なパターン**
   - 正規表現による検出

### 低優先度（最終確認時）

1. **細かな表記の統一**
   - 参考情報レベルの項目

2. **参考情報の確認**
   - 追加の改善点

## Cursorでの自動チェック

### 設定手順

1. **Cursorでプロジェクトを開く**
2. **ルールファイルのパスを設定**
3. **自動チェック機能を有効化**

### チェック実行

```bash
# ルールファイルの確認
cat cursor-rules/patterns.md

# エラーレベルの確認
cat cursor-rules/error-levels.md

# 修正例の確認
cat cursor-rules/correction-examples.md
```

### 修正提案の確認

1. **エラーレベルの確認**
   - エラー: 必ず修正
   - 警告: 可能な範囲で修正
   - 情報: 参考程度

2. **具体的な修正例の確認**
   ```bash
   cat cursor-rules/before-after-examples.md
   ```

3. **段階的な修正手順の実行**

## トラブルシューティング

### よくある問題

#### Q: Cursorがルールを認識しない

**解決方法:**
1. ルールファイルの存在確認
   ```bash
   ls -la cursor-rules/
   ```
2. 正規表現パターンの構文チェック
   ```bash
   cat cursor-rules/patterns.md
   ```
3. Cursorの設定確認

#### Q: チェックリストの項目が多すぎる

**解決方法:**
1. 執筆段階別のチェック項目を確認
   ```bash
   cat checklists/README.md
   ```
2. 優先度の高い項目から確認
3. 段階的チェックの実施

#### Q: 修正提案が具体的でない

**解決方法:**
1. `before-after-examples.md`を参照
   ```bash
   cat cursor-rules/before-after-examples.md
   ```
2. 具体的な修正例を確認
   ```bash
   cat cursor-rules/correction-examples.md
   ```

### サポート情報

- **ログファイル**: `test-results.md`, `checklist-test-results.md`
- **参考資料**: `cursor-rules/README.md`, `checklists/README.md`
- **更新履歴**: `plan.md`

## 更新とメンテナンス

### 定期的なメンテナンス

1. **週次**: テストの実行
2. **月次**: ルールの見直し
3. **四半期**: システム全体の確認

### バックアップ

1. **Gitでのバージョン管理**
2. **重要なファイルのバックアップ**
3. **設定ファイルのバックアップ**

## 問い合わせ先

問題が解決しない場合は、以下の情報を添えて問い合わせてください：

1. 発生した問題の詳細
2. 実行したコマンド
3. エラーメッセージ
4. システム環境情報
5. 再現手順 