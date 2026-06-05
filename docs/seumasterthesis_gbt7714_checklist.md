# `seumasterthesis` 与 `GB/T 7714-2015` 不一致项清单

## 检查范围

- 检查对象：`template/seumasterthesis.bst`
- 参照对象：`template/gbt7714-2015.bst`
- 当前启用配置：`main.tex`
- 当前实际输出样例：`main.bbl`

说明：本清单按仓库内置的 `template/gbt7714-2015.bst` 作为“国标实现参照”进行比对，并结合当前编译产物 `main.bbl` 取证；未逐条人工转录 `docs/附件3-GBT 7714-2015参考文献著录规则.pdf` 原文。

## 总体结论

`template/seumasterthesis.bst` 不是严格按 `GB/T 7714-2015` 实现的样式文件，当前仓库默认配置也没有启用国标样式。因此，当前参考文献部分不能认定为“与国标一致”。

## 已确认不一致项

### 1. 默认配置未启用国标样式

- 结论：不符合
- 证据：
  - `main.tex:11-16` 中，国标样式 `template/gbt7714-2015` 被注释掉，实际启用的是 `template/seumasterthesis`
  - `README.md:35-40` 明确写到模板同时提供“国标样式”和“东南大学特定样式”两套口径
- 说明：
  - 这一项不是条目细节问题，而是总开关问题
  - 只要当前仍使用 `template/seumasterthesis`，整体上就不能称为“严格国标输出”

### 2. 英文作者姓名未按国标口径转为大写

- 结论：不符合
- 证据：
  - `template/gbt7714-2015.bst:17,36` 设定了 `uppercase.name`
  - `template/gbt7714-2015.bst:471-476` 在英文姓名格式化时执行了大写转换
  - `template/seumasterthesis.bst:251-271` 的英文姓名格式化逻辑未做对应的大写转换
  - `main.bbl:52-57` 当前输出为 `He K, Zhang X, Ren S, et al.`
  - `main.bbl:47-50` 当前输出为 `Blum A, Ligett K, Roth A.`
- 说明：
  - 按仓库内置国标实现，英文作者应输出为全大写姓氏口径，如 `HE K, ZHANG X, REN S, et al.`
  - 当前 `seumasterthesis` 的输出显然更接近学校示例或常见英文排版习惯，而不是仓库内置国标实现

### 3. 学位论文被细分为“硕士学位论文/博士学位论文”

- 结论：不符合
- 证据：
  - `template/gbt7714-2015.bst:1530-1545` 中，`mastersthesis` 与 `phdthesis` 统一按 `D` 处理，`phdthesis` 直接复用 `mastersthesis`
  - `template/seumasterthesis.bst:1185-1228` 为硕士论文单独输出 `[D]: [master's thesis]` / `[D]: [硕士学位论文]`
  - `template/seumasterthesis.bst:1354-1397` 为博士论文单独输出 `[D]: [PhD thesis]` / `[D]: [博士学位论文]`
  - `main.bbl:79-96` 已实际出现带 `[硕士学位论文]`、`[博士学位论文]` 的输出
  - `README.md:35-40` 也明确承认这一点与国标口径不同
- 说明：
  - 按仓库内置国标实现，学位论文的核心文献类型标识是统一的 `[D]`
  - `seumasterthesis` 则把学位层次写进了条目文本，属于有意向校内示例靠拢，而不是严格遵循国标实现

### 4. 电子文献缺少访问日期 `urldate` 支持与输出

- 结论：不符合
- 证据：
  - `template/seumasterthesis.bst:23-60` 的 `ENTRY` 字段中包含 `url`，但不包含 `urldate`
  - `template/seumasterthesis.bst:1058-1082` 的 `electronic.misc` 仅输出标题、URL 或 arXiv 信息、年份
  - `template/gbt7714-2015.bst:76-77` 的 `ENTRY` 字段明确包含 `url` 与 `urldate`
  - `template/gbt7714-2015.bst:1085-1089` 定义了 `format.urldate`
  - `template/gbt7714-2015.bst:1345-1458` 在多类电子文献输出路径中调用了 `format.urldate`
  - `main.bbl:16-26`、`main.bbl:28-34`、`main.bbl:36-39` 的在线文献当前只看到 URL 和年份，没有访问日期
- 说明：
  - 对 `EB/OL` 这类在线文献，当前 `seumasterthesis` 实现没有给访问日期留接口
  - 即使 `.bib` 数据里愿意补访问日期，现有 `seumasterthesis.bst` 也无法按国标实现口径输出

## 本次未列为“已确认不一致”的争议项

### 会议论文连接方式

- 现象：
  - `template/seumasterthesis.bst:780-806`、`template/seumasterthesis.bst:1156-1180` 使用了 `In:`
  - `main.bbl:52-66` 会议论文样例也表现为 `In: ...`
  - `README.md:59-60` 起已经明确指出，会议论文在“国标、学校写作指南、优秀范文”之间本身就存在冲突
- 本次处理口径：
  - 由于仓库内置的 `template/gbt7714-2015.bst` 也存在 `In:` 的实现路径，本次不把这一项直接定性为“已确认不合规”
  - 如果需要，我可以下一轮只针对会议论文条目，按 `docs/附件3-GBT 7714-2015参考文献著录规则.pdf` 再做一次更严格的人工比对

## 建议

- 如果目标是“尽量按国标输出”，优先把 `main.tex` 中的样式切换为 `template/gbt7714-2015`
- 切换样式后，建议同步核对 `.bib` 数据字段，尤其是电子文献的 `url`、`urldate`、学位论文条目字段
- 切换后应重新编译，再对生成的 `main.bbl` 或 PDF 做第二轮抽检
