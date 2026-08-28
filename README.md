<p align="center">
  <img src="./docs/logo.png" width="120" height="120" alt="白猫工作室" />
</p>

<h1 align="center">白猫工作室 TG 自动获客助手 · 商业版</h1>

<p align="center">
  <strong>多账号管理、消息运营、线索采集、AI 炒群与 MCP 智能体协议深度接管的一体化桌面营销系统</strong>
</p>

<p align="center">
  <a href="https://github.com/ChiSonKon/tg-sender-releases/releases/latest"><img alt="Latest Release" src="https://img.shields.io/github/v/release/ChiSonKon/tg-sender-releases?display_name=release&style=for-the-badge&color=1677ff"></a>
  <a href="https://github.com/ChiSonKon/tg-sender-releases/releases"><img alt="Downloads" src="https://img.shields.io/github/downloads/ChiSonKon/tg-sender-releases/total?style=for-the-badge&color=22a06b"></a>
  <img alt="Platform" src="https://img.shields.io/badge/Platform-Windows%20%7C%20macOS-7c3aed?style=for-the-badge">
</p>

<p align="center">
  <a href="README_EN.md">English version</a> | <strong>中文版</strong> | <a href="README_JA.md">日本語版</a>
</p>

---

> 🚀 当前版本：**商业版 v4.0**。本仓库用于产品介绍、安装包发布和问题反馈，不公开商业版闭源业务代码。

---

## 🤖 0 步骤极简上手：让 AI Agent 帮你自动下载与配置（面向完全小白）

您**无需手动下载安装包，也无需手动配置任何繁琐文件**！只需将下方这段【智能体提示词】直接复制发送给您的 AI Agent（支持 **Google Antigravity、Cursor、Claude Desktop、Windsurf** 等）：

```text
帮我从 GitHub 仓库 https://github.com/ChiSonKon/tg-sender-releases 自动下载最新的 Telegram 获客助手商业版（v4.0），解压并自动配置到当前系统的 MCP 服务中（开启全功能读写授权）。配置完成后，向我汇报你可以调度的 18 项 Telegram 自动化获客功能。
```

> 💡 **Agent 自动执行流程**：
> 1. AI Agent 自动访问 GitHub Releases 下载适配您系统的最新版程序并解压；
> 2. AI Agent 自动将 MCP 获客服务注册至当前环境；
> 3. 配置就绪后，您只需向 Agent 发送自然语言指令（例如：*“帮我向目标用户/群组发信”*、*“帮我采集群成员并自动伪装”*、*“帮我加入群组并自动破解人机验证”*），Agent 将全自动调度执行！

---

### 📸 AI Agent 自动化调度发信实况演示

配置完成后，AI Agent 即可直接调度 Telegram 托管账号执行真实触达与消息分发：

<p align="center">
  <img src="./docs/mcp_agent_demo_v4.png" alt="MCP 服务与 Agent 调度发信实况" width="95%" />
</p>

### 🧩 进群动态人机验证（Captcha）AI 协同自动破解流程

当账号加入开启了防机器人验证（如 `@Shieldy`、`@go365_ai_bot`、`@WeGroupRobot` 等）的群组时，系统将毫秒级捕获私聊 Deep-Link 或群内挑战题目，自动求解数学题、点击确认按钮并解除禁言，全流程无需人工干预：

<p align="center">
  <img src="./docs/mcp_captcha_flow_v4.png" alt="进群动态验证与人机验证破解时序图" width="95%" />
</p>

---

<details>
<summary><strong>🛠️ 进阶开发者：手动配置 MCP 指南（点击展开）</strong></summary>

如果您习惯手动配置，也可以手动下载解压后，将以下标准配置添加到 AI Agent 的 `mcpServers` 中：

