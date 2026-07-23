<p align="center">
  <img src="./docs/logo.png" width="120" height="120" alt="白猫工作室" />
</p>

<h1 align="center">白猫工作室 TG 自动获客助手 · 商业版</h1>

<p align="center">
  <strong>多账号管理、消息运营、线索采集与 AI 社群互动的一体化桌面工具</strong>
</p>

<p align="center">
  <a href="https://github.com/ChiSonKon/tg-sender-releases/releases/latest"><img alt="Latest Release" src="https://img.shields.io/github/v/release/ChiSonKon/tg-sender-releases?display_name=release&style=for-the-badge&color=1677ff"></a>
  <a href="https://github.com/ChiSonKon/tg-sender-releases/releases"><img alt="Downloads" src="https://img.shields.io/github/downloads/ChiSonKon/tg-sender-releases/total?style=for-the-badge&color=22a06b"></a>
  <img alt="Platform" src="https://img.shields.io/badge/Platform-Windows%20%7C%20macOS-7c3aed?style=for-the-badge">
</p>

> 当前版本：**商业版 v2.3**。本仓库用于产品介绍、安装包发布和问题反馈，不公开商业版源代码。

## 私信群发与富文本演示

https://github.com/user-attachments/assets/d2d45e1f-58b2-499d-973b-a31c802ab19f

## AI 炒群与群组群发演示

https://github.com/user-attachments/assets/da417416-df93-4988-9e72-e530873dd4b2

## 当前版本下载

