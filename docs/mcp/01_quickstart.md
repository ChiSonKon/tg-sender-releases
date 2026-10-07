# 🤖 MCP 智能体协议 · 一键全自动配置

> 💡 **核心定位**：通过 **Model Context Protocol (MCP)** 协议，把软件里绝大多数获客功能开放给外部主流 AI 智能体（Agent）调度。
> v5.0.0 为 **45 项**工具；**5.0.1 起为 53 项**（新增智能群发、群质量漏斗、加群过验证、建机器人、@SpamBot 申诉、统一群发完整能力、账号管理），完整列表见 [MCP 工具参考](03_tools_reference.md)。会发消息 / 加群 / 改账号的动作需要开启写入权限，预览与查看类操作默认可用。并会检测、修复指向已失效路径的旧配置。
> 彻底告别“向 Agent 发提示词修改配置被拒绝”的烦恼！

---

## 一、方案 A（强烈推荐 · 双击即用）：解压后一键脚本

软件包内置了跨平台自动化注入脚本，无需手动配置任何 JSON，直接双击运行：
- **Windows 用户**：双击运行 `一键配置本机所有AI_Agent.bat`
- **macOS 用户**：双击运行 `一键配置本机所有AI_Agent.command`

### 🚀 自动化特性：
1. **零 Python 环境依赖**：脚本自动使用内置环境与原生命令探测；
2. **主流 Agent 全覆盖**：自动扫描并精准适配：
   - **OpenAI Codex**
   - **Claude Desktop**
   - **Cursor**
   - **Google Antigravity**
   - **Windsurf**
   - **Claude Code**、**Gemini CLI**、**VS Code（Copilot 原生 MCP）**（v5.0 新增）
   - **VS Code Cline / Roo-Code**
3. **安全合并备份**：自动备份现有配置文件，以非覆盖的安全 Merge 方式追加 `whitecat-tg-assistant` 工具链。

---

## 二、方案 B（软件内配置）：在客户端界面一键注入

若您已经打开了获客助手客户端：
1. 切换至【**设置**】➔【**🔌 MCP 服务与 Agent 配置**】页面；
2. 点击高亮按钮：【**⚡ 一键自动扫描并配置本机所有 Agent**】；
3. 弹窗将显示检测到的 Agent 路径，点击确认即可无缝写入，重启对应 Agent 即刻生效！

---

<p align="center">
  <a href="../SUMMARY.md">⬅️ 返回文档目录</a> | <a href="02_prompts.md">下一篇：自然语言提示词库 ➡️</a> | <a href="03_tools_reference.md">MCP 工具参考</a>
</p>\n