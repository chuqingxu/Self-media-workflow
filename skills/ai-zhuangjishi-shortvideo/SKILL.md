---
name: ai-zhuangjishi-shortvideo
description: Full short-video production workflow for the "AI 装机师" personal IP. Use when the user says the wake phrase "你用ai装机师skill", "你用 AI 装机师 skill", or asks for 抖音, 微信视频号, 小红书, 短视频, 个人 IP 引流, 概念讨论, 文案, 真人口播脚本, 拍摄清单, 素材转录, 剪映协作, HyperFrames 自动成片, 画中画, 多平台适配, 发布包装, 封面生成, image2 生图, 爆款封面, 封面样本, 私域承接, 数据复盘, 系列延伸, 爆款素材库, 爆款拆解, 竞品视频拆解, 素材库沉淀, 抖音合规, 星图预审, 外流风险, 第三方 App 引导风险, or true multi-agent collaboration for 二三线城市中小企业老板 content that sells AI access/token services or custom enterprise AI projects.
---

# AI 装机师短视频全流程

## Wake Phrase

The user's wake phrase is:

```text
你用ai装机师skill
```

Treat common spacing/capitalization variants as the same trigger, including:

```text
你用 AI 装机师 skill
你用ai装机师 skill
你用 AI装机师skill
```

When the wake phrase appears, enter this skill immediately and treat it as the user's standing explicit request for `real_multi_agent` collaboration for that task.

Required behavior after the wake phrase:

1. Start with Mode Gate.
2. State `Execution Mode: real_multi_agent` if subagent tools are available.
3. Spawn real subagents for independent work rather than role-playing them in the main thread.
4. Use a minimum production set when the task is content production: 口播编剧 Agent, 剪辑/平台优化 Agent, 审核 Agent, with the main assistant as 总控制片人.
5. Leave handoff/audit evidence when writing to a folder, or summarize each agent's independent output in the final answer.
6. If subagent tools are not available, state: `当前环境无法真实调用子 agent，本次只能 single_agent_with_reviews` and do not claim multi-agent collaboration.

## Non-Negotiable Truth Rule

Never pretend that role labels are real multi-agent collaboration.

Use these execution modes honestly:

- `real_multi_agent`: actual subagents are spawned through available multi-agent tools, each with an independent task, run/source id, returned artifact, and integration step.
- `single_agent_with_reviews`: one Codex instance follows multiple review perspectives without spawning subagents.
- `single_agent_direct`: one Codex instance produces the requested artifact directly.
- `tool_executed`: local tools such as HyperFrames, ffmpeg, transcription, browser, or file operations were actually used.

If the user uses the wake phrase or otherwise asks for real multi-agent collaboration and subagent tools are available, spawn subagents for independent work. If subagent tools are not available, say so and continue only as `single_agent_with_reviews` after making the limitation explicit.

Only call work `real_multi_agent` when there is checkable evidence:

- agent name or role
- run/source id when the tool provides one
- timestamp or execution order
- input brief
- returned conclusion or output file
- unresolved questions or risks

If any of these are missing, label the work `single_agent_with_reviews` or `single_agent_direct`.

Every run must leave an execution note in the final answer:

```text
Execution Mode: real_multi_agent / single_agent_with_reviews / single_agent_direct
Tool Execution: none / HyperFrames / ffmpeg / transcription / browser / other
参与 agent: [names or roles]
各自交付: [short list, or “none”]
审核结果: [pass / needs revision]
```

## Default Positioning

- 人设: AI 装机师
- 一句话介绍: 以前帮人装电脑系统，现在帮老板装公司 AI 系统。
- 目标人群: 二三线城市中小企业老板、小团队老板、传统行业老板
- 语气: 老板朋友型，懂技术但说人话；少讲术语，多讲老板能理解的场景和结果
- 出镜方式: 真人口播优先
- 平台: 抖音 + 微信视频号；需要时扩展到小红书、朋友圈
- 引流目标: 个人微信
- 承接产品: 中转站 token / AI 使用入口，企业定制 AI 项目

Core promise:

> 帮二三线中小企业老板，把 AI 从“听说很厉害”装成“公司每天能用”。

Avoid presenting the user as a generic AI blogger. Frame the work as installing, configuring, showing, and teaching a usable company AI system.

## Stage Router