请从 [Latest Release](https://github.com/ChiSonKon/tg-sender-releases/releases/latest) 下载与设备匹配的版本。

| 系统 | 适用设备 | 下载 |
| --- | --- | --- |
| Windows x64 | Windows 10 / 11 | [下载 Windows](https://github.com/ChiSonKon/tg-sender-releases/releases/latest/download/WhiteCat-TG-Assistant-Commercial-v2.3-Windows.zip) |
| macOS arm64 | Apple Silicon：M1 / M2 / M3 / M4 | [下载 macOS Apple Silicon](https://github.com/ChiSonKon/tg-sender-releases/releases/latest/download/WhiteCat-TG-Assistant-Commercial-v2.3-macOS-arm64.zip) |
| macOS x86_64 | Intel 处理器 Mac | [下载 macOS Intel](https://github.com/ChiSonKon/tg-sender-releases/releases/latest/download/WhiteCat-TG-Assistant-Commercial-v2.3-macOS-x86_64.zip) |

## 本次新增

### 场景贴纸库

- 可按业务场景整理和调用贴纸素材。
- 支持关键词匹配与目标群组策略，社群互动更自然。
- 贴纸规则可与 AI 回复流程配合使用。

### 最近发言人采集

- 可按最近活跃情况采集群组发言人。
- 减少对长期不活跃成员的无效触达。
- 采集结果可继续用于筛选、导出和后续任务。

### 富文本与可点击超链接

- 私信群发和群组群发支持富文本内容。
- 支持可点击超链接，并保留常用文本样式。
- 发送前可检查内容与链接效果，降低格式错误。

## 重点优化

### AI 社群互动

- 优化话题切换逻辑，减少连续回复中的内容重复。
- 增加回复概率与引用概率控制，使互动节奏更接近真实社群。
- 改进角色、目标群组与上下文管理，降低不同任务之间的内容干扰。

### 数据克隆反馈

- 增强克隆过程的状态、进度与结果反馈。
- 对失败原因提供更明确的提示，便于调整来源和任务配置。

### 代理验证与账号管理

- 优化代理格式识别、连通性验证和状态提示。
- 增强账号与代理绑定逻辑，降低配置错误。
- 网络异常时保留账号信息，恢复连接后可重新检测。

### 暖号并发

- 优化多账号暖号任务的并发控制与运行状态展示。
- 同一账号的发送操作采用顺序保护，减少并发冲突。
- 停止任务时更及时地终止待发送内容。

## 核心功能

| 分类 | 功能 |
| --- | --- |
| 账号与环境 | 多账号管理、Session 导入导出、在线检测、资料修改、代理管理 |
| 消息与触达 | 私信群发、群组群发、富文本、超链接、附件、转发 |
| 成员与线索 | 成员采集、最近发言人采集、社群线索监测与处理 |
| AI 社群运营 | 多群并发、独立上下文、角色策略、贴纸场景、回复与引用控制 |
| 社群自动化 | 暖号养号、自动回复、访客机器人、频道内容迁移 |
| 任务管理 | 逐目标进度、成功与失败统计、运行日志、任务停止控制 |

## 安装与升级

### Windows

1. 下载 Windows ZIP 并解压到一个全新文件夹。
2. 双击 `TG自动获客助手_商业版_v2.3.exe`。
3. 首次运行后进入账号管理，导入 Session 或迁移现有数据。
4. 如果 SmartScreen 提示未知发布者，请先核对 SHA-256，再选择“更多信息”→“仍要运行”。

Windows 数据目录：

```text
%LOCALAPPDATA%\WhiteCat\TG自动获客助手\
├── config.json
├── session\
├── data\
└── 日志\
```

### macOS

1. 在“关于本机”中确认处理器类型：Apple 芯片下载 `arm64`，Intel Mac 下载 `x86_64`。
2. 解压 ZIP，将应用拖入“应用程序”文件夹。
3. 当前安装包采用临时签名，未完成 Apple 公证；首次启动请在 Finder 中右键应用并选择“打开”。
4. 如系统仍阻止启动，请核对 SHA-256 后再执行：

```bash
xattr -dr com.apple.quarantine "/Applications/TG自动获客助手_商业版.app"
```

macOS 数据目录：

```text
~/Library/Application Support/WhiteCat/TG自动获客助手/
├── config.json
├── session/
├── data/
└── 日志/
```

### 升级与数据继承

1. 停止正在运行的任务并关闭软件。
2. 备份当前数据目录和 Session。
3. 将 v2.3 解压到全新目录，不要覆盖当前安装目录。
4. 启动 v2.3 后导入 Session 或使用数据迁移功能。
5. 先用少量账号和测试群验证代理、发送格式与任务配置，再恢复正式任务。

迁移采用复制方式，不会主动删除原数据。需要回退时，请先关闭 v2.3，再使用备份数据恢复。

## 常见问题

<details>
<summary><strong>为什么重启后账号显示“待连接”？</strong></summary>

软件会先读取本地 Session，再后台连接 Telegram。网络或代理暂时不可用时，账号仍会保留在列表中；恢复连接后可重新检测。
</details>

<details>
<summary><strong>如何确认富文本和链接发送正确？</strong></summary>

建议先向自有测试账号或测试群发送，确认加粗、链接和换行效果后，再逐步扩大任务范围。
</details>

<details>
<summary><strong>Apple 芯片和 Intel Mac 应该如何选择？</strong></summary>

M1、M2、M3、M4 等 Apple 芯片下载 `arm64`；“关于本机”显示 Intel 的设备下载 `x86_64`。
</details>

<details>
<summary><strong>为什么 macOS 提示无法验证开发者？</strong></summary>

当前安装包采用临时签名，未完成 Apple 公证。请只从本仓库下载、核对 SHA-256，并使用 Finder 右键“打开”。
</details>

<details>
<summary><strong>AI 社群互动是否需要单独配置接口？</strong></summary>

需要在软件中配置可用的 AI API。建议先在测试群验证回复风格、话题切换、额度和并发设置。
</details>

## 联系与反馈

- Telegram：[t.me/oxbaimao](https://t.me/oxbaimao)
- 问题反馈：[GitHub Issues](https://github.com/ChiSonKon/tg-sender-releases/issues)
- 版本下载：[Latest Release](https://github.com/ChiSonKon/tg-sender-releases/releases/latest)

反馈问题时，请附上操作系统、软件版本、问题发生时间、相关页面和已脱敏的日志片段。请勿上传 Session、API 密钥、授权码或客户数据。

## 合规与安全说明

本工具仅用于合法、授权、合规的社群运营和客户服务场景。使用者应确保：

- 仅操作本人所有或已获得明确授权的账号、群组、频道和数据；
- 不用于骚扰、刷屏、诈骗、钓鱼、虚假宣传、恶意举报或规避平台限制；
- 遵守 Telegram 服务条款、群组规则、隐私要求及所在地法律法规；
- 对发送频率、账号安全、内容真实性和数据处理承担管理责任。

---

<p align="center">
  <strong>White Cat Studio · 白猫工作室</strong><br>
  <sub>© 2024–2026 White Cat Studio. All rights reserved.</sub>
</p>
