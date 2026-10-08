# 📚 MCP 工具参考（共 53 项）

> 本页由软件里的工具定义自动生成（tools/docs/gen_mcp_reference.py），数量与名称与软件一致。5.0.0 为 45 项；**5.0.1 新增 8 项**（标 🆕）。
> 每个工具的完整参数以 Agent 里看到的工具说明为准。带「预览」的工具默认 `dry_run=true` 只预览，**不会真正发送 / 加群 / 退群 / 创建群**，确认后需显式传 `dry_run=false`。
> 软件默认以「只读」安全模式启动 MCP：预览 / 查看 / 扫描 / 评估类操作可用，会发消息、加群、改账号的动作需要开启写入权限。

## 账号与网络（9 项）

| 工具 | 说明 |
|---|---|
| `tg_list_accounts` | 列出当前所有托管的 Telegram 账号、完整手机号、昵称、用户名、连接状态与代理配置。 |
| `tg_manage_accounts` 🆕 | 账号的载入与登录：load_sessions 载入已有会话文件；import_session 导入一个 .session；login_start 用手机号开始登录并请求验证码，再用 login_submit 提交验证码，若账号有两步验证则继续用 login_submit 提交 password；check_status 批量检查账号状态（在线 / 双向受限 / 冻结 / 封禁 / Session失效 / 需人工验证；「未核实」= 限制状态没能核实，账号原有状态保持不变）；disconnect 断开；remove 删除账号及其会话文件（不可恢复，必须 confirm="DELETE <手机号>"）；set_2fa 设置 / 修改两步验证密码（必须 confirm="SET 2FA <手机号>"）。 |
| `tg_account_health` | 查看账号风控阶段与今日剩余配额：号龄分级（隔离 / 养号一二三阶段 / 正常使用）、阶段原因、24 小时内私信/群发言/拉人/进群的已用与上限、最近一次体检结果（出口国家与漂移、专属代理、资料完整度、SpamBot 状态）。超出配额的发送会被软件拒绝，请据此安排任务；解除限制只能由用户在软件界面中操作。 |
| `tg_check_account_status_full` | 检测账号的限制状态（名副其实）：先用 Telegram 自己的冻结信号判断是否被冻结，再向官方 @SpamBot 发 /start 读取本次的新回复（不会读到旧回复），结构化解析 正常无限制 / 临时受限（含 UTC 解封时间）/ 双向受限 / 永久封禁 / 冻结 / 需人工验证，并返回完整回复全文与可用申诉按钮。SpamBot 没回复、被限流、回复看不懂时 status=未核实、verified=false——不当成正常，也不会改动账号原有状态；确认正常会自动解除过时的「受限」标记。 |
| `tg_prune_restricted_accounts` | 清理失效 / 受限账号并把会话文件隔离归档。只清理「已核实」的：没连上 / 连接失败 / 检查出错的账号不会被清理；双向受限、冻结等软状态必须当场重新检测确认（重新检测为正常则解除标记、不清理）；封禁 / Session失效这类 Telegram 硬错误才凭记录处理。默认移到隔离目录 session_quarantine，quarantine=false 才会直接删除（不可恢复）。prune_types 决定清理哪些类型。 |
| `tg_account_warmup` | 养号：让指定账号在 channels 里模拟真人阅读（分批翻帖、停留、标记已读，会真实计入浏览量），持续 duration_minutes 分钟，后台运行，用 tg_smart_broadcast 的 status 查看、tg_stop_task(task_id=job_id) 停止。必须提供 channels；要先让账号入群请用 tg_join_and_verify。 |
| `tg_update_account_profile` | 修改指定 Telegram 账号的个人资料（昵称、姓氏、Bio 个人简介、公开用户名、个人主页展示频道）。 |
| `tg_convert_session` | 会话格式转换工具：查看会话结构摘要（只给密钥指纹，不泄露密钥），并在 Telethon .session / Pyrogram .session / 字符串 / Telegram Desktop tdata 之间互转（全部离线）。 |
| `tg_manage_proxies` | 代理池综合管理：查询当前配置的代理列表、批量导入新代理、快速测试代理连通性与网络延迟、以及为账号执行一号一IP的智能规划与绑定落盘。 |

