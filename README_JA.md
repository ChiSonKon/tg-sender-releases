<p align="center">
  <img src="./docs/logo.png" width="120" height="120" alt="WhiteCat Studio" />
</p>

<h1 align="center">WhiteCat TG 自動集客アシスタント · コマーシャル版</h1>

<p align="center">
  <strong>複数アカウント管理・メッセージ配信・リード収集・AIグループ自動育成・MCP AIエージェント完全連携の統合デスクトップシステム</strong>
</p>

<p align="center">
  <a href="https://github.com/ChiSonKon/tg-sender-releases/releases/latest"><img alt="Latest Release" src="https://img.shields.io/github/v/release/ChiSonKon/tg-sender-releases?display_name=release&style=for-the-badge&color=1677ff"></a>
  <a href="https://github.com/ChiSonKon/tg-sender-releases/releases"><img alt="Downloads" src="https://img.shields.io/github/downloads/ChiSonKon/tg-sender-releases/total?style=for-the-badge&color=22a06b"></a>
  <img alt="Platform" src="https://img.shields.io/badge/Platform-Windows%20%7C%20macOS-7c3aed?style=for-the-badge">
</p>

<p align="center">
  <a href="README_EN.md">English version</a> | <a href="README.md">中文版</a> | <strong>日本語版</strong>
</p>

---

> 🚀 現在のバージョン：**コマーシャル版 v4.0**。本リポジトリは製品案内、リリース配布、フィードバック専用です。ソースコードは非公開です。

---

## ⚡ 最速セットアップ：ローカル AI エージェント一括自動設定（拒否トラブル完全回避・100%成功）

### 方法 A（最もおすすめ · ダブルクリックするだけ）：同梱の自動設定スクリプト
リリースパッケージをダウンロードして展開後、**フォルダ内のスクリプトをダブルクリックして実行するだけ**です：
- **Windows ユーザー**：`一键配置本机所有AI_Agent.bat` をダブルクリック
- **macOS ユーザー**：`一键配置本机所有AI_Agent.command` をダブルクリック

> 🚀 **全自動検出と安全マージ**：
> - Python のインストール不要で、PC にインストールされている主要 AI エージェント（**OpenAI Codex、Claude Desktop、Cursor、Google Antigravity、Windsurf、VS Code Cline / Roo-Code**）を自動検出；
> - 既存の設定を自動バックアップしながら、MCP サーバー設定を安全に統合；
> - **「Codex や Claude などのエージェントにプロンプトを送ってもシステム設定の変更を拒否される」問題を完全に回避できます！**

---

### 方法 B（アプリ内設定）：設定画面からワンクリック登録
獲客アシスタント本体をすでに起動している場合：
1. 【**設定**】➔【**🔌 MCP サービスと Agent 設定**】タブを開きます；
2. 【**⚡ ローカルの全 AI エージェントを一括自動検出・設定**】ボタンをクリック；
3. ポップアップで検出結果と設定パスを確認できます。対象エージェントを再起動またはリロードすれば、18 種類の自動化ツールが即座に使用可能になります！

---

### 方法 C（プロンプトによる導入）：エージェントに完全なファイル・ターミナル権限がある場合
ご利用のエージェントがローカルファイルの編集やダウンロードに対応している場合は、以下のプロンプトをそのまま送信することも可能です：

```text
GitHub リポジトリ https://github.com/ChiSonKon/tg-sender-releases から最新の Telegram 集客アシスタント商用版 (v4.0) を自動ダウンロード・展開し、現在の MCP サーバー設定にフル権限で登録してください。完了後、利用可能な18種類の集客機能を報告してください。
```

> 💡 **エージェントが自動で行うこと**:
> 1. GitHub Releases よりお使いのOSに最適な最新版を自動取得・展開；
> 2. 現在の AI 環境に MCP 集客サービスを自動登録；
> 3. 準備完了！あとは「ターゲットにメッセージを送信して」「グループ参加認証を自動解除して」と指示するだけです。

---

### 📸 AI エージェント自動配信の実況画面

設定後、AI エージェントに自然言語で指示するだけで、自動でアカウントを切り替えて配信を実行します。

<p align="center">
  <img src="./docs/mcp_agent_demo_v4.png" alt="MCP サービスとエージェント連携画面" width="95%" />
</p>

### 🧩 グループ参加時ロボット認証（Captcha）の自動解除フロー

Bot認証（`@Shieldy`, `@go365_ai_bot`, `@WeGroupRobot` 等）が有効なグループに参加した場合も、システムが即座に算術問題を計算し、インラインボタンを押してミュートを自動解除します。

<p align="center">
  <img src="./docs/mcp_captcha_flow_v4.png" alt="参加認証自動解除シーケンス図" width="95%" />
</p>

---

<details>
<summary><strong>🛠️ 開発者向け：手動 MCP 設定（クリックして展開）</strong></summary>

```json
{
  "mcpServers": {
    "whitecat-tg-assistant": {
      "command": "python",
      "args": [
        "<アプリ展開パス>/run_mcp_server.py",
        "--stdio",
        "--allow-writes",
        "--connect-accounts"
      ],
      "env": {
        "PYTHONIOENCODING": "utf-8",
        "PYTHONDONTWRITEBYTECODE": "1"
      }
    }
  }
}
```
</details>

---

## 🎬 デモ動画

### 個別ダイレクトメッセージ＆リッチテキスト

https://github.com/user-attachments/assets/d2d45e1f-58b2-499d-973b-a31c802ab19f

### AI グループ自動育成＆グループ一斉配信

https://github.com/user-attachments/assets/da417416-df93-4988-9e72-e530873dd4b2

---

## 📥 ダウンロード

[Latest Release](https://github.com/ChiSonKon/tg-sender-releases/releases/latest) よりお使いのOSに合ったパッケージをダウンロードしてください。

| OS | 対象デバイス | ダウンロード |
| --- | --- | --- |
| Windows x64 | Windows 10 / 11 | [Windows 版](https://github.com/ChiSonKon/tg-sender-releases/releases/latest/download/WhiteCat-TG-Assistant-Commercial-v4.0-Windows.zip) |
| macOS arm64 | Apple Silicon: M1 / M2 / M3 / M4 | [macOS Apple Silicon 版](https://github.com/ChiSonKon/tg-sender-releases/releases/latest/download/WhiteCat-TG-Assistant-Commercial-v4.0-macOS-arm64.zip) |
| macOS x86_64 | Intel Mac | [macOS Intel 版](https://github.com/ChiSonKon/tg-sender-releases/releases/latest/download/WhiteCat-TG-Assistant-Commercial-v4.0-macOS-x86_64.zip) |

---

## 📬 お問い合わせ

- **公式 Telegram サポート**: [t.me/oxbaimao](https://t.me/oxbaimao)
- **不具合・要望**: [GitHub Issues](https://github.com/ChiSonKon/tg-sender-releases/issues)

---

<p align="center">
  <strong>White Cat Studio</strong><br>
  <sub>© 2024–2026 White Cat Studio. All rights reserved.</sub>
</p>