```json
{
  "mcpServers": {
    "whitecat-tg-assistant": {
      "command": "python",
      "args": [
        "<软件解压路径>/run_mcp_server.py",
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

## 🎬 视频演示

### 私信群发与富文本演示

https://github.com/user-attachments/assets/d2d45e1f-58b2-499d-973b-a31c802ab19f

### AI 炒群与群组群发演示

https://github.com/user-attachments/assets/da417416-df93-4988-9e72-e530873dd4b2

---

## 📥 当前版本下载

请从 [Latest Release](https://github.com/ChiSonKon/tg-sender-releases/releases/latest) 下载与设备匹配的版本。

| 系统 | 适用设备 | 下载 |
| --- | --- | --- |
| Windows x64 | Windows 10 / 11 | [下载 Windows](https://github.com/ChiSonKon/tg-sender-releases/releases/latest/download/WhiteCat-TG-Assistant-Commercial-v4.0-Windows.zip) |
| macOS arm64 | Apple Silicon：M1 / M2 / M3 / M4 | [下载 macOS Apple Silicon](https://github.com/ChiSonKon/tg-sender-releases/releases/latest/download/WhiteCat-TG-Assistant-Commercial-v4.0-macOS-arm64.zip) |
| macOS x86_64 | Intel 处理器 Mac | [下载 macOS Intel](https://github.com/ChiSonKon/tg-sender-releases/releases/latest/download/WhiteCat-TG-Assistant-Commercial-v4.0-macOS-x86_64.zip) |

> 🔧 **2026-08-29 更新**：v4.0 商业版全新发布！深度集成 MCP 智能体 18 项全能获客工具池、动态进群人机验证自动破解、群发禁言与失效账号安全隔离治理以及 SpamBot 全文深度诊断。

---

## 🌟 v4.0 重磅新增与特性

### 1. 🤖 MCP 智能体协议 18 项全功能获客工具池
- **全功能调度**：覆盖单发/群发私聊与群消息、群成员采集、批量强拉、超级群/频道创建与改名、个人主页挂载、账号资料修改、智能养号、机器人深度探查与生态分析；
- **智能分发模式**：支持 `average_distribution`（平均分配调度）、`round_robin`（轮询分发）、`single_account`（指定单账号）；
- **跨平台适配**：标准 JSON-RPC Stdio 通信，无缝接入 Antigravity、Claude Desktop、Cursor、Windsurf 及任何标准 MCP Client。

### 2. 🧩 动态进群人机验证与验证码自动破解 (`tg_verify_group_join` & `tg_solve_captcha`)
- **多插件支持**：自动识别并破解 `@Shieldy`、`@MissRose_bot`、`@GroupHelpBot`、`@go365_ai_bot`、`@WeGroupRobot` 等常见入群防机器人插件；
- **私聊 Deep-Link 联动**：自动捕获 `[✅ 开始验证 ↗]` 等深层链接，自动向机器人发起 `/start <token>` 私聊握手；
- **四则运算公式秒解**：内置中英文数学题解析引擎，自动计算并点击内联正确答案按钮；
- **AI 协同求解**：遇到复杂图片验证码或问答时，自动将上下文透传给 AI Agent 研判作答。

### 3. 🧹 群发禁言与失效账号安全隔离治理 (`tg_prune_restricted_accounts`)
- **发信权限探针**：批量诊断账号在目标群的真实写权限，精准识别群内禁言、双向受限（SpamBlock）、冻结或 Session 失效；
- **安全隔离归档**：支持一键将失效/受限 Session 移动至带时间戳的 `session_quarantine/` 目录，防止营销资源浪费与风控连锁反应。

### 4. 📜 SpamBot 官方状态全文与精准解封时间 (`tg_check_account_status_full`)
- **官方对话解析**：捕获 `@SpamBot` 完整交互全文，结构化提取 **UTC 精确解封时间**；
- **限制性质诊断**：明确区分临时限制（带倒计时）与永久冻结，并提取可用申诉按钮。

### 5. 🎭 目标群成员一键伪装
- **全套伪装填充**：自动抓取目标群组真实成员的名字、简介与个人头像，一键对列表马甲账号进行全套伪装填充；
- **多群组支持与跨群去重**：支持同时输入多个目标群组，自动按顺序采集并在多群组间全局去重，数据不足自动顺延补齐；
- **5 层严格真实度过滤**：强制要求必须有头像、必须有名字、排除 Bot/已删除/诈骗账号，默认排除管理员。

---

## 🛠️ 核心功能一览

| 分类 | 功能列表 |
| :--- | :--- |
| **MCP 智能体协作** | 18 项全能获客契约、AI 自然语言接管、Stdio 进程管道、自动解人机、动态禁言隔离 |
| **账号与风控治理** | 多账号管理、Session 导入导出、连通性检测、资料修改、SpamBot 全文诊断、安全隔离库 |
| **消息与触达** | 私信群发、群组群发、富文本、可点击超链接、附件图片视频、频道转发、多模式分发 |
| **成员与线索** | 高速成员采集、最近发言人定向提取、目标群一键全套伪装、线索去重与筛选 |
| **AI 社群运营** | AI 炒群、逐群独立运营策略、自定义角色 Prompt、数据克隆（移形换位）、回复概率控制 |
| **社群自动化** | 批量强拉、批量创建群组与频道、智能养号暖号、自动回复、访客机器人 |

---

## 📖 安装与运行指南

### Windows
1. 下载 `WhiteCat-TG-Assistant-Commercial-v4.0-Windows.zip` 并解压到一个全新目录；
2. 双击运行 `TG自动获客助手_商业版_v4.0.exe`；
3. 首次运行可导入现有 Session 账号或配置代理；
4. 如果 SmartScreen 提示未知发布者，请选择“更多信息”→“仍要运行”。

### macOS
1. 根据处理器类型下载对应版本（Apple 芯片下载 `arm64`，Intel Mac 下载 `x86_64`）；
2. 解压 ZIP，将应用拖入“应用程序”文件夹；
3. 首次启动请在 Finder 中右键应用并选择“打开”；如遇拦截，可在终端执行：
   ```bash
   xattr -dr com.apple.quarantine "/Applications/TG自动获客助手_商业版.app"
   ```

---

## 🔒 隐私、安全与合规声明

- **本地隐私承诺**：所有 Telegram 账号 Session、代理凭据及聊天数据均严格存储在本地加密目录，**绝不上云、绝不向任何第三方传输**。
- **公共 API 规范**：软件内置 Telegram 官方标准 API 配置，开箱即用。
- **合规说明**：本工具仅限用于合法、授权、合规的客户服务、营销推广与社群运营场景。请严格遵守 Telegram 服务条款与相关法律法规。

---

## 📬 联系与技术支持

- **Telegram 官方客服**：[t.me/oxbaimao](https://t.me/oxbaimao)
- **问题反馈**：[GitHub Issues](https://github.com/ChiSonKon/tg-sender-releases/issues)
- **版本发布**：[GitHub Releases](https://github.com/ChiSonKon/tg-sender-releases/releases)

---

<p align="center">
  <strong>White Cat Studio · 白猫工作室</strong><br>
  <sub>© 2024–2026 White Cat Studio. All rights reserved.</sub>
</p>
