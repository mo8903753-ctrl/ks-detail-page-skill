# Figma 工法（Claude 端）

## 页面组织
04 评审板=结构与文案唯一事实源(保持干净) / 05 装配版 / 06 最终成品(auto-layout 竖栈)。

## Figma 原生帧（禁 Codex 生成的类型）
长精确文本类：参数表/对比表/时间线/运费表/引言墙。白字号红线(680宽)：日期26/正文24/注20。
引言墙配产品横带：母带抽帧+底缘90px渐变融入暗底，文本层保持可编辑。

## 上传热替换标准姿势
1. upload_assets 匿名批量拿 URL（nodeId 模式会静默失败,禁用）
2. multipart POST(文件名=图层名)，响应直接给 imageHash+placedOnNodeId
3. use_figma 批量 `fills=[{type:'IMAGE',scaleMode:'FILL',imageHash}]` 直写目标节点
4. 删除落在第一页的临时帧(按 placedOnNodeId)；回读 fills 校验 hash

## 已踩坑清单
- auto-layout 栈内挪位用 insertChild(index)，改 y 无效
- text.resize() 会把 textAutoResize 锁死为 NONE → 高度冻结；先设宽再重设 textAutoResize='HEIGHT' 让高度回流后再排版
- 新建文本高度需二次读取(同 session 先提交后量)
- 占位帧可能自带 auto-layout + 红虚线描边，改建前 layoutMode='NONE' + strokes=[]
- 每次 use_figma 前 setCurrentPageAsync；文本改动前逐 segment loadFontAsync
- SVG 导入后 resize 不缩 strokeWeight，需按导入实高同步乘系数
- figma 资产短时效 URL 下载失败时换 curl_cffi impersonate 通道
