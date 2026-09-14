# 04. 系统配置与 MCP 智能体

> 📌 **模块分类**：底座与环境设置  
> 💡 **核心定位**：系统核心参数配置，以及全行业首创的 41 项 MCP (Model Context Protocol) 智能体调度控制台。

---

## 一、解决的核心商业痛点
配置繁琐、无法与现代前沿大模型协同，传统脚本只能机械运行无法根据实时反馈自适应调整策略。

---

## 二、界面实战图解
<p align="center">
  <img src="../manual_images/17_设置_系统配置与MCP.png" alt="系统配置与 MCP 智能体 界面截图" width="98%" style="border-radius: 8px; box-shadow: 0 4px 16px rgba(0,0,0,0.3);">
</p>

---

## 三、功能特性一览
- API 凭据配置：自定义配置官方 Telegram API ID 与 API Hash
- 内置前置全局网络探测隧道，无需开启全局 VPN TUN 模式即可直连
- 一键配置本机所有主流 AI Agent（Claude Desktop、Cursor、Codex、Antigravity、Windsurf）
- 41 项 MCP 协议工具实时就绪，支持 AI 自然语言全自动接管获客系统

---

## 四、标准实战操作指南
1. 填入您申请的 Telegram API ID 与 Hash（亦可使用内置商业默认高速通道）；
2. 点击「自动探测本地代理」，软件将自动识别本机运行的 Clash/v2rayN 并一键建立前置隧道；
3. 在「MCP 智能体配置」板块，点击「⚡ 一键配置本机所有 AI Agent」；
4. 重启您的 Claude Desktop 或 Cursor，即可在对话框中直接通过一句话让 AI 调度软件所有获客功能！

---

## 五、工业级防封与实战秘诀
- MCP 协议支持只读审计与完全读写两种权限，生产环境中可按需开启 `--allow-writes` 授权；
- 若遇到系统提示代理连接失败，直接在网络设置中将前置隧道代理端口对应本机代理端口即可。

---

<p align="center">
  <a href="../USER_MANUAL.md">⬅️ 返回总目录</a> | <a href="https://github.com/ChiSonKon/tg-sender-releases">🏠 返回项目首页</a>
</p>
