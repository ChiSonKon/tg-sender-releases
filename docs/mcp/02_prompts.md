# 🎯 MCP 自然语言提示词库与实战案例（53 项工具）

> 💡 配置好 MCP 之后，您无需再动手点击复杂后台，只需在 AI Agent（Claude / Codex / Antigravity / Cursor）中发送自然语言，AI 将全自动编排调用 53 项获客工具完成闭环！

---

## 经典实战场景 1：1:1 毫秒级克隆目标大佬主页

**用户输入提示词**：
```text
请使用 whitecat-tg-assistant 的 MCP 工具，帮我把当前在线的账号 1 伪装成 @target_ceo 的形象。要求抓取原图头像、高仿昵称、同步简介签名，并对防封敏感词进行安全覆写。
```

**AI 智能体自动执行链**：
1. 抓取目标公开 Profile（昵称 / 简介 / 头像）；
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

## 5.0.1 新增场景 10：先混脸熟，再私信（对方的动态 + 触达顺序）

**用户输入提示词**：
```text
请先用 tg_unified_send 预览（dry_run）：对 targets.txt 里的用户，用账号 +85212345678 按「先混脸熟」顺序触达——先浏览对方的动态，再点赞，停几秒后发这段文字：「你好，看到你在做……」。对方没有动态的直接发私信。预览没问题再告诉我，我确认后再正式发送。
```

**AI 智能体自动执行链**：
1. 调用 `tg_unified_send`，`contact_sequence="warm_then_text"`、`story_fallback_dm=true`、`dry_run=true`，汇报预览（目标数、预计耗时、账号额度）；
2. 你确认后以 `dry_run=false` 执行，后台运行；
3. 用 `tg_get_task_status` / `tg_smart_broadcast` 的 status 查看进度，日志里会写明每个目标浏览 / 点赞 / 发送的结果与没有动态的目标。

> 提示：想自己定顺序时传 `contact_sequence_steps`，例如 `["story_view","story_like","pause","image","text"]`；图片可传 `image_paths` 一次发多张（相册）。

---

## 5.0.1 新增场景 11：探查一个机器人（群管类用群模式）

**用户输入提示词**：
```text
帮我探查 @some_bot 的功能，整理成菜单树和可复现的提示词。默认的安全规则不要改。如果它是需要拉进群才能完整探查的机器人，先给我看群模式的 dry_run 预览，我确认后再执行。
```

**AI 智能体自动执行链**：
1. 调用 `tg_probe_bot_features(bot_username="@some_bot")`（只读安全：跳过购买 / 支付 / 删除类按钮，外链 / 分享手机号等始终不点）；
2. 看结果里的 `group_context.likely`：为 `true` 时私聊结果不完整，按 `recommended_next_step` 先 `dry_run` 预览 `group_mode={"create_test_group": true}`，把「会创建临时测试群、拉入机器人并设为管理员、结束后删除群」告诉你并等确认；
3. 你确认后 `dry_run=false` 执行，汇报菜单树、`skipped_buttons`、`group_probe.cleanup` 与复现提示词。

---

<p align="center">
  <a href="01_quickstart.md">⬅️ 上一篇：一键配置 Agent</a> | <a href="../faq/01_anti_ban.md">下一篇：防风控与养号秘籍 ➡️</a>
</p>\n

---

## 5.0.1 新增场景 4：评估一批群，再决定加哪些

**用户输入提示词**：
```text
这是我收集的 200 个群链接（粘贴在后面）。请先评估质量，别加群。评估完告诉我高价值、中等、低价值各有多少，把低价值的列给我看原因，我来决定加黑名单还是照样加。
```

**AI 智能体自动执行链**：
1. 调用 `tg_group_funnel`（action=evaluate）后台读取群的公开信息和最近消息打分（不加群、不发消息）；
2. 用 `tg_smart_broadcast` 的 status 查看进度，完成后调用 `tg_group_funnel`（action=results）；
3. 汇报分级与原因；**由你决定**哪些进黑名单（`action=lists, op=add`），哪些照样加。

## 5.0.1 新增场景 5：按账号额度分配加群，并自动过验证

**用户输入提示词**：
```text
用我这 30 个在线账号，把名单里没进过的群每个群安排 2 个账号加入，跳过黑名单，先给我预览。
```

**AI 智能体自动执行链**：
1. 调用 `tg_group_funnel`（action=join，默认 dry_run=true）返回计划：多少次加群、多少个群被黑名单跳过、超出今日额度需要几天；
2. 你确认后用 `dry_run=false` 执行，进群后自动通过验证（点按钮 / 算术 / 跳转私聊机器人 / AI 兜底）；
3. 失败原因逐条写在结果里；规则判断不了的验证，用 `tg_verify_group_join` 读出题目，再用 `tg_solve_captcha` 由你作答。

## 5.0.1 新增场景 6：只让在群里的账号发，封号自动改派

**用户输入提示词**：
```text
用这 50 个号给这 100 个群发这条公告（文案在后面）。先预览分配方案，再发。
```

**AI 智能体自动执行链**：
1. 调用 `tg_smart_broadcast`（action=start，默认 dry_run=true）：扫描各账号入群情况，返回「多少个群有账号可发、多少个群没有任何所选账号在群里」；
2. 确认后 `dry_run=false` 后台发送；发送中账号被封 / 被禁言 / 限流，会自动把没做完的目标改派给同群其他账号；
3. 用 status 查看进度，需要时 `tg_stop_task`（传 job_id）只停这一个任务。

## 5.0.1 新增场景 8：没有 AI Key，让 Agent 充当「大模型」跑 AI 炒群

**用户输入提示词**：
```text
我没配 AI Key。请启用 Agent 代答，然后一直处理软件发来的 AI 请求：每条按它给的系统提示词和聊天记录写一句自然的群聊发言，直接交回去，别加角色名，也别暴露你是 AI。
```

**AI 智能体自动执行链**：
1. `tg_agent_llm`（action=enable）把 AI 供应商切到 mcp_agent；
2. 循环调用 `action=pending`（带 `wait_seconds` 长轮询）取走待办，写出回复后 `action=respond`；
3. 需要停止时 `action=disable` 切回原来的供应商。注意：这会消耗 Agent 一侧的 Token，且比直连 API 慢。

## 5.0.1 新增场景 9：调整账号风控额度

**用户输入提示词**：
```text
我的账号都是老号，别用新号阶段那套限制了。把每个账号每天的私信上限设成 150、进群 40，其它保持默认。
```

**AI 智能体自动执行链**：
1. 先向你确认（这是你的决定权）；
2. `tg_update_system_config`（`account_guard` = `{"mode": "custom", "limits": {"dm": 150, "join": 40}}`）立即生效；
3. `tg_account_health` 复查各账号的上限与剩余额度。

## 5.0.1 新增场景 7：创建机器人 / 处理 SpamBot 限制

**用户输入提示词**：
```text
用账号 1 通过 BotFather 创建一个机器人，名称「我的客服」，用户名 my_support_bot，把 Token 给我。
```
```text
账号 2 发不了消息，帮我看看 @SpamBot 怎么说，然后一步一步处理。我会告诉你该怎么回答。
```

**AI 智能体自动执行链**：
1. `tg_create_bot`（action=create）返回 Token（机密，请妥善保存）；BotFather 限制创建数量 / 频率时会如实返回原因；
2. `tg_spambot_appeal`（action=start）读出当前状态与按钮，由你决定点哪个按钮、如实回复什么文字；遇到人机验证需要你在手机上完成。