First identify the user's current stage. Do not force every request into script generation.

| Stage | Trigger | Main output |
| --- | --- | --- |
| 概念澄清 | “我想拍一个概念” | 追问、角度判断、目标人群、转化目标 |
| 选题打磨 | 有粗主题但不清楚怎么拍 | 选题标题、平台角度、系列位置 |
| 脚本成型 | 要文案/口播 | 抖音版、视频号版、小红书版脚本 |
| 拍摄准备 | 要拍摄清单/怎么录 | 镜头、补拍素材、口播注意事项 |
| 素材分析 | 用户给了视频/音频 | 转录、金句、废话段、可用片段 |
| 成片剪辑 | 要剪辑/画中画/字幕 | 剪映清单或 HyperFrames 成片方案 |
| 封面生成 | 要封面、生图、image2、爆款封面、给封面样本 | 封面策略、image2 生图提示词、生成图、封面字排版与审核 |
| 平台适配 | 要发多个平台 | 各平台剪辑差异、标题、封面、话题 |
| 抖音合规预审 | 抖音发布前、星图预审、口播/字幕/封面/评论区检查 | 外流风险、第三方 App 引导风险、安全替代表达 |
| 私域承接 | 要引流/微信话术 | 评论区引导、加微信首句、分流问题 |
| 数据复盘 | 用户给发布数据 | 问题归因、保留/砍掉、下一轮实验 |
| 系列延伸 | 某条反馈好/想扩展 | 3-10 条延伸选题和拍摄优先级 |
| 嘉宾问题库 | 提到某期嘉宾、访谈、采访、预设问题 | 嘉宾画像、独家问题、追问、禁问、现场顺序 |
| 爆款拆解 | 用户给链接/视频/截图，或要求找素材 | 结构拆解、借鉴点、老初版本改写、入库文件 |

If the user is at 概念澄清 stage, ask only the few questions needed to move forward. Prefer 3-5 questions:

- 这条视频想让老板产生什么反应：认同、焦虑、信任、咨询，还是加微信？
- 有没有真实案例或场景可以讲？
- 这条更想承接 token / AI 入口，还是企业定制项目？
- 你准备真人正面口播，还是口播加屏幕演示？
- 目标平台优先级是抖音、视频号、小红书，还是都要？

## Real Multi-Agent Orchestration

Use real subagents only for independent work that can run in parallel. Keep the main assistant as 总控制片人.

Recommended agent roster:

| Agent | Responsibility | Model preference |
| --- | --- | --- |
| 总控制片人 | 判断阶段、拆任务、整合结果、决定下一步 | strongest available |
| 概念策划 Agent | 老板痛点、选题角度、系列位置 | strong reasoning |
| 口播编剧 Agent | 平台脚本、开头钩子、CTA | strong writing |
| 拍摄导演 Agent | 镜头、画面、补拍、现场执行 | standard |
| 素材整理 Agent | 转录、挑片段、删废话、金句标记 | fast/standard |
| 剪辑 Agent | 剪映清单、HyperFrames 画中画、字幕动效 | strong coding/video |
| 封面生成 Agent | 爆款封面策略、image2 生图、中文大字排版、封面 A/B 版本 | image2-capable image model + strong visual judgment |
| 平台优化 Agent | 抖音/视频号/小红书机制适配 | standard |
| 私域转化 Agent | 评论区、加微信、token/定制分流 | standard |
| 审核 Agent | 人设一致性、抖音/星图合规、转化链路、是否可拍 | strongest available |

Rules:

- Do not spawn agents just to make the process look serious.
- The wake phrase counts as explicit authorization for real multi-agent collaboration for that task.
- Spawn only when the user uses the wake phrase, explicitly asks for multi-agent collaboration, or the current task clearly benefits from parallel independent work and the user has authorized it.
- Give each subagent a concrete, bounded task and a required artifact.
- Do not let multiple agents edit the same file unless explicitly coordinating a merge.
- The main assistant must integrate the outputs and own the final decision.
- Always include an 审核 Agent before finalizing major scripts, published assets, or workflow changes.

Minimum real multi-agent set for a production task:

```text
总控制片人
口播编剧 Agent
剪辑/平台优化 Agent
审核 Agent
```

## Handoff Artifact

When handing work to any agent or moving between stages, use this compact card. For real multi-agent work, save or report a handoff record. If a folder is provided, store handoff records under `协作记录/`.

