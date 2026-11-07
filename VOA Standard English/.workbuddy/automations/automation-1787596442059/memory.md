# Automation Memory: Order 1 - VOA生词笔记格式统一

## 2026-08-31 (首次执行)
- 巡检范围：库根目录无 Part*.md（仅 `未命名.base`，已排除）；实际生词笔记为 `VOA标准英语听力生词\` 子文件夹 3 个文件：`Part1.法律与政治.md`、`Part2.科技进步.md`、`Part3.财经透视.md`。
- 依据本自动化 prompt 的 Order 1 规则逐条核对：标题 `#### Material N.`、词条首字母加大+整词加粗、搭配短语加粗、短语例保持普通文本、语块间空行分隔等均符合；唯一不符合项为**规则 4**——全部完整句例句仅斜体、缺 `e.g -` 标记。
- 共修正 24 处（仅加 `e.g -` 标记，例句斜体保留，未改动释义）：
  - Part1（5 处）：At no point（2 处）、Amid、In full swing、Bloc
  - Part2（9 处）：Crust、Sprinkle（2 处）、Mold、Encroach、Prompt、Depression、Shuttle、Tribute
  - Part3（10 处）：Cutback、Drive off、Soften、Projection、Sovereign debt、Spark（3 处）、Bring somebody↔down、Poll
- 短语/词组例（`the latest hike in interest rates`、`to make forward/backward projections of population figures`、`to convene a meeting`、`a high/low/poor turnout`、`biodiesel` 等）保持普通文本，未加 e.g/斜体，符合规则 4。
- 注意：旧自动化（automation-1787406431385）的 memory 记录过 2026-08-26「去除 e.g」修订；本次按**本自动化** prompt 规则 4 恢复 `e.g -` 标记。若用户偏好「无 e.g」惯例，请调整本自动化 prompt 第 4 条。
- 结论：3 个文件已全部符合当前 Order 1 规则。

## 2026-09-02 (用户确认：例句不加 e.g)
- 用户明确指示「不要 e.g，例句加斜体不加 eg」，确认采用「无 e.g」惯例。
- 已移除 08-31 补上的全部 24 处 `e.g -` 标记（Part1 5 / Part2 9 / Part3 10），例句斜体保留；三个文件均无 e.g 残留，恢复为纯斜体例句。
- 已同步更新**本自动化 prompt 第 4 条**：例句前一律不加 e.g；完整句才斜体；短语不加斜体保持普通文本；逐项修正时需同时去除已有 e.g 标记。
- 注意：本次 automation_update 返回 status = PAUSED（未改动状态字段，属原有状态）。若需每日 9:00 自动巡检，请确认是否恢复 ACTIVE。
- 结论：三个文件全部符合修订后的「无 e.g」规范。

## 2026-09-02 (晚间续跑)
- 巡检：三个 Part 文件 `e.g` 零残留；Order 1 格式（首字母加大加粗 span、词条/搭配加粗、完整句纯斜体）保持完好，无需改动。
- 附带排查：VOA 斜体绿色差异根因 = Blue Topaz 主题 `--accent-em`（theme.css L13651-13660 给 em 上色），CNN 10 为默认主题故无此色；已给出复刻方案（装主题或 CSS snippet），未改动 CNN 库外观配置。
- 自动化状态 ACTIVE，每日 9:00 巡检正常运行。
