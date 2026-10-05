# ❓ 常见问题排查与官方技术支持

---

## 一、常见问题排查速查

### Q1: 电脑端打开提示缺少运行时或报错？
**解答**：Windows 用户请确保安装了微软官方标准的 `Visual C++ Redistributable 2015-2022` 运行库。

### Q2: 导入的 Session 为什么显示待连接或无法登录？
**解答**：
1. 检查电脑端代理设置是否能够正常直连 Telegram DC 服务器；
2. 检查该 Session 是否已经在其他设备被强制登出注销。

### Q3: 手机端机器人推送商机很准，如何充值月卡？
**解答**：直接在 [@wchjbot](https://t.me/wchjbot) 内点击【**购买续费**】，支持通过 EPUSDT/TRC20/TON 在线充值，亦可联系官方客服购买充值卡密秒兑换。

### Q4: 第一次打开提示「Windows 已保护你的电脑」或杀毒软件拦截？
**解答**：软件暂未购买代码签名证书，Windows 会对新软件提醒一次。点 **「更多信息」→「仍要运行」**；杀毒软件里选择「恢复 / 信任」并把安装目录加入白名单。详见 [安装指南](../getting_started/desktop_install.md)。

### Q5: macOS 提示「无法验证开发者」或「已损坏」？
**解答**：App 采用 Ad-hoc 签名。macOS 14 及更早：右键 → 打开；macOS 15 及更新：系统设置 → 隐私与安全性 → 「仍要打开」；仍提示已损坏则在终端执行 `xattr -dr com.apple.quarantine "/Applications/TG自动获客助手 旗舰商业版.app"`。

### Q6: 试用到期了，我的账号和数据还在吗？
**解答**：都在。试用到期只是暂停功能，激活授权后继续使用。数据保存在你电脑的用户数据目录，**卸载软件也不会删除**。

### Q7: 怎么购买、怎么激活卡密？
**解答**：见 [试用、购买与激活](../getting_started/activation_and_trial.md)。软件内收银台与官方机器人 [@oxbaimaobot](https://t.me/oxbaimaobot) 均可购买；忘记卡密可在「激活 / 找回卡密」窗口点「找回我的卡密」。

### Q8: 语音条发不出去 / 提示没有 ffmpeg？
**解答**：v5.0 的 Windows 与 macOS 安装包已内置转码组件，无需额外安装。如果仍提示缺少，请确认使用的是官方 v5.0 安装包（老版本需自行安装 ffmpeg），或把提示截图发给客服。

### Q9: 数据在哪里？怎么备份 / 迁移？
**解答**：Windows：`%LOCALAPPDATA%\WhiteCat\TG自动获客助手`；macOS：`~/Library/Application Support/WhiteCat/TG自动获客助手`。备份或迁移时关闭软件后复制整个文件夹即可。Session 相当于登录凭证，请勿外发。

---

## 二、官方技术支持通道

- 💬 **官方 Telegram 客服**: [@oxbaimao](https://t.me/oxbaimao)
- 🤖 **手机端获客机器人**: [@wchjbot](https://t.me/wchjbot)
- 🌐 **GitHub 官方发布仓**: [ChiSonKon/tg-sender-releases](https://github.com/ChiSonKon/tg-sender-releases)
- 🐛 **问题反馈与需求提交**: [GitHub Issues](https://github.com/ChiSonKon/tg-sender-releases/issues)

---

<p align="center">
  <a href="01_anti_ban.md">⬅️ 上一篇：防风控秘籍</a> | <a href="../README.md">🏠 返回文档首页</a>
</p>\n