```markdown
# Agent Handoff

- Execution mode:
- Agent name:
- Run/source id:
- Timestamp or execution order:
- Input received:
- Output produced:
- Decisions made:
- Assumptions:
- Risks:
- Questions for next agent:
- Files created/changed:
```

Use this standard collaboration folder when writing files:

```text
协作记录/
  00-orchestrator-brief.md
  01-topic-strategy-handoff.md
  02-scriptwriter-output.md
  03-platform-editor-output.md
  04-conversion-review-output.md
  05-compliance-review-output.md
  06-final-merge-report.md
  audit-log.md
```

For ordinary single-video planning, also maintain a compact production card:

```markdown
# 视频生产卡

- 项目/主题:
- 当前阶段:
- 目标平台:
- 目标观众:
- 核心老板痛点:
- 这条内容的目标动作:
- 承接方向: token / 企业定制 / 信任沉淀
- 必须保留的信息:
- 禁止表达:
- 已有素材:
- 缺口:
- 下一步交付:
```

## Production Outputs

For a single concept that has been clarified, produce:

1. 概念定稿
2. 抖音版真人口播脚本
3. 视频号版真人口播脚本
4. 小红书/朋友圈改写建议 when requested
5. 3 个开头钩子
6. 拍摄清单
7. 画中画分镜表
8. 剪映协作清单 or HyperFrames 成片方案
9. 标题、封面字、封面生成方案、话题
10. 评论区引导
11. 加微信后的首句承接话术
12. 嘉宾专属问题库 when there is a guest/interview
13. 审核结果

For a batch plan, produce a table with:

- 日期
- 栏目
- 选题
- 目标老板痛点
- 抖音钩子
- 视频号角度
- 需要拍的素材
- CTA
- 承接方向
- 复盘指标

If the user provides a target folder and asks to落文件夹, create or update practical files there. Prefer:

```text
账号定位.md
7天测试计划.md
选题池/
单条视频/
素材/
脚本/
问题库/
拍摄清单/
剪辑工程/
封面/
发布文案/
复盘/
私域承接话术/
```

Do not write files unless the user clearly asks for filesystem output.

## Guest-Specific Question Bank

Use this when each episode has a guest, interviewee,老板,企业负责人, or field-test subject. Build a fresh question bank before scripting so every episode has practical, easy, catchy, non-repeating questions.

Core rule:

> 每期问题都必须围绕“这个嘉宾独有的行业、身份、业务场景和当下卡点”，不能复用泛泛的 AI 访谈问题。

For each guest, produce:

1. 嘉宾画像: 身份、行业、业务压力、他为什么适合这一期
2. 本期核心验证: 这期到底要验证 Codex/AI 能不能进入哪个真实业务
3. 10-15 个专属主问题: short, plain, practical, and shootable
4. 5-8 个现场追问: used when the answer is vague, boastful, or too abstract
5. 3-5 个抓人问题: sharper first-3-seconds hooks or trailer questions
6. 禁问/慎问: privacy, trade secrets, unlicensed endorsements, pricing promises, platform-sensitive claims
7. 问题顺序: 装前 -> 装中 -> 第一次反应 -> 业务迁移 -> 下一步

Question types to mix:

- 痛点问题: “你现在最烦、最重复、最没人处理的一件事是什么？”
- 判断问题: “这个回答能不能拿去给客户/员工/老板看？”
- 对比问题: “不用 AI 以前，这件事通常怎么做？卡在哪里？”
- 拆解问题: “如果把它放进公司流程，第一步应该接在哪？”
- 反应问题: “刚才哪一刻你觉得它不是玩具？”
- 风险问题: “你最担心员工乱用它造成什么问题？”
- 迁移问题: “如果只选一个场景先试，你会选客服、销售、文档、报价还是内部协作？”
- 回访问题: “明天你会不会自己再打开？如果会，你第一件事想问什么？”

Style requirements:

- Prefer one sentence per question, 10-24 Chinese characters when possible.
- Use老板能听懂的话; avoid model names, API, agent, vector database, RAG unless the guest is technical.
- Make questions answerable on camera in 10-30 seconds.
- Avoid “你怎么看 AI” unless it is immediately tied to a concrete业务动作.
- Do not repeat the same generic question across episodes; adapt by industry and role.
- Include at least one question that can become the video title or opening hook.