## 发信与触达（8 项）

| 工具 | 说明 |
|---|---|
| `tg_send_message` | 向指定 Telegram 用户、群组或频道发送真实消息（支持文本、图片、表情、Markdown/HTML 格式，支持指定发信账号）。默认发送后回读核实消息确实存在（verified=true / false；false 表示接口没报错但回读没找到，可能被机器人 / 群规则立即删除）；失败时给出人话原因（限流、被限制、对方开启付费消息等）。 |
| `tg_batch_send_messages` | 批量向目标列表（私聊用户或群组清单）发送推广或营销消息，支持多账号轮询发信与间隔限速控制；按错误分类处理限流 / 失效账号（全部冷却则剩余目标标「未执行」并停止）。同步调用，目标多时请改用 tg_unified_send。 |
| `tg_unified_send` 🆕 | 与软件里「统一群发 / 私信群发」同一个引擎：多账号发到群 / 频道 / 用户，支持圆形视频（video_note_path）、多张图片相册（image_paths）；私信用户时还能「对方的动态」（story_view 浏览 / story_like 点赞 / story_reply 内容回复到对方动态）和「触达顺序」（预设名，或 contact_sequence_steps 自定义：浏览动态、点赞、电话、转发并置顶、文字、图片、文件、语音条、圆形视频、名片、内联消息、停顿）。 |
| `tg_force_invite` | 批量把目标用户拉进指定的群组 / 频道（与软件里「强拉加群」同一个引擎）：先核实每个账号确实在群里且有拉人权限；拉入后回读对方是否真在群里（Telegram 对隐私受限的人不报错而是悄悄不拉，不会再被算成功）；每个账号独立间隔 / 冷却 / 人数上限；隐私受限的人可选改发私信邀请链接（只算「已发邀请」）。后台运行，返回 job_id，用 tg_get_task_status / tg_smart_broadcast 的 status 查看，tg_stop_task 停止。dry_run=true 只核实账号、不拉任何人。账号的拉人风控额度照常生效。 |
| `tg_configure_auto_reply` | 配置私信自动回复规则（支持固定话术应答、AI 智能客服应答、关键词话术库、打字延迟与回复概率设定）。 |
| `tg_start_auto_reply` | 启动当前所有在线账号的私信自动回复与智能客服接待服务。 |
| `tg_stop_auto_reply` | 停止运行中的私信自动回复服务。 |
| `tg_manage_visitor_bots` | 访客机器人多开管理：配置多个 Bot Token、设定自动回复与广告内容、启动或停止所有访客机器人服务。 |

## 线索与监控（12 项）

| 工具 | 说明 |
|---|---|
| `tg_collect_members` | 从指定的公开或私有 Telegram 群组中采集活跃成员列表（可按近期活跃天数筛选，导出用户名与 ID）。 |
| `tg_manage_monitor_rules` | 管理关键词与群组消息监控规则（支持查询规则列表、新建规则、更新规则、删除规则或查询单条规则）。 |
| `tg_start_monitor` | 启动指定规则或全部已启用规则的群组消息实时监控与线索捕获引擎。 |
| `tg_stop_monitor` | 停止指定规则或全部正在运行的群组消息监听引擎。 |
| `tg_get_monitor_hits` | 检索监控引擎捕获到的实时商机线索与历史命中记录，支持按白名单过滤、按规则筛选与限制条数。 |
| `tg_manage_risk_blacklist` | 管理商机信誉核验与风控黑名单库（查询黑名单列表、单条/批量添加黑名单人员及标签、移除黑名单、清空黑名单、提取纯净白名单目标）。 |
| `tg_start_spy_engine` | 启动间谍获客引擎：潜伏在指定竞品或对标群组中，监听群内用户的提问与购买意图，调度账号协同推销与私聊精准截流。 |
| `tg_stop_spy_engine` | 停止运行中的间谍潜伏获客引擎。 |
| `tg_get_spy_status` | 查询间谍获客引擎当前的潜伏状态、监听群组数以及已成功截流/捕获的商机客户数量。 |
| `tg_desk_leads` | 查看会话工作台里的线索回复：被流水线私信过、并且已经回复的人（账号、对方、首次/最近回复时间、最新内容、是否已跟进），以及开启了 AI 接待的会话与其暂停原因（需人工跟进）。 |
| `tg_pipeline_status` | 查看自动化流水线：每条流水线的运行状态、配置、各阶段（去重 / 安全过滤 / 分配账号 / 模拟真人私信）排队与过滤数量、已完成数量与主要过滤/失败原因；传 pipeline_id 时附带最近的线索明细。 |
| `tg_pipeline_control` | 创建、修改、启动、暂停、停止、删除自动化流水线。目前支持 monitor_to_dm（监听即转化：关键词命中后自动去重、过滤机器人与黑名单、分配仍有私信配额的已养号账号、随机延迟并模拟输入后私信）。私信会受账号风控阶段与 24 小时配额约束；默认不使用监听号私信。启动后对真实用户发送消息，请先确认话术与监听规则。 |

