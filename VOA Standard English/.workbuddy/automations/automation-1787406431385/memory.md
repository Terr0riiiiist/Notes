# Automation: Order 1 - VOA生词笔记格式统一

## 执行摘要 (2026-08-24)

对 VOA 生词笔记做格式规范化。本次处理的文件（库根目录无 Part*.md，仅子文件夹有效）：
- VOA标准英语听力生词/Part1.法律与政治.md
- VOA标准英语听力生词/Part2.科技进步.md
- VOA标准英语听力生词/Part3.财经透视.md

### 本次改动
1. **e.g 标记统一**：所有 `e.g - ` / `e.g:` / `E.g - ` 等不规范写法规范化
   为 `e.g *句子*`（小写、单空格、示例句斜体）。共修正 16 处。
2. **补 e.g 到缺失的示例句**：3 处斜体完整句此前缺 e.g 标记，已补上
   （Part2 Sprinkle A/B 例句、Prompt 例句）。
3. **词头冒号后多余空格**：8 个词条词头 `**:` 后原为两个空格（含 Part2 Provost
   的非断行空格 \xa0），统一改为一个空格
   （Appeal, Last ditch, Remorse, Attorney, Amid, Antagonize, Provost, Blast）。
4. 清理文末多余空行、压缩连续空行为单行（不改变词条间已有空行分隔）。

### 已确认符合规范（无需改）
- 单词/短语：首字母加大 + 整词加粗、短语整词加粗均正确。
- 词条之间已有空行分隔；attorney / attorney general 作为关联词紧挨排列正确。
- 短语型示例（如 to convene a meeting、a 60% turnout of voters、to make
  forward/backward projections...）保持普通文本、无 e.g/斜体，符合要求。
- 标题 `#### Material N` 未加粗；释义内容语法/拼写未改动。

### 校验
脚本后检查：剩余不规范 e.g = 0，剩余词头双空格 = 0，规则检查 ISSUES = none。

## 执行摘要 (2026-08-26)

再次核对 3 个 Part*.md（注意 Part1 在 2026-08-24 上次运行后被改动过，本次重点重审）。

### 本次改动（均为"空格"格式归一，未改释义内容）
1. **粗体子形式/短语后多余空格**：`**stiffen something**  to`、`**recipe for something**  a`、
   `**hike in something**  the`、`**cutback (in something)**  reduction`、`**downturn (in something)**  a`、
   `**drive somebody/something ↔ off**  to`、`**prolong something**  to`、`**prompt somebody to do something**   e.g`、
   `**sprinkle A on/onto/over B**  e.g` 等 → 统一改为单空格。
2. **独立 e.g 前多余空格**：Part2 Shuttle `*2*. …between two places  e.g *I’m flying…*` → 单空格。
3. **语法标记后多余空格**：`(of the police)  to` → `(of the police) to`；
   `[intransitive, transitive]  to` → `[intransitive, transitive] to`。
4. **音标冒号后多余空格**：`/ˈmɑːtə(r)/ :  a` → `/ˈmɑːtə(r)/ : a`（单空格）。
5. **中文释义前多余空格**：`government  劫持，盗用`、`grow  堆肥`、`bread  面包皮`、
   `[[#^ideology]]  实用主义` → 均改为单空格。
6. **SYN. 标记前多余空格**统一归为单空格。
7. **Part2 Shuttle 编号格式**：`*1*.a` → `*1*. a`（与 `*2*. a` 一致）。

### 刻意保留（非规范问题，不动）
- 各行缩进、Part1 末尾两 bullet 同行分隔的 `    - `（合并会破坏列表结构）。
- 释义拼写/语法原样（含既有 "Detaniee"）、所有粗体+首字母放大词头、
  全部 e.g 斜体完整句、语块空行分隔、attorney/attorney general 紧挨排列。

### 校验
全部词头粗体+首字母放大完好；内部多余多空格仅剩 Part1 L114 的 bullet 分隔符（刻意保留）；
无破坏 HTML span / 粗体结构；e.g 全部为完整斜体句。

## 执行摘要 (2026-08-26 晚间) — Part3 专项

- 触发：用户单独要求对 Part3 执行 Order 1。此时 Part3 已被替换为更大的新版本（54 行，含 Material 1/3/5），与上午处理过的 24 行版本不同，且例句 `e.g` 标记已丢失。
- 修复：
  1. **缺失 e.g 标记（10 处）**：原文例句仅有斜体、缺 `e.g`。已补 `e.g *完整句*`；`**spark something** *句*`、`**spark something off** *句*` 改为 `**form** e.g *句*`；bullet 下 ` - A recent poll suggests…` 改为 ` - e.g *…*`。
  2. **poll 词头缺格式**：原为 `poll: the …`，改为 `**<span style="font-size: larger; font-weight: bold;">P</span>oll**: the …`（首字母放大+整词加粗；`poll` 是主词条，非子形式）。
  3. **多余多空格归一**：L37 `owes   国债`→单空格；L50 `damaged    SYN.`→单空格；L52 `opinion   SYN.`→单空格。
- 校验：17 个主词头全部 span+加粗；完整例句均带 e.g 斜体（10 处）；无内部多余多空格；标题未加粗；子形式（`**a tax/price hike**`、`**fiscal cliff** …`）保持无 span；释义拼写未改。
- 踩坑：多空格归一正则 ` {2,}(e\.g )` 误将 e.g 行行首 8 空格缩进压成 1 空格，已补回 8 空格缩进（L41/L43/` - ` bullet 因只含单空格未被误伤）。

## 执行摘要 (2026-08-26 晚间复跑) — Part3 再次执行 Order 1
- 触发：用户再次要求"对 Part3 执行 Order 1"。此时 Part3（20:30 版本）含 10 处 `e.g` 标记，与最新规范（例句斜体、不加 e.g）不符；Part1/Part2 均已无 e.g。
- 修复：去除 10 处 `e.g` 标记（斜体、缩进、bullet 保留）：Cutback / Drive off / Soften / Projection / Sovereign debt / Spark（3 处：`**spark something** *句*`、`*Winds...*`、`**spark something off** *句*`）/ Bring somebody↔down / Poll（` - *A recent poll...*`）。
- 校验：17 词头 span+加粗完好；标题 3 个未加粗；e.g=0；内部双空格=0；子形式无 span。
- 结论：三个 Part 笔记现已全部符合 Order 1 最新规范。

## 规则澄清 (2026-08-26)
- 用户确认：`SYN.` 同义词是否加粗（如 Part1 的 `SYN.**<font color="#6425d0">place</font>**` vs Part3 的 `SYN.<font color="#6425d0">brave</font>`）**不属于 Order 1 规范**，保持各自现状，巡检/格式化时不要改动 SYN. 部分的加粗样式。
