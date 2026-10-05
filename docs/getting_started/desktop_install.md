
# 💻 电脑端下载与安装指南（v5.0）

> 🚀 当前版本：**v5.0.0**。支持 **Windows 10 / 11（64 位）**，以及 **macOS（Apple Silicon M1–M4 / Intel）**。
> 每个平台都提供两种形式：**安装版**（推荐，自带自动更新）和**免安装版**（解压即用，适合不想安装、放在移动硬盘或多开的场景）。

---

## 一、官方下载（GitHub Releases）

前往 [Releases 页面](https://github.com/ChiSonKon/tg-sender-releases/releases/latest) 下载。**请只从这里下载**，并核对下方的 SHA-256 校验和。

| 系统 | 形式 | 文件 | 说明 |
| :--- | :--- | :--- | :--- |
| **Windows x64** | 安装版 ⭐ | `WhiteCat-TG-Assistant-5.0.0-Setup.exe` | 双击安装，免管理员权限，装在你自己的用户目录 |
| **Windows x64** | 免安装版 | `WhiteCat-TG-Assistant-5.0.0-Windows-x64-Portable.zip` | 解压后双击里面的 `TG自动获客助手_旗舰商业版.exe` |
| **macOS Apple Silicon** | 安装版 ⭐ | `WhiteCat-TG-Assistant-5.0.0-macOS-arm64.dmg` | M1 / M2 / M3 / M4，拖进「应用程序」 |
| **macOS Apple Silicon** | 免安装版 | `WhiteCat-TG-Assistant-5.0.0-macOS-arm64-Portable.zip` | 解压得到 `.app`，放哪都能运行 |
| **macOS Intel** | 安装版 ⭐ | `WhiteCat-TG-Assistant-5.0.0-macOS-x64.dmg` | Intel 处理器的 Mac |
| **macOS Intel** | 免安装版 | `WhiteCat-TG-Assistant-5.0.0-macOS-x64-Portable.zip` | 解压得到 `.app` |

> 不确定芯片？点屏幕左上角苹果菜单 → **关于本机**：显示「芯片 Apple M…」选 arm64，显示「处理器 Intel…」选 x64。
> 校验：Windows 在 PowerShell 执行 `Get-FileHash <文件>`；macOS 在终端执行 `shasum -a 256 <文件>`，结果应与 Release 页面的 `SHA256SUMS.txt` 一致。

---

## 二、系统与环境要求

- **Windows**：Windows 10 或 11，64 位。安装后约占 0.6 GB，建议预留 2 GB 以上空闲空间。
- **macOS**：macOS 11 或更高版本（Apple Silicon 与 Intel 请分别下载对应的包）。
- **网络**：必须联网（激活授权、检查更新都需要）。软件通过 Telegram 官方网络工作，如果你所在网络不能直接访问 Telegram，请先准备可用的网络环境，或在软件里给账号配置代理。
- **内存**：同时在线的账号越多占用越大，账号多时请关闭其他大型软件。

---

## 三、Windows

### 方式 A：安装版（推荐）
1. 双击 `WhiteCat-TG-Assistant-5.0.0-Setup.exe`；
2. 如果出现蓝色的「Windows 已保护你的电脑」→ 点 **「更多信息」→「仍要运行」**（见下方说明）；
3. 一路「下一步」（建议勾选「创建桌面快捷方式」），安装完成后从开始菜单或桌面启动。

### 方式 B：免安装版
1. 把 `…Windows-x64-Portable.zip` 解压到任意位置（建议非系统盘、路径尽量短）；
2. 双击文件夹里的 `TG自动获客助手_旗舰商业版.exe`；
3. 想删除时直接删文件夹即可。

### 为什么会弹出「Windows 已保护你的电脑」？
软件目前**没有购买微软的代码签名证书**，Windows 会对「还没见过的新软件」做一次提醒，**不代表有病毒**。每个新版本第一次运行时可能再出现一次，做法相同。
如果杀毒软件（360 / 火绒 / Defender 等）拦截或把文件放进隔离区：在杀毒软件里选择「恢复 / 信任」，并把安装目录加入信任。安装版默认目录：`%LOCALAPPDATA%\Programs\TG自动获客助手_旗舰商业版`（在资源管理器地址栏粘贴回车即可打开）。

---

## 四、macOS

### 方式 A：安装版（dmg）
1. 双击 `.dmg`，把 App 拖到「应用程序」；
2. 第一次打开会被系统拦截（App 采用 Ad-hoc 签名，没有购买 Apple 开发者账号），按下面放行：
   - **macOS 14 及更早**：在「应用程序」里 **右键 App → 打开 → 再点「打开」**；
   - **macOS 15 及更新**：先双击一次（会被拦）→ **系统设置 → 隐私与安全性** → 往下拉 → 点 **「仍要打开」** → 输入开机密码；
   - 如果提示「已损坏，无法打开」：打开「终端」执行下面这行（路径按实际位置改），然后重新打开：
     ```bash
     xattr -dr com.apple.quarantine "/Applications/TG自动获客助手 旗舰商业版.app"
     ```
3. 放行一次后，之后可正常双击使用。

### 方式 B：免安装版（zip）
解压得到 `TG自动获客助手 旗舰商业版.app`，放到任意位置，按上面同样的方法放行后使用。

### 语音条（语音消息转码）
macOS 版已**内置**转码组件（FFmpeg，LGPL 许可，随包附许可证），无需额外安装，即可把 mp3 / wav 等音频转成 Telegram 原生语音条。

> ⚠️ macOS 版是首次发布，已通过自动化构建与自检，**欢迎在使用中把遇到的问题反馈给客服**（见文末）。

---

## 五、数据放在哪里？卸载会删数据吗？

- 账号 Session、配置等数据只保存在你自己的电脑上，**不上传**：
  - Windows：`%LOCALAPPDATA%\WhiteCat\TG自动获客助手`
  - macOS：`~/Library/Application Support/WhiteCat/TG自动获客助手`
- **升级软件、卸载软件、删除免安装文件夹，都不会删除这个数据目录**（避免误删账号）。想彻底清除请手动删除该文件夹，删之前先备份。
- Session 文件相当于账号登录凭证，请勿发给他人。

---

## 六、软件更新

联网状态下，软件会在启动约 20 秒后、之后每 6 小时检查一次更新，也可以在【设置】里手动点「检查更新」。发现新版本会弹窗，点「立即更新」即可：软件在后台下载并校验，**安装版会自动覆盖安装并重新打开**，用户数据不受影响。
**免安装版**同样会收到更新提示，但在 Windows 上点「立即更新」会走安装程序、装成安装版；如果想继续保持免安装，请忽略提示，直接到 Releases 页面下载新的压缩包覆盖旧文件夹。

---

## 七、下一步

安装好之后请阅读：[**试用、购买与激活（卡密）**](activation_and_trial.md)。

---

<p align="center">
  <a href="architecture.md">⬅️ 上一篇：生态架构</a> | <a href="activation_and_trial.md">下一篇：试用、购买与激活 ➡️</a>
</p>
