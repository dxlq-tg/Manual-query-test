# 带来源定位的回答示例

## 示例一：明确型号的参数问题

问题：`CT511 LTE频段是多少？`

示例回答：

> 仓库检索状态：已检索  
> 结论状态：明确  
> 结论：DX-CT511 支持资料表中列出的 FDD Band 1/3/5/8 和 TDD Band 34/38/39/40/41。
>
> 参考位置：《DX-CT511&DX-CT511N-4G模块技术手册》，“射频功能介绍”，PDF 第 32 页，工作频段表。  
> evidence_id：`dx-ct511-ct511n-technical-manual-p0197-ev` 至 `dx-ct511-ct511n-technical-manual-p0205-ev`

这些记录位于 `dataset/by_product/dx-ct511/parameters.jsonl`，包含每个频段的上行、下行范围和 PDF 页内坐标。回答不得把 CT511N 专有的 GNSS 内容加入 CT511 结论。

## 示例二：跨型号功能比较

问题：`Wi-Fi模块哪款支持HTTP功能？`

示例回答：

> 仓库检索状态：已检索  
> 结论状态：无法确认  
> 结论：当前仓库只收录一款 Wi-Fi 模块 DX-WF24；现有资料仅“提及 HTTP”，不足以确认模块支持 HTTP 协议功能。
>
> 检索范围：WF 系列当前已收录的 DX-WF24。  
> 参考位置：《DX-WF24 通讯操作示例》，“附件 → TCP多连接示例 → 创建数据库&添加数据”，PDF 第 20 页。原文是访问外部服务器管理页面 `http://localhost:18083`，不是模块 HTTP 指令或功能声明。  
> evidence_id：`dx-wf24-communication-examples-ev-b0285`
>
> 技术支持提示：当前仓库资料不足，无法可靠确认 DX-WF24 是否支持 HTTP 协议功能。建议联系公司技术支持，并提供产品型号、硬件/固件版本、应用场景及上述参考位置进行确认。

该判断先来自 `dataset/capabilities.jsonl` 中 DX-WF24 的 `http / mentioned` 候选，再用证据原文复核。因此不能把“资料中出现 HTTP 字样”写成“产品支持 HTTP”。

## 最小引用要求

每个结论至少返回：适用型号、手册名、章节或表格、PDF 页码和 `evidence_id`。页码来自 JSONL 的 `source_locators`；业务 AI 不必解析 PDF，人员可按仓库中的 `document.pdf` 复核。

## 无法访问仓库时

如果 AI 没有成功读取 GitHub 仓库，不应回答产品问题，只回复：

> 仓库检索状态：无法访问。当前无法读取指定仓库，请确认已启用网页、联网或 GitHub 访问能力后重试。
