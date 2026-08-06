---
name: ks-detail-page
description: 众筹详情页(KS/Indiegogo)全流程生产规范——从卖点骨架、Codex 生图指挥、逐帧证明力审计到 Figma 装配交付。当用户要做众筹详情页、审计详情页图文、指挥 Codex 出图、或为新品类(硬件/3C/影像等)复制这套流水线时使用。通用骨架+可替换品类层，配套 codex/ 目录为 Codex 端配置模板(tutti 共享上下文协作)。
---

# KS 详情页生产规范 (v3.0 · 固化自 Brightin Star 35mm APO 全程实战)

## 双端分工
- **Codex**：读 `codex/AGENTS.md` + style-token + project.json，用内置 GPT Image 2 生图，产出 out/(1360) 与 out-680/
- **Claude(你)**：骨架设计、文案、逐帧审计、仲裁、Figma 装配、交付打包。禁止代替 Codex 生图；禁止在 Figma 里排版拼"生成帧"(Figma 只做原生四类帧,见 06)

## 流程总纲（到成品交付为止）
0. **启动问询（必做第一步）**：不要让用户编辑任何文件。按 `project-layer/README.md` 的问询协议主动向用户提问（能从已给资料读出来的不问；一轮问完不挤牙膏），用回答自动填 project.json / 品类附录 / token 项目层
1. **起步**：基于问询结果完成品类层(竞品拆解/素材包盘点/卖点顺序/色彩)
2. **骨架**：五卖点漏斗排序 + 17 区块蓝图 → Figma 评审板(结构唯一事实源,保持干净)
3. **风格比选**：三风格试产 3 帧 → 用户定稿 → 锁 style-token
4. **文案**：大小标题+解释段全量先行(参考 `references/04-copy-rules.md` 密度标准)
5. **生产**：Codex 按 shotlist 出图；每轮交付必附自检数据(比例/黑边/运动量自报)
6. **审计**：逐帧证明力评分 + GIF 逐帧核验 + 仲裁(见 `references/07-audit-methods.md`)
7. **装配**：Figma 06 成品页热替换(匿名上传抓 imageHash 直写 fills)
8. **交付**：out-680 全量 + Figma 原生帧导出 → 「最终成品」+「分类装配包」双文件夹

## 铁律速查（违者返工）
- 图必须自己举证——去掉烧字后画面仍能说明卖点，否则重做
- 图文去重——图里烧过的话，相邻原生标题必须说互补信息
- 图示要素必须实物——对照物有体积有投影落在台面，禁悬浮线框/SVG 感
- 光学/性能证明只许真素材裁切，禁生成"证据"（图示线稿仅限机制/光路示意）
- 动图必须演示功能——"只会转"的删；逐帧自检不许抽样
- 长精确文本（表格/时间线/引言墙）禁生图，Figma 原生直出
- 一切比例/尺寸证明帧交付时像素实测自报，验收方独立复测
- 单位：焦距/口径 mm 小写连写(35mm/Ø39mm)；日期 BrE 无句点(Sep 2026)；标题 Title Case 动词必大写

## 参考文档
- references/01-structure.md — 卖点漏斗与区内结构语法
- references/02-proof-rules.md — 证明力与图示铁律
- references/03-gif-rules.md — GIF 治理与自检
- references/04-copy-rules.md — 文案密度/单位/标题规范
- references/05-honesty-gates.md — 真实性闸门
- references/06-figma-playbook.md — Figma 工法与坑
- references/07-audit-methods.md — 审计与验收工法
- references/08-category-lens.md — 品类附录·镜头/影像（换品类时替换本篇）