## 群与频道（10 项）

| 工具 | 说明 |
|---|---|
| `tg_batch_create_groups_channels` | 批量创建 Telegram 超级群组、广播频道或普通群，支持随机 5 字符公开用户名、全员禁言、慢速模式与一键挂在个人主页。 |
| `tg_smart_broadcast` 🆕 | 感知群成员关系的多账号群发：先扫描各账号加入了哪些群，只把每个目标交给真正在群里、健康、未被禁言、还有额度的账号（同一目标只发一次，不重复）；账号被封 / 被禁言 / 限流时自动改派给同群其他账号；按账号与代理线路控制并发，适合几十到上千个账号、大量群的场景。action=scan 只扫描；start 默认 dry_run=true 只预览分配方案（不发送任何消息），确认后用 dry_run=false 才真正发送，发送在后台运行，用 status 查看进度、stop 停止（只停这个任务）。目标请用群的 @用户名、t.me 链接或群 ID；邀请链接无法匹配。 |
| `tg_group_funnel` 🆕 | 群质量漏斗 + 入群 / 退群：evaluate 只读评估群值不值得加（活跃度、真人比例、广告密度、机器人、重复内容、主题匹配、慢速模式 → 高价值 / 中等 / 低价值 / 待定 / 不可用 + 原因，评分是启发式推荐，不保证转化）；results 查看评估结果；lists 管理黑名单（加群默认跳过）与白名单（永不推荐退群）；join 按账号额度与已入群情况规划并执行加群；leave 推荐并执行退群。 |
| `tg_join_and_verify` 🆕 | 让指定账号加入指定的群 / 频道（公开用户名、t.me 链接、邀请链接都行），并在 pass_gate=true 时自动通过入群验证：按钮 / 算术题 / 跳转私聊机器人 /start 并作答 / 过群知识库 / AI 兜底（设置里配了 AI Key 才用）；通过后还会复查账号是否已解除禁言。后台运行，用 tg_smart_broadcast 的 status 查看每个群的结果（含验证详情）。规则判断不了的验证，会在结果里写明，此时可用 tg_verify_group_join 读出题目，再用 tg_solve_captcha 由你作答。 |
| `tg_create_bot` 🆕 | 用一个已登录的账号和 @BotFather 对话：create 创建机器人并返回 Token；list 列出该账号名下的机器人；token 取回已有机器人的 Token。BotFather 对创建数量 / 频率有限制，被限制时如实返回原因，不重试。Token 是机密，只返回给你，日志里打码。用户名必须以 bot 结尾。注意：BotFather 的回复格式未在真实环境逐项验证，解析不了时会返回（已打码的）原文。 |
| `tg_start_channel_clone` | 启动频道克隆搬运引擎：实时监控源频道，自动洗稿净化（过滤源联系方式与外部链接，替换为自己的专属信息）后同步发布到自己的目标频道。 |
| `tg_stop_channel_clone` | 停止运行中的频道克隆与内容搬运任务。 |
| `tg_start_ai_hype` | 启动 AI 炒群与模拟群聊引擎：调度多个在线账号在目标群组中扮演不同人设（技术专家、铁粉、谨慎者、散户等），基于指定话题自动模拟真人多轮对话，暖场烘托气氛。 |
| `tg_stop_ai_hype` | 停止当前正在运行的 AI 模拟炒群与水军群聊演练任务。 |
| `tg_get_ai_hype_status` | 查询当前 AI 模拟炒群引擎的运行状态、目标群、参与账号数及缓存的历史消息条数。 |

