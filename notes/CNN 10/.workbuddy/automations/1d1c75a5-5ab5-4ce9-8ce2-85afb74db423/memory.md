# Automation Memory: Order 1 - CNN10 生词笔记格式统一

## 2026-09-02 (手动示范执行)
- 巡检范围：生词/ 目录（CNN原文/ 不处理）。
- 文件：`生词/Instagram.md`
- 修改 1 处：
  - `upfront:[only before noun] paid in advance...` → 词条加粗为首字母加大+整词加粗（`**<span style="font-size: larger; font-weight: bold;">U</span>pfront**: `），冒号后补一个空格，语法标签 `[only before noun]` 原样保留
  - 例句 `- There will be an upfront fee of 4%.`（完整句）→ `e.g - *There will be an upfront fee of 4%.*`，8 空格缩进
- 保留未处理：`contingent:`（无释义的不完整条目，规则 6 不做内容补写，仅记录）
- 说明：首字母"加大"用 HTML span 实现（`<span style="font-size: larger; font-weight: bold;">`），与 VOA Part 笔记样例一致；非 Markdown `**H**ike` 简写

## 2026-09-02 (Order 1 执行，规则改为不加 e.g)
- 用户确认全局惯例「例句不加 e.g」：已同步更新本自动化 prompt 第 4 条（完整句才斜体、短语普通文本、修正时去除已有 e.g）。
- 处理 `生词/Instagram.md`（用户已补全 contingent 释义）：
  - Upfront：移除 `e.g -` 标记，例句 `*There will be an upfront fee of 4%.*` 斜体保留。
  - **Contingent**：词头加粗+首字母加大、冒号后补空格；短语例 `arms sales contingent on the approval of congress` 保持普通文本。
  - **Go after**：同上格式化；例句 `*We're both going after the same job.*` 斜体。
  - **Watershed**：词头加粗+首字母加大，搭配 `watershed (in something)` 加粗；例句斜体。
- 重写时顺带清理网页粘贴产生的不可见字符（NBSP/零宽空格），释义措辞未改动。
- 结论：4 个条目全部符合 Order 1 规范。

## 2026-09-03 (Order 1 定时执行)
- 巡检范围：生词/ 目录（CNN原文/ 未触碰）。
- 文件：`生词/Instagram.md`，修改 1 处：
  - Contingent 短语例 `*Arms sales contingent on the approval of congress*`：非完整句（无谓语动词），按规则 4 去除斜体 → 普通文本（缩进保留）。
- 其余 3 条目（Upfront / Go after / Watershed）复查通过：词头首字母加大+整词加粗、例句完整句斜体、搭配 `watershed (in something)` 加粗、无 e.g 标记、语块间空行分隔。
- 不完整条目：无（4 条目释义均完整）。
- 结论：1 处修正后全部符合 Order 1 规范。

## 2026-09-03 (Order 1 手动执行 + 规则变更)
- 规则 4 变更（用户确认）：释义下一行例句——含不成完整句子的短语/词组——统一做斜体处理（覆盖原"仅完整句斜体"）。已同步更新自动化 prompt。
- `生词/Instagram.md`：
  - 新增条目 Implement 格式化：词头首字母加大+整词加粗；两条例句（短语例 + 完整句）去列表符号转 8 空格缩进斜体。
  - Contingent 短语例 `Arms sales contingent on the approval of congress` 由普通文本改回斜体（按新规则）。
  - 清理粘贴 NBSP；其余 Upfront / Go after / Watershed 复核合规。
- `生词/Tibet Mudslide.md`（新文件）：
  - Aerial / barrage / Nepalese / all-out 词头统一首字母加大+整词加粗（barrage、all-out 首字母大写），全角冒号"："→": "，清除零宽空格/NBSP/多余空格。
  - barrage、all-out 的释义行下例句（含不完整短语例 `a barrage of questions/criticisms/complaints`）统一斜体、去列表符号转 8 空格缩进。
  - 搭配 `barrage (of something)`、`barrage of questions/...` 加粗保留；`<font color="#de7802">` 粘贴色标保留未动。
- 不完整条目：无。
- 结论：2 个文件全部符合 Order 1（新规则 4）。

## 2026-09-19 14:05 (自动化触发)
- 注：合规文件清单与逐次执行日志统一维护在 `.workbuddy/memory/automations/1d1c75a5-5ab5-4ce9-8ce2-85afb74db423/memory.md`（本文件自 09-03 起不再追加明细）。
- 本次结果：`生词/` 4 个文件全部在合规清单内，按跳过规则零检查、零修改；无新增/被改动文件；`CNN原文/` 未触碰。报告"全部合规，无需修改"。
