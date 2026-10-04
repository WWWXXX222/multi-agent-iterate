# 方法来源与适配

本 skill 独立编写，提炼可迁移的方法，不复制 pstack 技能正文，也不打包视频字幕、公司资料或既往运行产物。不依赖安装 pstack。

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

上游 [pstack](https://github.com/backnotprop/pstack) 以 MIT 许可发布；本文件为方法归因，不改变其许可，也不为本仓库其他技能重新授权。