Useful output format:

```markdown
## 嘉宾专属问题库：{嘉宾名}

- 本期验证:
- 适合他的原因:
- 首发钩子问题:

| 阶段 | 问题 | 目的 | 可拍画面 |
| --- | --- | --- | --- |
| 装前 |  |  |  |
| 装中 |  |  |  |
| 反应 |  |  |  |
| 迁移 |  |  |  |
| 回访 |  |  |  |

### 现场追问

### 禁问/慎问
```

## Viral Material Library

Use a lightweight 爆款拆解库 to accumulate reusable structures. Prefer "user-fed first, assistant-found second":

- 用户喂素材: video link, local video path, screenshot, title/caption, performance data, or notes about why it felt useful.
- 助手找素材: only when the user asks; use public/searchable sources or browser access. Do not claim complete coverage of Douyin or 视频号 because platform access and recommendation feeds are limited.

When the user says `拆解这个爆款`, `放进爆款拆解库`, `建立素材库`, or gives a video/link for analysis, enter 爆款拆解 stage.

For each item, extract:

- 来源: 平台、链接、账号、发布时间 if available, performance data if provided
- 开头 3 秒: exact hook or visual opening
- 核心冲突: why the target viewer keeps watching
- 口播结构: setup, pain, turn, proof, CTA
- 镜头/画中画: main shot, screen demo, B-roll, text card, before/after
- 字幕节奏: density, emphasis words, line breaks
- 标题封面: title, cover text, thumbnail idea
- 评论区引导: prompt, keyword, pinned comment
- 为什么有效: audience, emotion, information density, platform fit
- 老初版本改写: how to adapt without copying
- 系列延伸: 3-5 follow-up angles
- 承接方向: token / 企业定制 / 信任沉淀

If writing files, use:

```text
爆款拆解库/
  抖音/
  视频号/
  小红书/
  通用结构/
```

Filename pattern:

```text
爆款拆解库/抖音/001-主题短名.md
```

Do not copy another creator's wording wholesale. Extract structure, rhythm, visual method, and conversion logic, then rewrite into the 老初/AI 装机师 voice.

When using 爆款拆解库 for a new concept, retrieve 1-3 relevant structures first, then produce the new script and shooting plan.

## Cover Generation Agent

Use this when the user asks for 封面, 封面生成, 生图, image2, 爆款封面, 封面样本, or gives cover references.

Hard rule:

> 封面生图阶段必须调用 image2 模型能力或当前环境中等价的 image2-capable image generation entrypoint. Do not pretend a prompt-only plan is an actual generated cover.

Execution modes:

- `tool_executed`: image2/image generation tool was actually called and produced an image.
- `single_agent_direct`: only a cover strategy or prompt was produced because image generation was unavailable.

If the environment exposes the image tool as `image_gen`, use it as the image2-capable generation entrypoint. If the tool does not expose a model selector, state that the available built-in image generation tool was used for the image2-required stage and do not claim a specific hidden model parameter was manually selected.

Default AI 装机师 cover style, based on the user's reference samples:

- Vertical cover, usually 3:4 or 4:5 for feed cover; adapt to 9:16 when used as a title card.
- 真人近景 or 半身, black T-shirt, direct eye contact, pointing at the camera or holding a phone.
- Background: office, park/greenery, factory/warehouse, storefront, or dark tech background; keep it blurred and secondary.
- Huge Chinese headline, 2-4 short lines, occupying 45%-65% of the canvas.
- Typography: extra-bold Chinese characters, black stroke, heavy drop shadow, slight 3D/extruded effect.
- Palette: white + cyan/blue/green + yellow/orange emphasis. Avoid weak pastel or elegant poster styles.
- Emotion: 老板朋友型 but blunt; the cover should feel like “老板，别踩坑，我跟你说句实话”.
- No QR code, no WeChat ID, no phone number, no platform logo, no misleading official badges.

Cover workflow:

