<p align="center">
  <img src="./docs/logo.png" width="120" height="120" alt="WhiteCat Studio" />
</p>

<h1 align="center">WhiteCat TG Assistant · Commercial Edition</h1>

<p align="center">
  <strong>All-in-One Desktop Telegram Growth System with Multi-Account Management, Campaign Automation, Lead Scraping, AI Group Warming & Full MCP Agent Takeover</strong>
</p>

<p align="center">
  <a href="https://github.com/ChiSonKon/tg-sender-releases/releases/latest"><img alt="Latest Release" src="https://img.shields.io/github/v/release/ChiSonKon/tg-sender-releases?display_name=release&style=for-the-badge&color=1677ff"></a>
  <a href="https://github.com/ChiSonKon/tg-sender-releases/releases"><img alt="Downloads" src="https://img.shields.io/github/downloads/ChiSonKon/tg-sender-releases/total?style=for-the-badge&color=22a06b"></a>
  <img alt="Platform" src="https://img.shields.io/badge/Platform-Windows%20%7C%20macOS-7c3aed?style=for-the-badge">
</p>

<p align="center">
  <strong>English version</strong> | <a href="README.md">中文版</a> | <a href="README_JA.md">日本語版</a>
</p>

---

> 🚀 Current Version: **Commercial v4.0**. This repository is for product introduction, releases, and issue tracking. Commercial source code is proprietary.

---

## 🤖 Model Context Protocol (MCP) & AI Agent Full Takeover

WhiteCat TG Assistant v4.0 natively integrates the **Model Context Protocol (MCP)** standard. Without writing custom glue code, you can easily copy the pre-built MCP configuration to your AI Agents (such as **Google Antigravity, Cursor, Claude Desktop, Windsurf**, etc.). The Agent gains **full control and scheduling capabilities** over the entire Telegram marketing workflow!

### ⚡ Quickstart: 2 Steps to AI Agent Marketing

1. **Download & Launch**: Open the client and navigate to **Settings** ➔ **MCP Service & Agent Configuration**;
2. **Copy Config to Agent**: Click **Copy Configuration** and paste the JSON snippet into your AI Agent's `mcpServers` configuration:

```json
{
  "mcpServers": {
    "whitecat-tg-assistant": {
      "command": "python",
      "args": [
        "<app_directory>/run_mcp_server.py",
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

### 📸 Live Agent Dispatch & Message Delivery

Once configured, instruct your AI Agent in natural language (e.g., *"Send message '1' to https://t.me/oxbaimao using average distribution mode via TG Assistant MCP"*). The Agent orchestrates active accounts and executes real Telegram deliveries instantly!

<p align="center">
  <img src="./docs/mcp_agent_demo.png" alt="MCP Service and Agent Dispatch Demo" width="95%" />
</p>

### 🧩 Automated Join Verification (Captcha) AI Solving Flow

When accounts join groups with active anti-bot protection (`@Shieldy`, `@go365_ai_bot`, `@WeGroupRobot`, etc.), the engine captures deep-link verification challenges, evaluates math problems, clicks confirmation inline buttons, and lifts mutes without human intervention:

<p align="center">
  <img src="./docs/mcp_captcha_flow.png" alt="Group Join Captcha Auto-Solving Sequence Diagram" width="95%" />
</p>

---

## 🎬 Video Demonstrations

### Direct Messaging & Rich Text Demo

https://github.com/user-attachments/assets/d2d45e1f-58b2-499d-973b-a31c802ab19f

### AI Group Warming & Bulk Group Messaging Demo

https://github.com/user-attachments/assets/da417416-df93-4988-9e72-e530873dd4b2

---

## 📥 Download Current Version

Please download the build matching your operating system from [Latest Release](https://github.com/ChiSonKon/tg-sender-releases/releases/latest).

| OS | Supported Devices | Download |
| --- | --- | --- |
| Windows x64 | Windows 10 / 11 | [Download Windows](https://github.com/ChiSonKon/tg-sender-releases/releases/latest/download/WhiteCat-TG-Assistant-Commercial-v4.0-Windows.zip) |
| macOS arm64 | Apple Silicon: M1 / M2 / M3 / M4 | [Download macOS Apple Silicon](https://github.com/ChiSonKon/tg-sender-releases/releases/latest/download/WhiteCat-TG-Assistant-Commercial-v4.0-macOS-arm64.zip) |
| macOS x86_64 | Intel Processor Mac | [Download macOS Intel](https://github.com/ChiSonKon/tg-sender-releases/releases/latest/download/WhiteCat-TG-Assistant-Commercial-v4.0-macOS-x86_64.zip) |

---

## 🌟 v4.0 Major Highlights

1. **18 Full-Featured MCP Marketing Tools**: Direct messages, group broadcasts, lead scraping, bulk force-invites, channel creation, profile modification, warm-up, and bot ecosystem analysis.
2. **Dynamic Group Join Captcha Solver**: Auto-handles Shieldy, MissRose, GroupHelp, Deep-Link verification bots, and arithmetic questions.
3. **Muted & Inactive Account Quarantine**: Probes send permissions, detects SpamBlocks, and safely archives expired sessions into `session_quarantine/`.
4. **SpamBot Full-Text Diagnostics**: Captures raw dialogs from `@SpamBot` and extracts exact UTC release timestamps.
5. **1-Click Profile Cloning & Disguise**: Scrapes active group members and disguises puppet accounts with real avatars and bios.

---

## 🔒 Privacy & Safety Statement

- **100% Local Storage**: All Telegram sessions, proxy credentials, and data remain strictly on your local machine. No cloud uploads.
- **Compliance**: For legitimate, authorized customer outreach and community management only.

---

## 📬 Contact & Support

- **Telegram Support**: [t.me/oxbaimao](https://t.me/oxbaimao)
- **Bug Reports**: [GitHub Issues](https://github.com/ChiSonKon/tg-sender-releases/issues)
- **Releases**: [GitHub Releases](https://github.com/ChiSonKon/tg-sender-releases/releases)

---

<p align="center">
  <strong>White Cat Studio</strong><br>
  <sub>© 2024–2026 White Cat Studio. All rights reserved.</sub>
</p>
