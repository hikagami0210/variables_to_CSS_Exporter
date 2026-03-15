# Figma Variables to CSS Exporter

Figmaのローカルバリアブル（Variables）を抽出し、プロジェクトですぐに使えるCSSカスタムプロパティ（CSS変数）としてエクスポートするFigma向けカスタムプラグインです。

**EnterpriseプランのREST API制限（編集権限がないと叩けない問題）を回避し、Dev Mode（閲覧権限のみ）からでもローカルバリアブルを完全に抽出・コード化するために開発されました。**

## ✨ 主な機能

- **2つの出力フォーマットに対応:** UI上のプルダウンから、プロジェクトに合わせて最適な出力形式を瞬時に切り替え可能。
  - **Tailwind CSS v4 (`@theme`):** 最新のTailwind仕様に完全準拠。出力された `theme.css` を読み込むだけで、`bg-primary` や `p-4` などのユーティリティクラスがゼロコンフィグで利用可能になります。
  - **Standard CSS (`:root`):** 従来のWeb標準に則った汎用的なCSS変数として出力します。
- **Tailwind向けネームスペースの自動最適化:** Figmaのコレクション名や型を自動解析し、Tailwindが認識するプレフィックス（`--color-*`, `--spacing-*`, `--radius-*` など）へ安全にマッピングします。
- **単一ツールで完結:** 外部のStyle DictionaryやREST API、JSONの書き出し処理に依存せず、Figma内で完結。
- **Dev Mode対応:** FigmaのDev Mode（開発モード）のインスペクトパネルから直接シームレスに起動可能。
- **完全なエイリアス解決:** バリアブルの参照（Alias）を再帰的に解決し、CSSの `var(--...)` 構文にマッピング。
- **堅牢な命名の正規化:** スラッシュ、空白、カンマ（`,`）、ドット（`.`）などを安全なケバブケース（kebab-case）のCSS変数名に自動フォーマット。
- **ワンクリックダウンロード:** 変換されたCSSを直接ローカルへダウンロード可能（フォーマットに応じて `theme.css` または `variables.css` として保存されます）。

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
