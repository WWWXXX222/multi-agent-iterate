# 方法来源与适配

本 skill 独立编写，提炼可迁移的方法，不复制上游技能或配置正文，也不打包视频字幕、公司资料或既往运行产物。不依赖安装 pstack 或 Claude Code。

核对日期：2026-10-02。pstack 参考版本：`157aae39a733135e93d8b5b19ff62c6a84b0ad56`。链接固定到此次阅读版本，便于以后复查；不把上游规则作为本 skill 的隐含执行指令。

## pstack 的具体启发

- [arena](https://github.com/backnotprop/pstack/blob/157aae39a733135e93d8b5b19ff62c6a84b0ad56/skills/arena/SKILL.md)：同题独立候选，读实际产物，选底稿、少量吸收与重新验证。
- [swarm](https://github.com/backnotprop/pstack/blob/157aae39a733135e93d8b5b19ff62c6a84b0ad56/skills/swarm/SKILL.md)：明确完成条件，分片或竞赛式并行，隔离输出，汇总掉队与缺口。
- [interrogate](https://github.com/backnotprop/pstack/blob/157aae39a733135e93d8b5b19ff62c6a84b0ad56/skills/interrogate/SKILL.md)：多个独立 reviewer 质疑，主控逐项裁决，评审本身不自动修改产物。
- [figure-it-out](https://github.com/backnotprop/pstack/blob/157aae39a733135e93d8b5b19ff62c6a84b0ad56/skills/figure-it-out/SKILL.md)：先定义可检验的完成条件，建立基线，以假设—改变—测量循环推进。
- [show-me-your-work](https://github.com/backnotprop/pstack/blob/157aae39a733135e93d8b5b19ff62c6a84b0ad56/skills/show-me-your-work/SKILL.md)：让重要决策、证据、失败和取舍可回溯。
- [hillclimb](https://github.com/backnotprop/pstack/blob/157aae39a733135e93d8b5b19ff62c6a84b0ad56/skills/poteto-mode/playbooks/hillclimb.md)：固定测量条件，逐次验证，保留有效改变，撤回无效尝试。
- [reflect](https://github.com/backnotprop/pstack/blob/157aae39a733135e93d8b5b19ff62c6a84b0ad56/skills/reflect/SKILL.md)：把真实返工转成具体改进，优先考虑结构化约束，避免堆叠泛化规则。

## 视频的启发

已读取用户给定[视频的英文自动字幕](https://www.youtube.com/watch?v=NjoZoUm85x0)，自动字幕可能有识别误差；以下为意译的工作流启发，不是逐字引语。

- [约 03:52–04:12](https://www.youtube.com/watch?v=NjoZoUm85x0&t=232s)：让 agent 自己运行、收集证据并迭代改善。
- [约 09:09–12:30](https://www.youtube.com/watch?v=NjoZoUm85x0&t=549s)：可重复的验证工具配合功能地图，减少每次重新猜操作和重写验证脚本。此处推广为“条件—观察入口—通过标准—证据”的验证地图。
- [约 36:09–37:27](https://www.youtube.com/watch?v=NjoZoUm85x0&t=2169s)：对反复人工纠正的问题，优先从架构/数据结构、静态检查等层面消除，再以规则与 skill 补充。

视频主要讨论工程环境、验证与信任；arena/swarm/interrogate 的具体编排来自仓库。两者分别引用，不把仓库方法都说成视频里讲过。

## 本 skill 的明确适配

1. 跨领域可用。主观规划不能用“测试全绿”证明现实商业效果，证据未知时允许有条件交付。
2. 默认继承当前可用模型；具备条件时才做真实跨模型评审，不硬编码上游模型名，也不把同模型换人设描述为多模型。
3. 默认有限轮次与停滞结束，控制日常任务成本；这区别于上游 autonomous-run 的持续运行模式。用户明确的持续目标按当前工具与预算约束处理，不虚构后台调度。
4. 验收条件与作者分开。硬约束对候选公开，排序权重/验收样例可留给裁判；不靠投票或分数上涨通过。
5. 范围和授权来自当前用户任务，已有授权沿用。Skill 不隐含代码发布、对外消息、业务系统写入或定时任务。
6. 只沉淀通用机制。OKR 只是可选应用场景，飞书、双语网站与上线操作不属于核心流程。
7. 后续按用户反馈补充结构挑战、文档/coding/混合验收和隔离回放方法：允许重新审视可变框架，要求重要建议带具体改法及价值判断，避免把单一案例的分类固化。这些是本 skill 的扩展，不归称为视频或 pstack 原有规则；不发布业务案例原文。

## Boris Cherny 分享与截图来源核对

核对日期：2026-10-05。以下是 2026 年 1 月的历史分享及此次读取的官方文档，不把历史工具配置称为当前唯一推荐。

### 原作者分享

[Boris 的线程首帖](https://x.com/bcherny/status/2017742741636321619)发表于 2026-01-31 23:32 UTC，介绍来自 Claude Code 团队的使用经验。以下逐条链接的作者、日期和开头正文已通过 X 官方公开嵌入数据核对：

| 原帖 | 可直接核对的内容 | 本 skill 中的对应 |
| --- | --- | --- |
| [第 2 条：计划](https://x.com/bcherny/status/2017742745365057733) | 复杂任务先计划，另一个上下文评审计划 | 先明确实施与验收；复用独立评审名额 |
| [第 3 条：项目经验](https://x.com/bcherny/status/2017742747067945390) | 被纠正后更新项目指导，避免重复错误 | 有适用条件与验证办法的经验记录 |
| [第 5 条：自主排障](https://x.com/bcherny/status/2017742750473720121) | 给出问题或失败 CI，由 agent 完成修复 | 主动诊断、修复及复验 |
| [第 6 条：证明结果](https://x.com/bcherny/status/2017742752566632544) | 要求证明有效，比较主分支与修改后的行为 | 相同验收条件下检查前后证据 |
| [第 8 条：子 agent](https://x.com/bcherny/status/2017742755737555434) | 委派独立任务，保持主上下文聚焦 | 单一明确职责、精简回传、按需读取证据 |

**核验限制**：X 网页正文访问受限，官方 `cdn.syndication.twimg.com/tweet-result` 与 `publish.twitter.com/oembed` 返回的长帖内容有截断，未据此声称通读全部原帖。[TIGZIG 的线程转录](https://xlwings-lite.tigzig.com/post/claude-code-top-10-tips-from-boris-cherny)可辅助阅读未展开部分，但属于第三方转录，不能替代原作者核验。

### 官方文档与社区模板分开

- [Claude Code 官方最佳实践](https://code.claude.com/docs/en/best-practices)：已读取关于可执行验收、探索后计划、小修改跳过规划、及时纠偏、子 agent 调查和精简项目指导的相关章节。它支持本文采用的通用方法；并不要求所有任务统一写入某个 `tasks/` 路径。
- 截图英文对应文本可见于 [gavinwright-engr 的社区 Gist](https://gist.github.com/gavinwright-engr/499e96574d7a10d939b34388a3774924)，创建于 2026-02-26，读取版本 `82211cf6dc558981378428396bf7630d223b41d1`。其标题归于 Boris，但发布者不是 Boris；未找到足以证明整份配置由他撰写或首发的证据，也不声称该 Gist 是最早版本。
- 因而不把模板中的固定“三步以上”、强制 `tasks/todo.md` / `tasks/lessons.md`、每次实施前确认等细则归为已核实的 Boris 原话；不复制模板正文，不采用“提升 10 倍”的效果宣传。

### 此次更新的适配判断

增加失效前提触发的局部重规划、实施与验证共同计划、主动根因排查、简洁方案的收益检查，以及经验的记录—读取—验证—修剪循环。具体触发条件、文档验收、预算连续累计、已有授权沿用和经验存放边界是本 skill 的设计；不冒充上游逐字规则。

原有独立上下文、按需并行、验收证据与有限轮次继续沿用。Boris 的工具名称、历史模型选择、权限配置和并行数量不直接移植；适配不会自动更改宿主模式、权限或全局记忆。

上游 [pstack](https://github.com/backnotprop/pstack) 以 MIT 许可发布；本文件为方法归因，不改变其许可，也不为本仓库其他技能重新授权。
