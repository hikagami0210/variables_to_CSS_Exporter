# Figma Variables to CSS Exporter

Figmaのローカルバリアブル（Variables）を抽出し、プロジェクトですぐに使えるCSSカスタムプロパティ（CSS変数）としてエクスポートするFigma向けカスタムプラグインです。

**EnterpriseプランのREST API制限（編集権限がないと叩けない問題）を回避し、Dev Mode（閲覧権限のみ）からでもローカルバリアブルを完全に抽出・コード化するために開発されました。**

## ✨ 主な機能

- **単一ツールで完結:** 外部のStyle DictionaryやREST APIに依存せず、Figma内で完結。
- **Dev Mode対応:** FigmaのDev Mode（開発モード）のインスペクトパネルから直接シームレスに起動可能。
- **完全なエイリアス解決:** バリアブルの参照（Alias）を再帰的に解決し、CSSの `var(--...)` 構文にマッピング。
- **モード（テーマ）の自動マッピング:** コレクション内のMode（Light / Darkなど）を自動検知し、`:root` や `[data-theme="dark"]` などのCSSセレクタに振り分け。
- **堅牢な命名の正規化:** スラッシュ、空白、カンマ（`,`）、ドット（`.`）などを安全なケバブケース（kebab-case）のCSS変数名に自動フォーマット。
- **ワンクリックダウンロード:** 変換されたCSSを `.css` ファイルとして直接ローカルへダウンロード可能。

## 🛠 前提条件

- [Node.js](https://nodejs.org/) がインストールされていること
- Figma デスクトップアプリがインストールされていること

## 🚀 セットアップ手順

1. **リポジトリのクローン・準備**

```bash
# プロジェクトディレクトリに移動
cd figma-variables-exporter

# パッケージのインストール（TypeScriptとFigma型定義）
npm install
```