## 验证与风控（9 项）

| 工具 | 说明 |
|---|---|
| `tg_verify_group_join` | 针对指定群组进行入群人机验证扫描与自动挑战求解（支持 Shieldy、MissRose、数学运算、内联按钮点击等）。 |
| `tg_solve_captcha` | 向进群验证挑战或人机验证码提交解答（支持通过按钮索引点击指定答案，或向群组/私聊发送计算文本答案）。 |
| `tg_spambot_appeal` 🆕 | 与官方 @SpamBot 逐步对话，用于处理「双向限制 / 受限 / 封禁」的申诉。每次只做一步并原样返回 SpamBot 的回复与按钮：start=发 /start 查看当前状态；click=点某个按钮（button 为按钮文字，可部分匹配）；reply=发送一段文字；read=只读最近一条。重要：本工具不会替你编造任何资料。SpamBot 问到的情况（用途、怎么使用 Telegram 等）请如实回答；申诉文字请如实说明。遇到人机验证（验证码 / 图片题）会标记 human_verification=true，请人工在手机上完成，不要让 Agent 代做。 |
| `tg_check_target_safety` | 对指定 Telegram 用户做风险信号检查（检测受限状态、查询历史曾用名）。 |
| `tg_classify_targets` | 批量识别并分类目标类型（群组 Group / 超级群 Supergroup / 频道 Channel / 机器人 Bot / 普通用户 User）。 |
| `tg_probe_bot_features` | 真实探查一个 Telegram 机器人：发 /start、读取它声明的指令与简介，逐层点击菜单按钮，返回菜单树与「复现提示词」（有 AI 时由 AI 整理）。默认只读安全模式：跳过购买 / 支付 / 充值 / 提现 / 确认 / 删除类按钮（可用 skip_risky_buttons=false 在用户授权后放开），外链、小程序、支付发票、分享手机号 / 位置按钮无论如何都不点（skipped_buttons 列出原因）。 |
| `tg_analyze_group_ecosystem` | 真实读取目标群 / 频道的资料（成员 / 在线 / 简介 / 置顶）与近期消息样本，返回统计事实（内容构成、发言集中度、回复 / 转发 / 链接占比、高峰时段、外链与机器人、转化信号等）；deep_ai_analysis=true 且已配置 AI 时附带 AI 解读（ai_used / ai_error 说明是否用上）。读不到的数据列在 data_gaps，没有账号时返回 error，不提供示例数据。 |
| `tg_batch_report_target` | 批量举报目标：调度多个在线账号对 Telegram 上的违规账号、诈骗群组或侵权频道集中提交举报投诉。 |
| `tg_start_ad_clicker` | 自动广告点击引擎：调度账号批量浏览目标频道的赞助商广告（Sponsored Messages），或自动点击机器人内嵌键盘按钮（Inline Buttons）完成任务互动。 |

## 系统与任务（5 项）

