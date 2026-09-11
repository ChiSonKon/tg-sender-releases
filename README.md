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

> 🚀 当前版本：**商业版 v4.1**。本仓库用于产品介绍、安装包发布和问题反馈，不公开商业版闭源业务代码。

---

## ⚡ 极速上手：本地 AI Agent 一键全自动配置（告别 Agent 拒绝，100% 成功）

### 方案 A（强烈推荐 · 双击即用）：解压后一键配置脚本
客户下载并解压软件包后，**直接双击运行目录下的配置脚本**：
- **Windows 用户**：双击运行 `一键配置本机所有AI_Agent.bat`
- **macOS 用户**：双击运行 `一键配置本机所有AI_Agent.command`

> 🚀 **全自动检测与注入**：
> - 脚本将**免 Python 依赖、全自动探测**本机所有已安装的主流 Agent（包括 **OpenAI Codex、Claude Desktop、Cursor、Google Antigravity、Windsurf、VS Code Cline / Roo-Code**）；
> - 自动安全合并写入对应的 MCP 配置文件并自动备份旧配置；
> - **彻底绕开**“向 Codex / Claude 等 Agent 发送提示词时被拒绝修改系统配置”的问题，双击即搞定！

---

### 方案 B（软件内配置）：在客户端界面一键注入
若您已经打开了获客助手主程序：
1. 切换至【**设置**】➔【**🔌 MCP 服务与 Agent 配置**】页面；
2. 点击大号高亮按钮：【**⚡ 一键自动扫描并配置本机所有 Agent**】；
3. 弹出窗口将直观显示检测到的 Agent 及配置路径，重启或刷新对应 Agent 即可直接调度全量 41 项获客与社群治理工具！

---

### 方案 C（备用提示词）：如果您的 Agent 具备完备的文件读写与终端权限
若您的 Agent 具备终端执行与本地文件写入权限，亦可将下方提示词直接复制发送给 Agent 自动下载配置：

```text
帮我从 GitHub 仓库 https://github.com/ChiSonKon/tg-sender-releases 自动下载最新的 Telegram 获客助手商业版（v4.1），解压并自动配置到当前系统的 MCP 服务中（开启全功能读写授权）。配置完成后，向我汇报你可以调度的 41 项 Telegram 自动化获客与社群治理功能。
```

> 💡 **Agent 自动执行流程**：
> 1. AI Agent 自动访问 GitHub Releases 下载适配您系统的最新版程序并解压；
> 2. AI Agent 自动将 MCP 获客服务注册至当前环境；
> 3. 配置就绪后，您只需向 Agent 发送自然语言指令（例如：*“帮我向目标用户/群组发信”*、*“帮我采集群成员并自动伪装”*、*“帮我加入群组并自动破解人机验证”*、*“帮我监控商机群并过滤高危黑名单”*），Agent 将全自动调度执行！

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

