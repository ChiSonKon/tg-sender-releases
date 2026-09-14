# 🎯 41 项 MCP 自然语言提示词库与实战案例

> 💡 配置好 MCP 之后，您无需再动手点击复杂后台，只需在 AI Agent（Claude / Codex / Antigravity / Cursor）中发送自然语言，AI 将全自动编排调用 41 项获客工具完成闭环！

---

## 经典实战场景 1：1:1 毫秒级克隆目标大佬主页

**用户输入提示词**：
```text
请使用 whitecat-tg-assistant 的 MCP 工具，帮我把当前在线的账号 1 伪装成 @target_ceo 的形象。要求抓取原图头像、高仿昵称、同步简介签名，并对防封敏感词进行安全覆写。
```

**AI 智能体自动执行链**：
1. 调用 `tg_probe_bot_features` 或抓取目标公开 Profile；
2. 下载目标头像并调用 `tg_update_account_profile` 更换头像；
3. 提取简介并替换商业引流链接，覆写昵称；
4. 汇报：“已成功将账号伪装完成，主页克隆度 99.8%！”

---

## 经典实战场景 2：万人群精准采集 ➔ 自动过滤 ➔ 批量强拉

**用户输入提示词**：
```text
请帮我从公开大群 https://t.me/industry_alpha 中采集最近 1 个月内发言的活跃潜客，剔除死号与僵尸号，然后调度 5 个在线发信账号，把他们批量拉入我的官方私域群 https://t.me/my_vip_community。
```

**AI 智能体自动执行链**：
1. 调用 `tg_collect_members` 并开启活跃度过滤；
2. 获得清洗后的潜客名单；
3. 调用 `tg_force_invite` 启动多账号轮换阶梯强拉；
4. 实时监控加群进度，遇验证码自动调用 `tg_solve_captcha` 破解。

---

## 经典实战场景 3：商机关键词全域监听与信誉核验

**用户输入提示词**：
```text
请启动关键词监听，监控词包括“采购”、“求购开发”、“寻求代理”。一旦发现线索，先与本地风控黑名单比对，剔除老赖和高危号，将安全买家信息整理并直接通过 Telegram 发送给我。
```

**AI 智能体自动执行链**：
1. 调用 `tg_manage_monitor_rules` 录入关键词规则；
2. 调用 `tg_start_monitor` 开启监听；
3. 调用 `tg_manage_risk_blacklist` 毫秒级核验发言人信誉；
4. 调用 `tg_send_message` 将纯净买家白名单实时推送到您的私聊窗口。

---

<p align="center">
  <a href="01_quickstart.md">⬅️ 上一篇：一键配置 Agent</a> | <a href="../faq/01_anti_ban.md">下一篇：防风控与养号秘籍 ➡️</a>
</p>\n