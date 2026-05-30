# 🐱 WhiteCat TG Bulk Assistant (白猫工作室 Telegram 智能群发与裂变营销控制台)

[![Version](https://img.shields.io/badge/Version-v1.0.0--stable-blue?style=for-the-badge&logo=telegram)](https://github.com/ChiSonKon/tg-sender-releases/releases)
[![License](https://img.shields.io/badge/License-Proprietary-red?style=for-the-badge)](https://t.me/oxbaimao)
[![Platform](https://img.shields.io/badge/Platform-Windows%20%7C%20Linux%20%7C%20macOS-brightgreen?style=for-the-badge&logo=windows)](https://github.com/ChiSonKon/tg-sender-releases/releases)

> **声明：** 本仓库为 **WhiteCat TG Bulk Assistant** 官方唯一发布与分发仓库。由于商业闭源保护，本仓库**仅托管已编译、经过 Cython 二进制加密及 PyInstaller 混淆保护的各平台分发包**，不包含产品源代码。下载安装包请直接前往 [Releases 页面](https://github.com/ChiSonKon/tg-sender-releases/releases)。

---

## ⚡ 为什么选择 WhiteCat TG Bulk Assistant？

在 Telegram 营销生态中，传统的群发工具往往面临 **“单账号效率低”、“极易被判定滥用封号”、“群组管理员秒删秒踢”** 以及 **“功能单一无法形成闭环”** 等痛点。

**WhiteCat TG Bulk Assistant** 是一款革命性的、跨平台企业级 Telegram 营销与裂变自动化控制台。它不仅是一个群发工具，更是一个将 **多账号高并发管理、高精度成员采集、物理防封、防删撤回、安全格式转换以及 AI 智能炒群** 融为一体的终极营销武器。

```
                    ┌──────────────────────────────┐
                    │  WhiteCat TG Bulk Assistant  │
                    └──────────────┬───────────────┘
                                   │
         ┌─────────────────────────┼─────────────────────────┐
         ▼                         ▼                         ▼
   【高并发群发矩阵】         【防风控防删黑科技】       【精准引流与智能化】
   - 多账号高并发连接         - 自动假消息替换机制       - 目标群组成员高精采集
   - 独立代理绑定(SOCKS5)     - 自动消息延时撤回防留底   - 养号/暖号/模拟浏览
   - 文本/HTML/图片/文件      - Session/TData格式互转   - AI 自动智能对话炒群
```

---

## 🔥 核心震撼功能清单

### 1️⃣ 企业级多账号并发矩阵
*   **无限账号载入**：支持同时导入、连接、管理成百上千个 Telegram 账号（支持 `.session` 及 `TData` 格式）。
*   **独立代理绑定 (SOCKS5)**：每个账号均可绑定独立的代理 IP，支持批量自动轮询与分流，彻底规避因 IP 关联导致的成批封号。
*   **可视化在线看板**：实时监控每一个账号的在线/离线/风控状态。

### 2️⃣ 物理防封与防踢黑科技
*   **假消息替换 (Fake Message Replacement)**：发送广告消息后，可自动将其替换为正常的问候或空白消息，规避群组内监测机器人的关键词自动封号。
*   **定时自动撤回 (Auto Recall)**：发送消息后，在设定的几秒或几分钟内自动物理撤回，既保证了曝光率，又让群管理员无法留底举报。
*   **高精度智能延时**：内置防指纹延时算法，模拟真人打字与发送间隔，强力对抗 Telegram 官方的风控机制。

### 3️⃣ 高精度成员采集与精准提取
*   **一键导出 CSV**：输入目标公开或私有群组链接，秒级提取出所有成员信息（用户名、ID、姓名、最后在线时间）。
*   **活跃度筛选**：支持按“最近在线时间”过滤，只提取最近 24 小时或 3 天内活跃的真实用户，杜绝僵尸号。

### 4️⃣ 安全与格式转换中心
*   **TData ↔ Session 双向无损转换**：市面上首款完美兼容两端格式的转换工具。无需重新登录，即可将买来的 TData 格式账号转为 API 专用的 Session，或反向生成可在电脑端直接打开的 TData，保护您的账号资产。

### 5️⃣ AI 炒群与养号暖号
*   **AI 智能对话联动**：基于 AI 的群聊模拟，多账号在群内自动进行上下文关联的真实对话聊天，快速炒热群组氛围。
*   **自动养号暖号**：模拟真人自动加入目标群组、浏览消息、点击按钮，极大提升新号的账号权重与抗封等级。

---

## 📊 三大版本功能对比矩阵

| 功能模块 | 基础版 (Basic) | 进阶版 (Advanced) | 完全版 (Complete) |
| :--- | :---: | :---: | :---: |
| **多账号管理与 Session 导入** | ✅ | ✅ | ✅ |
| **独立代理绑定与状态看板** | ✅ | ✅ | ✅ |
| **统一群发 (群组/私信/对话)** | ✅ | ✅ | ✅ |
| **高精成员采集 (导出 CSV)** | ✅ | ✅ | ✅ |
| **账号资料批量修改** | ✅ | ✅ | ✅ |
| **物理防封 (假消息替换/自动撤回)**| ✅ | ✅ | ✅ |
| **批量自动举报 (商业对抗)** | ❌ | ✅ | ✅ |
| **养号暖号机制 (加入/浏览)** | ❌ | ✅ | ✅ |
| **TData / Session 格式安全互转**| ❌ | ✅ | ✅ |
| **AI 智能炒群联动** | ❌ | ❌ | ✅ |
| **多线程并发速度上限** | 中等 | 高 | 无限制 |
| **安全防护级别** | 标准加密 | 高级二进制加密 | 高级二进制加密 |

---

## 📥 安装与下载指引

1. 前往本仓库的 [Releases 页面](https://github.com/ChiSonKon/tg-sender-releases/releases) 下载适合您操作系统的最新版压缩包：
   * **Windows 平台**：`WhiteCat_TG_Assistant_XXX_Windows.zip` (解压双击即可运行)
   - **Linux 平台**：`WhiteCat_TG_Assistant_XXX_Linux.tar.gz`
   - **macOS 平台**：`WhiteCat_TG_Assistant_XXX_Mac.zip`
2. 解压下载的压缩包。
3. 双击 `WhiteCat_TG_Assistant.exe`（Windows）或执行对应启动程序，软件将自动启动。

---

## 🔑 激活与授权购买

本软件启动时会根据您本地的硬件配置（CPU、主板 UUID）生成唯一的 **本地机器码（一机一码绑定）**。

请复制软件启动弹窗中的“机器码”，联系官方客服获取专属激活卡密。

### 💬 唯一官方联络通道
*   **Telegram 官方客服**: [https://t.me/oxbaimao](https://t.me/oxbaimao)
*   **官方 Telegram Channel**: [@oxbaimao_channel](https://t.me/oxbaimao) (关注频道获取软件更新与营销技巧)

> **⚠️ 注意：** 官方客服绝对不会主动私聊您，请认准唯一用户名 `@oxbaimao`，谨防上当受骗！
