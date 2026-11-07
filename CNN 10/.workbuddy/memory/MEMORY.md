# CNN 10 库 - 长期项目记忆

## Order 1 格式约定(2026-09-05 更新)
- 词条统一 `**<span style="font-size: larger; font-weight: bold;">X</span>xx**: 释义`(首字母加大+整词加粗;冒号后单空格)。
- 搭配短语整条加粗;例句一律 `*…*` 斜体、无 e.g 前缀;语块间空行;语法标签(如 [only before noun])与音标原样保留。
- **跳过规则**:经复查确认合规的文件不再重复检查,仅检查清单外的新增/未验证文件。
  - 已合规清单见 `.workbuddy/memory/automations/1d1c75a5-5ab5-4ce9-8ce2-85afb74db423/memory.md` 顶部。
  - 新文件格式化完成后,更新该清单。
- 生词文件可能含 NBSP(U+00A0),Edit 直接匹配易失败,用 Python 按行精确替换。
- 释义语法/拼写一律不动;CNN原文/ 目录永不处理。