1. Extract the video promise: target老板, pain, contradiction, result, platform.
2. Produce 3 cover text options, each under 18 Chinese characters for the main headline if possible.
3. Select one primary cover direction and one backup A/B direction.
4. Build an image2 prompt with: scene, creator pose, background, text layout, color, negative constraints.
5. Call image2/image generation when available.
6. Inspect the generated image for: readable Chinese text, face/hand issues, platform compliance, brand fit.
7. If Chinese text is wrong or unstable, keep the generated portrait/background as visual base and recommend deterministic text overlay via HyperFrames, CapCut/剪映, Canva, Figma, or a local image composition script.
8. Run Douyin/Xingtu Compliance Precheck on the final public-facing cover text for 抖音.

Important text rule:

Image generation may distort Chinese characters. For final publishing, exact Chinese cover text should be treated as a layout asset, not only as pixels produced by the image model. Prefer this production split when quality matters:

```text
image2 生成真人/背景/爆款视觉底图
  -> 人工或工具确定性叠加中文大字
  -> 审核 Agent 检查封面字与平台风险
```

Required output when generating covers:

```markdown
## 封面生成

- Execution Mode:
- Tool Execution:
- 目标平台:
- 画幅:
- 主封面字:
- 备选封面字:
- image2 提示词:
- 生成图路径或结果:
- 中文文字检查:
- 抖音/星图封面风险:
- 下一步修正:
```

## Editing Execution Modes

Choose the editing mode honestly.

### 剪映协作模式

Use when the user will edit manually or with a human editor. Output:

- 素材选择
- 剪辑节奏
- 删除/保留片段
- 画中画插入点
- 字幕稿
- 封面字
- BGM/音效建议
- 平台导出规格

### HyperFrames 自动成片模式

Use when the user wants Codex to actually build or render video compositions with overlays, picture-in-picture, animated captions, screen demos, title cards, or platform variants.

When using this mode, also use the HyperFrames and HyperFrames CLI skills if available. Follow their lint, inspect, preview, and render workflow. Use ffmpeg/transcription tools as needed.

Good fit for AI 装机师:

- 真人口播主画面
- AI 工具界面画中画
- 公司流程图/检查清单画中画
- 大字幕关键词强调
- 抖音竖版和视频号竖版差异版本

## Platform Rules

For 抖音:

- Target 30-45 seconds unless the user asks otherwise.
- Start with conflict, pain, or a blunt老板视角 question in the first 3 seconds.
- Optimize for completion rate: no long self-introduction, no abstract background.
- Use dense口播, quick cuts, large subtitles, and clear visual beats.
- Public CTA should usually stay inside Douyin interaction, such as comments, follow-up episodes, or in-platform engagement. Avoid hard-selling token, asking viewers to add WeChat, scan codes, search stores, or leave Douyin.

For 微信视频号:

- Target 45-90 seconds unless the user asks otherwise.
- Build trust with calmer pacing, specific examples, and a more conversational tone.
- Let the viewer feel the user is a reliable service provider, not just a hot-take creator.
- CTA can be softer and more relationship-oriented: “需要的话，我可以把检查清单发你。”

For 小红书:

- Use more experience-sharing and checklist language.
- Prefer cover text that looks like a note, not a hard ad.
- Convert the script into a caption/outline if requested.

## Content Pillars

- 装系统: 公司最基础的 AI 能力怎么搭起来
- 装软件: 哪些 AI 工具、入口、模型、token 值得先用
- 装驱动: 老板、员工、资料、流程、权限怎么接起来
- 杀病毒: 清掉 AI 焦虑、伪需求、乱买软件、员工乱用的问题
- 上门案例: 用匿名案例讲某类公司装完 AI 后哪里变快了
- 老板问答: 回答“我公司适不适合 AI”“先花多少钱”“员工不会用怎么办”等问题

## Conversion Logic

Public short videos should earn trust and collect intent. Public CTA should point to:

- 《中小老板 AI 装机检查清单》
- 《公司 AI 基础能力自测表》
- 《员工用 AI 不乱套的 5 个配置》

After the viewer adds WeChat, segment gently:

- If they only need a low-cost AI入口, recommend token/access after understanding usage volume and tool needs.
- If they mention company资料、客服、销售、报价、运营、知识库、自动化流程, move toward custom enterprise AI project diagnosis.
- If intent is unclear, ask: “你现在最想让 AI 先帮公司处理哪一块，客服、销售、文档，还是员工日常提效？”

## Douyin/Xingtu Compliance Precheck

Integrate `douyin-rule-check` as part of the 审核 Agent for 抖音/巨量星图 publication. This is a narrow precheck, not a full legal or all-platform compliance review.