| 工具 | 说明 |
|---|---|
| `tg_get_task_status` | 查询获客助手当前的后台任务执行状态、活跃并发队列与运行指标；传 job_id 可读取机器人探查的最终结果。 |
| `tg_stop_task` | 中止当前正在执行的后台获客任务（如群发、采集、强拉、批量建群）。 |
| `tg_get_system_config` | 查询当前系统的全局配置状态（API 凭证配置状态、前置网络代理 dialer_proxy 配置、网络探测结果与界面语言设置，敏感数据已安全打码）。 |
| `tg_update_system_config` | 修改并持久化系统的全局运行配置（如配置前置全局网络代理 dialer_proxy、系统语言、API 凭证，以及账号风控额度 account_guard）。account_guard.mode：stages=按号龄分阶段限额（默认）；custom=自定义全局额度（limits 里填每个账号每 24 小时的 dm 私信 / group_msg 群内发言 / invite 拉人 / join 进群上限，隔离状态的账号仍暂停）；off=关闭额度拦截（不限额，仍记录用量，风险由用户承担）。这是用户的决定权：调整前请向用户确认。 |
| `tg_agent_llm` 🆕 | 没有配置 AI API Key 时，软件里需要 AI 文字的功能（AI 炒群的发言与剧本生成、AI 接待、入群验证的 AI 兜底）可以改由你——接入的 AI Agent——代答。 |

## 使用上的几条重要说明

- **账号检测要看「是否核实」**：`tg_check_account_status_full` 先看 Telegram 的冻结信号，再读 @SpamBot **本次**的新回复；没回复 / 被限流 / 看不懂时 `status=未核实`、`verified=false`，不要当成正常。`tg_prune_restricted_accounts` 只清理已核实的账号，没连上的账号不会被清理。
- **机器人探查默认只读安全**：跳过购买 / 支付 / 充值 / 删除 / 确认类按钮，外链 / 小程序 / 支付发票 / 分享手机号 / 位置按钮任何时候都不点；`skip_risky_buttons=false` 需要用户明确授权。群管 / 验证 / 欢迎类机器人会被识别（`group_context.likely`），完整探查请用 `group_mode`（先 `dry_run` 预览，确认后在临时测试群里执行，结束自动清理）。
- **回读核实**：`tg_send_message` 默认发送后回读（`verified`）；统一群发 / 强拉加群同样以回读为准，日志里写明未核实的情况。
- **多轮与自动修复**：`tg_smart_broadcast` 支持 `rounds` 与 `heal`（默认关，会占用入群额度、有风控风险）。

- **账号风控额度由你决定**：默认按号龄分阶段限制每个账号 24 小时内的私信 / 群内发言 / 拉人 / 进群数量以保护新号；你可以在「设置 → 🛡 账号风控额度」改成统一的自定义额度或完全关闭拦截（风险自负），Agent 也可通过 `tg_update_system_config` 的 `account_guard` 调整（建议先征得你同意）。先用 `tg_account_health` 查看剩余额度。
- **入群有额度**：默认成熟账号约 20 次 / 24 小时（可自定义）；Telegram 对单个账号加入的群 / 频道总数也有上限。
- **没有 AI API Key 时**：`tg_agent_llm` 可让接入的 Agent 充当「大模型」，为 AI 炒群、AI 接待、入群验证的 AI 兜底代答（`enable` → 循环 `pending` → `respond`）。需要 Agent 在线并持续处理请求，每条回复消耗 Agent 一侧的 Token 且更慢；私信自动回复、频道克隆改写、机器人探查、运营分析仍需 API Key。
- **群质量评估只是推荐**：评分是启发式规则（活跃度、真人比例、广告密度、机器人占比、重复内容、主题匹配、慢速模式），不保证转化；加群 / 退群的决定权在你。
- **@SpamBot 申诉**：`tg_spambot_appeal` 只做逐步对话，不会替你编造任何资料，请如实作答；遇到人机验证需要你在手机上完成。
- **机器人 Token 是机密**：`tg_create_bot` 返回的 Token 只应保存在需要它的地方，泄露后到 @BotFather 里 `/revoke`。BotFather 的回复格式可能变化，解析不了时会返回（已打码的）原文。
- 未在真实 Telegram 环境逐项验证的部分（BotFather / SpamBot 的真实回复文案、千级账号规模下的吞吐与内存、Agent 代答的实际延迟）以实际使用为准，遇到问题请反馈。
