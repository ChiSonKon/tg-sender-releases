
# 🆕 v5.0 更新说明

v5.0 是一次**全面重构的大版本**：底层改为原生编译、全新的授权与购买体系、全新界面，并补齐了 macOS 版本。

---

## 一、安装与分发

- **原生编译**：程序由 Nuitka 编译为原生机器码，启动更稳、不依赖本机 Python 环境；
- **安装版 + 免安装版**：Windows `Setup.exe` / 便携 zip；macOS `dmg` / 便携 zip；Apple Silicon 与 Intel 各一份；
- **应用内自动更新**：启动后与每 6 小时检查，更新包经过签名与哈希校验，安装版可一键静默覆盖并自动重启；
- **语音条开箱即用**：Windows 与 macOS 均内置 FFmpeg（LGPL，随包附许可证），mp3 / wav 等可直接转成 Telegram 原生语音条，无需自己装环境。

## 二、授权与购买

- 新设备自带约 3 小时免费试用；
- 新的套餐体系（尝鲜体验卡 / 月 / 季 / 年 / 终身）；
- **软件内收银台**：USDT 多链支付，到账自动发卡密并自动激活；
- 官方购买机器人 [@oxbaimaobot](https://t.me/oxbaimaobot)：购买、续费、到期提醒；
- 卡密保险箱：卡密本机加密保存，换网络 / 断网恢复后自动重试激活，支持「找回我的卡密」。
- 详见 [试用、购买与激活](activation_and_trial.md)。

## 三、全新界面与引导

- 昼夜双主题（日间 / 夜间 / 自动），按 `Ctrl+K` 全局搜索功能；
- 首页新手任务与「流程」引导：把几个功能按顺序串成一条完整工作流；
- 全局账号池、开始前检查、运行中任务面板、结果摘要。

## 四、业务能力

- **账号健康守门员**：新号体检与按号龄分级的风控；
- **监听即转化流水线**：关键词监听 → 线索即时上屏 → 一键触达；
- **批量加群过群**：重构进群验证（过群）并支持「看图 AI」（可接 Gemini / GPT-4o / Ollama 视觉模型，需自行配置 Key）；
- **频道克隆**：修复把创建者 / 管理员误判为「不是管理员」的问题；
- **私信语音条**：修复打包版语音条发送失败；
- 安全检测页面全面中文化。

## 五、MCP 智能体（45 项工具）

- 工具由 41 项扩展到 **45 项**，新增：账号健康（`tg_account_health`）、流水线状态与控制（`tg_pipeline_status` / `tg_pipeline_control`）、线索台（`tg_desk_leads`）；
- 设置页「**一键配置本机所有 Agent**」支持：Claude Code、Claude Desktop、OpenAI Codex、Cursor、Windsurf、Google Antigravity、Gemini CLI、VS Code（Copilot 原生 MCP）、VS Code Cline / Roo-Code；并会检测并**修复指向失效路径的旧配置**。

## 六、已知事项（如实说明）

- Windows 安装包与 macOS App **暂未购买代码签名 / 公证**：首次运行会被系统拦截，按 [安装指南](desktop_install.md) 放行一次即可；
- macOS 版为首次发布，经自动化构建与自检验证，欢迎反馈问题；
- AI 能力目前需在软件里自行配置模型 Key。

---

<p align="center">
  <a href="activation_and_trial.md">⬅️ 上一篇：试用、购买与激活</a> | <a href="../README.md">🏠 返回文档首页</a>
</p>