Scope:

- A 类: 引导用户脱离平台交易或沟通
- B 类: 引导下载、搜索、打开、注册、扫码使用第三方 App

Must check all public-facing Douyin assets:

- 口播
- 字幕
- 封面字
- 标题
- 话题
- 评论区引导
- 置顶评论
- 画中画/截图/屏幕录制中的二维码、微信号、手机号、地址、第三方 App 搜索框

High-risk A 类 examples:

- 加微信、加我、私聊我、主页找联系方式
- 扫码、看二维码、看评论区联系方式
- 去淘宝/小店/线下门店/某地址找
- 私下交易、线下自取、站外咨询

High-risk B 类 examples:

- 下载某 App、应用商店搜某 App
- 打开某 App、注册某 App
- 扫码免费试用、去某 App 领福利
- 明确命令观众离开抖音完成第三方平台动作

Core judgment:

```text
分享式表达 usually safer.
命令式跳转 high risk.
```

Examples:

- Risky: “去 XX app 搜这个功能。”
- Safer: “我之前在 XX app 上看到过类似功能。”
- Risky: “加我微信，我发你检查清单。”
- Safer for Douyin: “这套检查清单我后面会继续拆。”
- Risky: “评论区留微信/看主页联系方式。”
- Safer for Douyin: “你可以在评论区说说你公司最卡的是客服、销售还是文档。”

Required output for Douyin precheck:

```markdown
## 抖音/星图合规预审

- 结论: pass / revise / high risk
- A 类外流风险:
- B 类第三方 App 风险:
- 具体风险句/画面:
- 建议替代表达:
- 范围外提醒:
```

If risk is found, revise the Douyin version before finalizing. Do not weaken 视频号/私域承接 logic globally; only make the Douyin public-facing version safer.

## Audit Gates

Use evidence-based audit gates.

### Mode Gate

- Declare `Execution Mode` before or at the start of substantive work when multi-agent collaboration is requested.
- Do not say “多 agent 已协作” unless actual subagents or independent model calls were used.
- If no subagent/tool evidence exists, say `single_agent_with_reviews`.

### Handoff Gate

- Each real agent stage must have a handoff record.
- If files are being written and a project folder exists, handoff records go under `协作记录/`.
- Missing handoff records mean the run cannot be claimed as `real_multi_agent`.

### Provenance Gate

- Final content must be traceable: who produced topic strategy, script, platform edit, conversion logic, and compliance review.
- In single-agent mode, mark these as review perspectives rather than agents.

### Contradiction Gate

- Check contradictions before final merge: strong Douyin conflict vs. trustworthy 视频号 tone, public no-hard-sell rule vs. private-domain sales logic, platform exposure vs. compliance.

### Final Claim Gate

- With handoff evidence: say `本次使用真实多 agent 协作`.
- Without handoff evidence: say `本次为单 agent 生成，并做多视角自检`.

Use three production review gates.

### 拍摄前审核

- Is the concept clear enough to shoot?
- Does it sound like AI 装机师?
- Is there one concrete老板场景?
- Is the CTA low-pressure and WeChat-friendly?
- Can the user realistically record this with available素材?

### 发布前审核

- First 3 seconds are strong enough?
- Any dead air, long intro, unclear subtitle, or missing picture-in-picture?
- Does each platform version have a reason to exist?
- Any exaggerated promise or risky claim?
- Is the private-domain next step clear?
- For 抖音/星图: run Douyin/Xingtu Compliance Precheck before finalizing口播、字幕、封面、评论区和画中画.

### 复盘后审核

- Was the failure/success caused by topic, hook, edit, cover, platform, or audience?
- Should the topic be repeated, remade, extended, or killed?
- Did it attract the right type of WeChat leads?

## Voice Rules

Use:

- “老板，你现在不是缺 AI 工具，是缺一套能跑起来的 AI 系统。”
- “十几年前装电脑系统，不能只装个 Windows，还得装驱动、装软件、调网络、教人怎么用。公司装 AI 也是一样。”
- “先别急着买一堆会员，先看入口、资料、流程、权限有没有装好。”

Avoid:

- 高高在上的专家口吻
- “颠覆”“遥遥领先”“100% 提效”等绝对化承诺
- 公开视频里直接强推 token 或价格
- 复杂技术名词堆叠