| 系统 | 适用设备 | 下载 | SHA-256 校验和 |
| --- | --- | --- | --- |
| **Windows x64** | Windows 10 / 11 64位 | [下载 Windows 完整包 (.zip)](https://github.com/ChiSonKon/tg-sender-releases/releases/latest/download/WhiteCat-TG-Assistant-Commercial-v4.1-Windows.zip)<br>[单文件免安装版 (.exe)](https://github.com/ChiSonKon/tg-sender-releases/releases/latest/download/TG自动获客助手_商业版_v4.1.exe) | `f572ae66ad7c674b9939b910b7dd0b24977abef89223b8e1b8df8d30d3e9ed9f`<br>`517b297805f9875030b7af89ed90348c17eddcb7051cae102f86962076f19f04` |
| **macOS arm64** | Apple Silicon：M1 / M2 / M3 / M4 | [下载 macOS Apple Silicon (.zip)](https://github.com/ChiSonKon/tg-sender-releases/releases/latest/download/WhiteCat-TG-Assistant-Commercial-v4.1-macOS-arm64.zip) | `be2bdbf2d001dea1d227264835c5402a408110969972b7da561a1ca70c8b4313` |
| **macOS x86_64** | Intel 处理器 Mac | [下载 macOS Intel (.zip)](https://github.com/ChiSonKon/tg-sender-releases/releases/latest/download/WhiteCat-TG-Assistant-Commercial-v4.1-macOS-x86_64.zip) | `9301a5b869fa51b928f59aa3afc4b16d793b6d01cd43f0a563ba1a1d5a599fda` |

> 🔧 **2026-09-11 更新**：v4.1 商业版全新发布！深度扩展至 **全量 41 项 MCP 获客与社群治理工具池**（涵盖关键词群监听、风控黑名单、间谍获客、自动回复、AI炒群、频道克隆、批量举报、广告点击、代理池、会话转换等）、**商机信誉核验与白名单纯净获客**（毫秒级比对剔除高危老赖数据）、**API 凭证跨机器安全保底与失效自愈重加密**、以及**监控账号在线心跳维持**。

---

## 🌟 v4.1 重磅新增与特性

### 1. 🤖 MCP 智能体协议 41 项全功能获客与治理工具池（100% 完全接管）
- **业务功能 100% 全量覆盖**：
  - **发信与触达**：单发私聊/群消息 (`tg_send_message`)、批量并发群发 (`tg_batch_send_messages`)、自动回复引擎 (`tg_configure_auto_reply`, `tg_start_auto_reply`, `tg_stop_auto_reply`)；
  - **引流获客与线索**：群成员全量/活跃采集 (`tg_collect_members`)、批量强制拉人进群 (`tg_force_invite`)、间谍静默线索引擎 (`tg_start_spy_engine`, `tg_stop_spy_engine`, `tg_get_spy_status`)；
  - **社群资产自动化**：批量创建群组与频道 (`tg_batch_create_groups_channels`)、账号资料与主页挂载批量修改 (`tg_update_account_profile`)、频道一键克隆搬运 (`tg_start_channel_clone`, `tg_stop_channel_clone`)；
  - **商业监控与风控黑名单**：关键词实时群监控规则管理 (`tg_manage_monitor_rules`)、启停与命中线索检索 (`tg_start_monitor`, `tg_stop_monitor`, `tg_get_monitor_hits`)、风控黑名单库增删查改与导入导出 (`tg_manage_risk_blacklist`)；
  - **AI 社群运营与炒群**：AI 矩阵炒群运营 (`tg_start_ai_hype`, `tg_stop_ai_hype`, `tg_get_ai_hype_status`)、访客机器人批量唤醒 (`tg_manage_visitor_bots`)；
  - **风控治理与安全防御**：账号真实发信权限与禁言探针 (`tg_prune_restricted_accounts`)、SpamBot 官方状态全文与精确 UTC 解封时间提取 (`tg_check_account_status_full`)、动态入群验证与人机验证码自动求解 (`tg_verify_group_join`, `tg_solve_captcha`)、目标安全检测与自动化分类 (`tg_check_target_safety`, `tg_classify_targets`)、批量违规举报 (`tg_batch_report_target`)、赞助广告自动点击 (`tg_start_ad_clicker`)；
  - **底层基建与运维**：账号智能养号 (`tg_account_warmup`)、动态代理池管理 (`tg_manage_proxies`)、Session 会话格式双向转换 (`tg_convert_session`)、系统配置实时热重载 (`tg_get_system_config`, `tg_update_system_config`)、全局异步任务调度与停止 (`tg_get_task_status`, `tg_stop_task`)。
- **一键全自动注入**：支持 `一键配置本机所有AI_Agent.bat` 与界面内一键扫描，无缝适配 OpenAI Codex、Claude Desktop、Cursor、Google Antigravity、Windsurf、VS Code Roo-Code。

### 2. 🛡️ 商机信誉核验与白名单纯净获客（业内首创）
- **仅导出白名单获客名单 (剔除高危数据)**：
  - 关键词监控工作台操作条新增【🛡️ 仅导出白名单(剔除高危)】开关（默认开启并自动记忆）；
  - 导出获客目标名单时，系统自动在毫秒级比对本地风控黑名单库，凡命中黑名单或高危标记的目标自动予以过滤剔除；
  - 导出成功弹窗中精准反馈导出的安全白名单用户数量与自动剔除的高危用户数量，确保一键导入【私信群发】或【批量强拉】的目标 100% 纯净高转化！
- **全方位风控黑名单管理**：
  - 监控工作台顶部操作条新增【🛡️ 风控黑名单库】入口，支持单条录入、多行文本一键批量粘贴导入、删除、清空与导出；
  - 实时线索流发信人列对命中黑名单的发信人醒目标红显示（如：`⚠️ [跑分老赖] 张三`）；
  - 命中记录右键快捷菜单与线索详情弹窗内均提供【🛡️ 将发送者加入风控黑名单】，发现恶意线索秒级拉黑入库。

### 3. 🔑 API 凭证跨机器多重安全保底与自愈系统（核心稳定性）
- **三重兜底保障**：
  - 商业版底层预置专属 Telegram API 凭证，构筑配置层、管理层与连接层三重兜底，彻底根除因换机、解压配置为空或跨机迁移导致的 `Your API ID or Hash cannot be empty or None` 错误；
- **跨机器指纹自愈重加密**：
  - 引入跨机器失效自愈机制：若检测到外机打包遗留或未匹配本机指纹的历史凭证，系统自动重置为商业版预设凭证并使用当前机器私钥重新加密持久化；
- **打码防护与明文一键切换**：
  - 设置界面 API 凭证默认维持 `Password` 密码遮罩打码保护，新增明文/密码切换按钮（👁️ / 🙈），方便客户需要时核对，保存时若留空自动回退为默认凭证，禁止误存空值。

### 4. 📌 指定公群/担保群信誉秒级核验
- **打破 Telegram 隐私限制的破局解法**：
  - 规则配置新增【信誉核验公群】选填项（支持公群 @用户名 或 群ID）；
  - 监控账号加入该公群/担保群后，线索命中时底层异步调用 MTProto 权限探针核验陌生发信人是否属于该公群成员；
  - 通知卡片中直观呈现 `📌 【担保群核验】✅ 已在该担保群内` 或 `❌ 未加入该担保群`，彻底杜绝虚假冒充。

### 5. 🧩 动态进群人机验证与验证码自动破解 (`tg_verify_group_join` & `tg_solve_captcha`)
- **多插件支持**：自动识别并破解 `@Shieldy`、`@MissRose_bot`、`@GroupHelpBot`、`@go365_ai_bot`、`@WeGroupRobot` 等常见入群防机器人插件；
- **私聊 Deep-Link 联动**：自动捕获 `[✅ 开始验证 ↗]` 等深层链接，自动向机器人发起 `/start <token>` 私聊握手；
- **四则运算公式秒解**：内置中英文数学题解析引擎，自动计算并点击内联正确答案按钮；
- **AI 协同求解**：遇到复杂图片验证码或问答时，自动将上下文透传给 AI Agent 研判作答。

### 6. 🧹 群发禁言与失效账号安全隔离治理 (`tg_prune_restricted_accounts`)
- **发信权限探针**：批量诊断账号在目标群的真实写权限，精准识别群内禁言、双向受限（SpamBlock）、冻结或 Session 失效；
- **安全隔离归档**：支持一键将失效/受限 Session 移动至带时间戳的 `session_quarantine/` 目录，防止营销资源浪费与风控连锁反应。

### 7. 📜 SpamBot 官方状态全文与精准解封时间 (`tg_check_account_status_full`)
- **官方对话解析**：捕获 `@SpamBot` 完整交互全文，结构化提取 **UTC 精确解封时间**；
- **限制性质诊断**：明确区分临时限制（带倒计时）与永久冻结，并提取可用申诉按钮。

### 8. 🎭 目标群成员一键伪装与社群全面优化
- **全套伪装填充**：自动抓取目标群组真实成员的名字、简介与个人头像，一键对列表马甲账号进行全套伪装填充；
- **多群组支持与跨群去重**：支持同时输入多个目标群组，自动按顺序采集并在多群组间全局去重，数据不足自动顺延补齐；
- **在线心跳维持**：发信通知时顺带发送在线心跳更新，使监控账号时刻保持在线活动心跳，消除离线顾虑。

---

## 🛠️ 核心功能一览

| 分类 | 功能列表 |
| :--- | :--- |
| **MCP 智能体协作** | 全量 41 项全能获客契约、AI 自然语言接管、一键配置本机所有 Agent、Stdio 管道通信、自动解人机、动态禁言隔离 |
| **商业监控与风控** | 关键词群监控、风控黑名单库、商机白名单过滤导出(剔除高危)、指定公群/担保群信誉秒级核验、在线心跳维持 |
| **账号与底层治理** | 多账号管理、API凭证跨机自愈与加密保护、SpamBot 全文UTC解封诊断、群写权限探针、失效账号隔离归档 |
| **消息与营销触达** | 私信群发、群组群发、富文本超链接、附件多媒体、频道转发广播、私信自动回复引擎、多种并发分发调度 |
| **成员与精准线索** | 高速成员采集、最近发言人定向提取、目标群成员一键全套伪装、线索全局去重、间谍静默获客引擎 |
| **社群自动化与矩阵** | AI 炒群矩阵、频道克隆搬运、批量强拉加群、批量建群建频道、批量违规举报、广告自动点击、代理池、Session转换 |

---

## 📖 安装与运行指南

### Windows
1. 下载 `WhiteCat-TG-Assistant-Commercial-v4.1-Windows.zip` 并解压到一个全新目录（亦可直接下载单文件版 `TG自动获客助手_商业版_v4.1.exe`）；
2. 双击运行 `TG自动获客助手_商业版_v4.1.exe`；
3. 商业版已内置默认 Telegram API 凭证，开箱即用，可直接导入现有 Session 账号或配置代理；
4. 如需与本地 AI Agent 联动，直接双击运行目录下的 `一键配置本机所有AI_Agent.bat` 即可全自动完成注入；
5. 如果 SmartScreen 提示未知发布者，请选择“更多信息”→“仍要运行”。

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
