# 📚 MCP 工具参考（共 53 项）

> 本页由软件里的工具定义自动生成，数量与名称与软件一致。5.0.0 为 45 项；**5.0.1 新增 8 项**（标 🆕）。
> 每个工具的完整参数以 Agent 里看到的工具说明为准。带「预览」的工具默认 `dry_run=true` 只预览，**不会真正发送 / 加群 / 退群**，确认后需显式传 `dry_run=false`。
> 软件默认以「只读」安全模式启动 MCP：预览 / 查看 / 扫描 / 评估类操作可用，会发消息、加群、改账号的动作需要开启写入权限。

## 账号与网络（9 项）

| 工具 | 说明 |
|---|---|
| `tg_list_accounts` | 列出当前所有托管的 Telegram 账号、完整手机号、昵称、用户名、连接状态与代理配置。 |
| `tg_manage_accounts` 🆕 | 账号的载入与登录：load_sessions 载入已有会话文件；import_session 导入一个 .session；login_start 用手机号开始登录并请求验证码，再用 login_submit 提交验证码，若账号有两步验证则继续用 login_submit 提交 password；ch…。 |
| `tg_account_health` | 查看账号风控阶段与今日剩余配额：号龄分级（隔离 / 养号一二三阶段 / 正常使用）、阶段原因、24 小时内私信/群发言/拉人/进群的已用与上限、最近一次体检结果（出口国家与漂移、专属代理、资料完整度、SpamBot 状态）。 |
| `tg_check_account_status_full` | 向官方 @SpamBot 发起深度诊断，获取完整官方回复全文，结构化解析受限原因、UTC 解封时间与可用申诉按钮。 |
| `tg_prune_restricted_accounts` | 批量检测全量托管账号健康度，自动清理群发禁言、双向受限、冻结或失效 Session，并一键安全隔离归档。 |
| `tg_account_warmup` | 养号：让指定账号在 channels 里模拟真人阅读（分批翻帖、停留、标记已读，会真实计入浏览量），持续 duration_minutes 分钟，后台运行，用 tg_smart_broadcast 的 status 查看、tg_stop_task(task_id=job_id) 停止。 |
| `tg_update_account_profile` | 修改指定 Telegram 账号的个人资料（昵称、姓氏、Bio 个人简介、公开用户名、个人主页展示频道）。 |
| `tg_convert_session` | 会话格式转换工具：查看会话结构摘要（只给密钥指纹，不泄露密钥），并在 Telethon .session / Pyrogram .session / 字符串 / Telegram Desktop tdata 之间互转（全部离线）。 |
| `tg_manage_proxies` | 代理池综合管理：查询当前配置的代理列表、批量导入新代理、快速测试代理连通性与网络延迟、以及为账号执行一号一IP的智能规划与绑定落盘。 |

## 发信与触达（8 项）

| 工具 | 说明 |
|---|---|
| `tg_send_message` | 向指定 Telegram 用户、群组或频道发送真实消息（支持文本、图片、表情、Markdown/HTML 格式，支持指定发信账号）。 |
| `tg_batch_send_messages` | 批量向目标列表（私聊用户或群组清单）发送推广或营销消息，支持多账号轮询发信与间隔限速控制。 |
| `tg_unified_send` 🆕 | 与软件里「统一群发」同一个引擎：多账号发到群 / 频道 / 用户，支持频道评论（最新帖 / 指定帖 / 秒评未来帖）、投票 / 清单、语音条、先响铃后发语音再发文字、转发、定时撤回、多线程、失败重试、循环轮次、限流冷却开关与休息间隔，以及联系人名片（`contact_card`）与内联机器人消息（`inline_query`，如 `@PostBot 帖子ID`）。 |
| `tg_force_invite` | 批量把目标用户拉进指定的群 / 频道（5.0.1 起与软件里「强拉加群」同一引擎）：先核实账号在群里且有拉人权限，检查 Telegram 返回的 `missing_invitees` 并回读对方是否真在群里（隐私受限的人不再被算成功），每个账号独立间隔 / 冷却 / 人数上限，可选私信邀请降级；后台运行返回 `job_id`，`dry_run=true` 只核实账号。 |
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
| `tg_pipeline_control` | 创建、修改、启动、暂停、停止、删除自动化流水线。 |

## 群与频道（10 项）

