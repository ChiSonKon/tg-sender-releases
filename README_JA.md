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

## 🤖 0ステップ超簡単導入：AIエージェントに自動ダウンロード＆設定をおまかせ

手動でのダウンロードや設定は**一切不要**です！以下のプロンプトをそのまま AI エージェント（**Google Antigravity、Cursor、Claude Desktop、Windsurf** 等）に貼り付けて送信するだけです：

```text
GitHub リポジトリ https://github.com/ChiSonKon/tg-sender-releases から最新の Telegram 集客アシスタント商用版 (v4.0) を自動ダウンロード・展開し、現在の MCP サーバー設定にフル権限で登録してください。完了後、利用可能な18種類の集客機能を報告してください。
```

> 💡 **エージェントが自動で行うこと**:
> 1. GitHub Releases よりお使いのOSに最適な最新版を自動取得・展開；
> 2. 現在の AI 環境に MCP 集客サービスを自動登録；
> 3. 準備完了！あとは「ターゲットにメッセージを送信して」「グループ参加認証を自動解除して」と日本語で指示するだけです。

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
