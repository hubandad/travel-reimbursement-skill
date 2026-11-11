# 差旅报销整理技能

把一个月或一次出差的票据，整理成公司 Excel 模板要求的报销单。

分享地址：https://github.com/hubandad/travel-reimbursement-skill

包含逐票核对、长票号文本保存、重复票据识别、退改签费用区分、申请人及费用承担人填写、差旅补助、公式合计与模板格式核验。此仓库只含通用指引及虚构验收案例，不含任何人的真实票据或公司内部模板。

## 补助规则

本技能记录了创建者明确提供的公司制度：**部门经理及以上150元/人/天，其余人员100元/人/天**。岗位级别不明时先询问，不默认100元。其他公司或更新制度，以使用者提供的现行规则为准。

## 同事怎样使用

### 在 Codex 中安装

将本仓库链接发给 Codex，并说：

> 请使用 skill-installer 从 https://github.com/hubandad/travel-reimbursement-skill 安装 `skills/travel-reimbursement` 技能。安装后，使用 `travel-reimbursement` 按我提供的票据与公司模板整理报销。

也可以将 `skills/travel-reimbursement` 整个目录放进你使用的客户端支持的本地技能目录。若客户端没有立即识别，重启或新建会话后再调用 `$travel-reimbursement`。

### 在支持文件处理与浏览的 ChatGPT 中使用

把本仓库链接和下面这段话一起发给 ChatGPT，并上传**自己的报销模板和票据**：

> 请打开 https://github.com/hubandad/travel-reimbursement-skill ，先阅读 README 和 `skills/travel-reimbursement/SKILL.md`，再读取其中任务所需的参考文件。按照这些流程整理我上传的报销票据。我的姓名、部门、岗位级别和本次公司制度如下；如果缺少决定补助或费用分类的信息，请先问清，再完成计算。保留模板原有格式、公式、下拉和打印设置，给我可下载的报销单。

**发一个链接不等于模型永久学会了技能。** 有浏览与文件处理能力的会话可将仓库内容作为当次任务参考；后续是否自动调用，取决于客户端是否安装并支持技能。读不到 GitHub 时，可下载仓库 ZIP，上传其中的技能文件及参考文件。没有表格写入能力的环境只能提供核对建议，不能声称生成了 Excel 文件。

本仓库还包含标准 `plugin.json`，供支持 Agent Plugins 的客户端识别技能目录；它不是已经上架的 ChatGPT 插件。插件安装或工作区分发仍需按所用客户端支持的方式操作。

### 每次报销需提供

- 票据目录，或上传的 PDF / 图片文件。
- 本次公司报销模板；不要用其他同事的历史明细充当本次费用。
- 姓名、部门、业务线及费用承担对象（已有可靠资料可复用）。
- 岗位级别或明确适用的补助日标准。
- 出差事项、日期与公司特殊规则；有会议专项要求时提供实际会议名称及通知。

桌面端只能读取已授权的目录；网页聊天无法仅凭电脑路径读取本地或 iCloud 文件。

## 交付结果

一份按模板填写的报销单，以及票据金额、补助天数及标准、总额和实际待补项。生成文件不等于提交报销审批或付款。

技能会保留原票据和模板。遇到同名文件或你已经手动修改的版本，会使用不冲突的新文件名，避免覆盖修改。

## 文件说明

- [`SKILL.md`](skills/travel-reimbursement/SKILL.md)：完整流程与补助规则。
- [`模板与 Excel 处理经验`](skills/travel-reimbursement/references/template-and-excel.md)：字段映射、长票号、公式与格式保留。
- [`虚构验收案例`](skills/travel-reimbursement/references/acceptance-cases.md)：经理/普通员工、重复票据、退票、未知级别等测试情境。

本技能不内置公司模板。模板可能包含隐藏人员表、内部地址及联系方式，使用时由各人自行提供，勿提交到此仓库。

技能与插件格式参考 [OpenAI 技能文档](https://learn.chatgpt.com/docs/build-skills) 和 [插件打包文档](https://developers.openai.com/plugins/build/plugins)。GitHub 发布与插件目录上架是不同操作。