| 工具 | 说明 |
|---|---|
| `tg_batch_create_groups_channels` | 批量创建 Telegram 超级群组、广播频道或普通群，支持随机 5 字符公开用户名、全员禁言、慢速模式与一键挂在个人主页。 |
| `tg_smart_broadcast` 🆕 | 感知群成员关系的多账号群发：先扫描各账号加入了哪些群，只把每个目标交给真正在群里、健康、未被禁言、还有额度的账号（同一目标只发一次，不重复）；账号被封 / 被禁言 / 限流时自动改派给同群其他账号；按账号与代理线路控制并发，适合几十到上千个账号、大量群的场景。 |
| `tg_group_funnel` 🆕 | 群质量漏斗 + 入群 / 退群：evaluate 只读评估群值不值得加（活跃度、真人比例、广告密度、机器人、重复内容、主题匹配、慢速模式 → 高价值 / 中等 / 低价值 / 待定 / 不可用 + 原因，评分是启发式推荐，不保证转化）；results 查看评估结果；lists 管理黑名单（加群默认跳…。 |
| `tg_join_and_verify` 🆕 | 让指定账号加入指定的群 / 频道（公开用户名、t.me 链接、邀请链接都行），并在 pass_gate=true 时自动通过入群验证：按钮 / 算术题 / 跳转私聊机器人 /start 并作答 / 过群知识库 / AI 兜底（设置里配了 AI Key 才用）；通过后还会复查账号是否已解除禁言。 |
| `tg_create_bot` 🆕 | 用一个已登录的账号和 @BotFather 对话：create 创建机器人并返回 Token；list 列出该账号名下的机器人；token 取回已有机器人的 Token。 |
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
| `tg_spambot_appeal` 🆕 | 与官方 @SpamBot 逐步对话，用于处理「双向限制 / 受限 / 封禁」的申诉。 |
| `tg_check_target_safety` | 对指定 Telegram 用户做风险信号检查（检测受限状态、查询历史曾用名）。 |
| `tg_classify_targets` | 批量识别并分类目标类型（群组 Group / 超级群 Supergroup / 频道 Channel / 机器人 Bot / 普通用户 User）。 |
| `tg_probe_bot_features` | 向指定 Telegram 机器人发送 /start 并深度递归点击所有透明内联按钮 (Inline Keyboard)，提取按钮矩阵、Emoji 视觉风格，并逆向产出 1:1 Agent System Prompt。 |
| `tg_analyze_group_ecosystem` | 读取目标群组/频道的近期消息样本并生成社群运营生态与受众画像统计分析。 |
| `tg_batch_report_target` | 批量举报目标：调度多个在线账号对 Telegram 上的违规账号、诈骗群组或侵权频道集中提交举报投诉。 |
| `tg_start_ad_clicker` | 自动广告点击引擎：调度账号批量浏览目标频道的赞助商广告（Sponsored Messages），或自动点击机器人内嵌键盘按钮（Inline Buttons）完成任务互动。 |

## 系统与任务（5 项）

| 工具 | 说明 |
|---|---|
| `tg_get_task_status` | 查询获客助手当前的后台任务执行状态、活跃并发队列与运行指标。 |
| `tg_stop_task` | 中止当前正在执行的后台获客任务（如群发、采集、强拉、批量建群）。 |
| `tg_get_system_config` | 查询当前系统的全局配置状态（API 凭证配置状态、前置网络代理 dialer_proxy 配置、网络探测结果与界面语言设置，敏感数据已安全打码）。 |
| `tg_update_system_config` | 修改并持久化系统的全局运行配置（如配置前置全局网络代理 dialer_proxy、系统语言、API 凭证，以及账号风控额度 account_guard）。 |
| `tg_agent_llm` 🆕 | 没有配置 AI API Key 时，软件里需要 AI 文字的功能（AI 炒群的发言与剧本生成、AI 接待、入群验证的 AI 兜底）可以改由你——接入的 AI Agent——代答。 |

## 使用上的几条重要说明

- **账号风控额度由你决定**：默认按号龄分阶段限制每个账号 24 小时内的私信 / 群内发言 / 拉人 / 进群数量以保护新号；你可以在「设置 → 🛡 账号风控额度」改成统一的自定义额度或完全关闭拦截（风险自负），Agent 也可通过 `tg_update_system_config` 的 `account_guard` 调整（建议先征得你同意）。先用 `tg_account_health` 查看剩余额度。
- **入群有额度**：默认成熟账号约 20 次 / 24 小时（可自定义）；Telegram 对单个账号加入的群 / 频道总数也有上限。
- **没有 AI API Key 时**：`tg_agent_llm` 可让接入的 Agent 充当「大模型」，为 AI 炒群、AI 接待、入群验证的 AI 兜底代答（`enable` → 循环 `pending` → `respond`）。需要 Agent 在线并持续处理请求，每条回复消耗 Agent 一侧的 Token 且更慢；私信自动回复、频道克隆改写、机器人探查、运营分析仍需 API Key。
- **群质量评估只是推荐**：评分是启发式规则（活跃度、真人比例、广告密度、机器人占比、重复内容、主题匹配、慢速模式），不保证转化；加群 / 退群的决定权在你。
- **@SpamBot 申诉**：`tg_spambot_appeal` 只做逐步对话，不会替你编造任何资料，请如实作答；遇到人机验证需要你在手机上完成。
- **机器人 Token 是机密**：`tg_create_bot` 返回的 Token 只应保存在需要它的地方，泄露后到 @BotFather 里 `/revoke`。BotFather 的回复格式可能变化，解析不了时会返回（已打码的）原文。
- 未在真实 Telegram 环境逐项验证的部分（BotFather / SpamBot 的真实回复文案、千级账号规模下的吞吐与内存、Agent 代答的实际延迟）以实际使用为准，遇到问题请反馈。
