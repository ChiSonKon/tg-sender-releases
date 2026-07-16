<p align="center">
  <img src="./docs/logo.png" width="120" height="120" alt="白猫工作室" />
</p>

<h1 align="center">白猫工作室 TG 自动获客助手 · 商业版</h1>

<p align="center">
  <strong>多账号管理、消息运营、线索处理与 AI 社群互动的一体化桌面工具</strong>
</p>

<p align="center">
  <a href="https://github.com/ChiSonKon/tg-sender-releases/releases/latest"><img alt="Latest Release" src="https://img.shields.io/github/v/release/ChiSonKon/tg-sender-releases?display_name=release&style=for-the-badge&color=1677ff"></a>
  <a href="https://github.com/ChiSonKon/tg-sender-releases/releases"><img alt="Downloads" src="https://img.shields.io/github/downloads/ChiSonKon/tg-sender-releases/total?style=for-the-badge&color=22a06b"></a>
  <img alt="Platform" src="https://img.shields.io/badge/Platform-Windows%20%7C%20macOS-7c3aed?style=for-the-badge">
</p>

<p align="center">
  <a href="#下载-v21">下载</a> ·
  <a href="#v21-重点升级">重点升级</a> ·
  <a href="#功能模块">功能模块</a> ·
  <a href="#安装与升级">安装升级</a> ·
  <a href="#常见问题">常见问题</a> ·
  <a href="#联系与反馈">联系反馈</a>
</p>

> 当前稳定版：**v2.1（2026-07-16）**。本仓库只用于产品介绍、安装包发布和问题反馈，不公开商业版源代码。

## 下载 v2.1

