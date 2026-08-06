# AGENTS.md — Codex 工作规则（v3.0，本目录自动生效）

你为众筹详情页出图。每一帧用内置 GPT Image 2 直接生成；禁 Figma/HTML/SVG/代码排版拼图；禁只交提示词；给 GPT Image 2 的提示词一律英文,给用户说明用中文,每帧回附提示词。

## 开工自备料
project.json 有占位符→读 产品资料/ 自己填(claim/pain/proof/must_show,缺的标【待确认】禁编造)。
素材盘点：递归全库→出清单→点名缺口→挑 3-5 张定义外观的进 assets/product-plate/→写 product_spec(跨帧一致性锚)→shotlist 每帧注明所用素材,无素材标"纯生成"。

## 顺序
读 project.json+spec/00-brief → 产 shotlist.md(每帧:卖点/部件/尺寸/说服方式/字表)→ 停等确认 → 出图 out/(1360) → 自检 → out-680/。

## 硬约束
- 生成宽 1360(=680×2)；字号红线(1360画布):正文≥48/小标题≥72/主标题≥96/价格≥144
- 产品外观锁 product-plate 参考图: "Use the reference image for exact geometry, proportions, port layout and colour. Do not redesign the product."
- 全局禁令: no watermark, no invented logo, no gibberish lettering, no text other than the exact strings provided, no wrong port/button count
- 字表外一个字都不许烧；烧字单位规范(mm 小写连写)全帧扫描自查
- 同帧连续两次跑歪→降级"无字底图+后压字"并在 shotlist 记录

## 证明力铁律(违者返工,详见仓库 references/02+03+05)
- 图去字后仍能说明卖点；图示对照物=实物有投影落台面,禁悬浮线框
- 比例/距离帧交付报像素实测(±0.02)；100%窗=原图合焦区字节级拷贝,禁人脸
- 光学证据只裁真样张禁生成；禁生成可识别真实品牌实物(宿主机身用真照去标)
- GIF:4K母带重切/680×382满幅/逐帧黑边+标识扫描/首末帧差≥8/255/报时间码
- 长精确文本帧(表格/时间线/引言)不做——归 Claude 端 Figma 原生

## 交付
改动清单+逐帧素材路径与时间码+比例自报+contact sheet+GIF自检数据。
修改前原件备份 audit/pre-*/；退役帧移 audit/retired-*/。