请只从 [Latest Release](https://github.com/ChiSonKon/tg-sender-releases/releases/latest) 下载。旧版的 Basic、Advanced、Complete 与旧 Linux/macOS 包已停止维护，不建议继续使用。

| 系统 | 适用设备 | 下载 |
| --- | --- | --- |
| Windows x64 | Windows 10 / 11 | [下载 Windows v2.1](https://github.com/ChiSonKon/tg-sender-releases/releases/latest/download/WhiteCat-TG-Assistant-Commercial-v2.1-Windows.zip) |
| macOS arm64 | Apple Silicon：M1 / M2 / M3 / M4 | [下载 macOS Apple Silicon v2.1](https://github.com/ChiSonKon/tg-sender-releases/releases/latest/download/WhiteCat-TG-Assistant-Commercial-v2.1-macOS-arm64.zip) |
| macOS x86_64 | Intel 处理器 Mac | [下载 macOS Intel v2.1](https://github.com/ChiSonKon/tg-sender-releases/releases/latest/download/WhiteCat-TG-Assistant-Commercial-v2.1-macOS-x86_64.zip) |

### SHA-256 校验值

| 文件 | SHA-256 |
| --- | --- |
| `WhiteCat-TG-Assistant-Commercial-v2.1-Windows.zip` | `81C29FFAFF5DCDFD586BE44ECF56DD587C2AFD30864D97B2E564D4D12D711EC3` |
| `WhiteCat-TG-Assistant-Commercial-v2.1-macOS-arm64.zip` | `B06C7EFBD3630A0742770320DB0C9EC9BB82BAD607F7D1EBCD2EF69436E30B35` |
| `WhiteCat-TG-Assistant-Commercial-v2.1-macOS-x86_64.zip` | `EE5E49264B57EE19B7C543DACF5BAD7CC5973DFFCCD5FB75570BDDEC846F86D9` |

每个压缩包的校验文件也已附在 Release 中。Windows 可使用 `Get-FileHash`，macOS 可使用 `shasum -a 256` 复核下载文件。

## v2.1 重点升级

### Session 重启后稳定保留

- Session、配置、数据库和日志改为保存在系统用户数据目录，不再依赖程序解压位置。
- 启动时先读取本地 Session，再后台检查连接；断网或代理异常时账号仍会显示为“待连接”。
- 导入、导出采用 SQLite 一致性快照，降低直接复制数据库时的损坏风险。
- 支持从旧版目录迁移 Session；迁移只复制、不删除、不覆盖已有文件。

### 更适合笔记本的界面

- 最低窗口尺寸降至 **880 × 560**。
- 功能侧栏支持搜索、折叠，并在窄屏自动进入紧凑模式。
- 运行日志可收起；密集页面支持滚动；账号列表会在窄屏隐藏次要字段。

### AI 炒群支持多群并发

- 单个任务可同时运行最多 **20 个群组或频道**。
- 每个目标独立维护上下文、记忆和任务状态，不会串群。
- AI 请求并发可设置为 **1～10 路**；同一 Telegram 账号的发送操作会自动串行保护。
- 多群任务表分别展示每个目标的状态、成功数与错误数。
- 点击停止后，不再投递已生成但尚未发送的内容。

### Windows 与 macOS 发布质量

- macOS 分别在 Apple Silicon 与 Intel Runner 上原生构建，不使用 Windows 伪交叉编译包。
- 两种 Mac 包均已通过自动测试、CPU 架构检查、签名检查和实际启动冒烟测试。

## 功能模块

商业版目前提供以下桌面模块；最终可用范围以账号授权为准。

| 分类 | 模块与能力 |
| --- | --- |
| 账号与环境 | 多账号管理、Session 导入导出、在线状态检查、账号资料修改、代理管理、安全与格式转换 |
| 消息与触达 | 统一群发、私信群发、附件与转发、成员采集、获授权成员邀请 |
| 社群自动化 | 养号暖号、私信自动回复、访客机器人、频道内容迁移、广告点击任务 |
| AI 与线索 | AI 社群互动、多角色与上下文记忆、多群并发、社群线索监测与处理 |
| 运营与治理 | 任务进度、逐目标统计、运行日志、内容与账号举报工具 |

所有自动化任务都应先在自有测试账号和自有群组中验证。请勿将成员采集、邀请、发送或举报功能用于未经授权的对象。

## 安装与升级

### Windows 10 / 11

1. 下载并解压 Windows ZIP 到一个**全新文件夹**。
2. 双击目录中的商业版 EXE。
3. 如 SmartScreen 提示未知发布者，请核对 SHA-256 后选择“更多信息”→“仍要运行”。
4. 进入“账号管理”，导入 Session 或使用“迁移旧 Session”。

Windows 客户数据固定保存在：

```text
%LOCALAPPDATA%\WhiteCat\TG自动获客助手\
├── config.json
├── session\
├── data\
└── 日志\
```

### macOS 11 或更高版本

1. 点击左上角  →“关于本机”，确认处理器类型。
2. M1/M2/M3/M4 下载 `arm64`；Intel Mac 下载 `x86_64`。
3. 解压 ZIP，将 `.app` 拖入“应用程序”文件夹。
4. 首次启动时，在 Finder 中右键应用并选择“打开”。

当前 v2.1 Mac 包已完成临时签名，但尚未使用 Apple Developer ID 公证。如果系统仍阻止启动，请先核对 SHA-256，然后在终端执行：

```bash
xattr -dr com.apple.quarantine "/Applications/TG自动获客助手_商业版.app"
```

macOS 客户数据固定保存在：

```text
~/Library/Application Support/WhiteCat/TG自动获客助手/
├── config.json
├── session/
├── data/
└── 日志/
```

后续配置 Apple Developer ID 后，将提供正式签名和 Apple 公证版本，减少 Gatekeeper 首次运行提示。

### 从旧版安全升级

1. 先停止任务并关闭旧版，确认 Session 已写盘。
2. 保留旧版整个目录作为回退备份。
3. 将 v2.1 解压到新文件夹，**不要覆盖旧版**。
4. Windows 用户可在“账号管理”点击“迁移旧 Session”并选择旧版根目录。
5. 先使用少量账号与测试群验证，再逐步恢复正式任务。

v2.1 的数据目录与旧版发布目录相互隔离；迁移不会删除旧 Session，需要回退时可直接关闭 v2.1 后运行旧版。

## AI 多群并发快速配置

1. 在 AI 炒群页面选择可用账号。
2. 在目标输入框中用逗号或分号填写多个群组/频道，最多 20 个。
3. 为项目配置背景、FAQ、角色与互动规则。
4. 根据 AI 接口额度设置 1～10 的并发上限；首次建议从 1～2 开始。
5. 启动后在“多群任务”表观察各目标状态、成功数和错误信息。

建议不同群组使用清晰、真实且不误导用户的互动规则，并遵守群组管理员要求。

## 常见问题

<details>
<summary><strong>为什么重新启动后账号显示“待连接”？</strong></summary>

v2.1 会先展示本地 Session，再后台连接 Telegram。网络、代理或 Telegram 暂时不可用时，账号不会从列表消失，而是显示为待连接；恢复网络后可重新检测。
</details>

<details>
<summary><strong>为什么不能直接覆盖旧版文件夹？</strong></summary>

新旧版本的数据位置和部分配置结构不同。解压到新文件夹并通过迁移功能导入 Session，既便于验证，也能随时回退。
</details>

<details>
<summary><strong>我的 Mac 应该下载哪个版本？</strong></summary>

M1、M2、M3、M4 等 Apple 芯片下载 `arm64`；“关于本机”显示 Intel 的设备下载 `x86_64`。
</details>

<details>
<summary><strong>为什么 macOS 提示无法验证开发者？</strong></summary>

当前包是临时签名、尚未 Apple 公证的首发测试版本。请只从本仓库下载、核对 SHA-256，然后使用 Finder 右键“打开”；仍被阻止时再使用上方 `xattr` 命令。
</details>

<details>
<summary><strong>AI 炒群是否需要单独的 API？</strong></summary>

需要在软件中配置可用的 AI API。建议先使用测试群校验提示词、回复风格、额度和并发设置，再用于正式运营。
</details>

<details>
<summary><strong>是否支持 Linux？</strong></summary>

当前商业版 v2.1 只发布 Windows 与 macOS。旧 Linux 包已停止维护，不应作为当前版本使用。
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
