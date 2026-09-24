# 首轮产物已验收 可进入研究设计与定向补证

三个 gpt-6-sol / xhigh 叶子任务均完成。主 Agent 已读取三份报告、框架证据矩阵、文献试跑卡、格式规范及路线图分析，并核对实际文件与关键页图。研究前置工作可接续；MathType 新建及回编辑能力仍待解决。当前尚未生成申报书定稿，也未创建文献提取 Skill。

## 框架按原文采用 方法名称需要纠正

[框架报告](../workstreams/framework/report.md)和[25条证据矩阵](../workstreams/framework/evidence_matrix.csv)可作为写作依据。基础、竞争、奖励是机制层；责任、效率、综合三方案位于基础配置内部。ZSG-DEA用于效率初配。共同前沿按三种方案分组，使用传统DEA，不能直接转述成按主体类型分组的SBM。另一Agent的三份预算加权公式单列为其新设计。

主Agent本轮目视回核论文物理61、71、72页，此前已查看25页图2.1与相关原文。原文中的部分符号、口径疑点已由leaf列明；未复算其数值结果。南京迁移应重新定义资源、指标、时间和约束，不逐字照抄有歧义的公式。

## 21篇文献已可访问 精读仍是下一阶段

[转换报告](../workstreams/literature/report.md)记录12份CAJ、1份KDH、8份HN，共21份2122页。主Agent重新打开全部PDF，页数与清单一致；重算全部21份原件哈希，与转换清单一致。核对结果见[first_round_file_checks.json](../research/first_round_file_checks.json)。此检查证明文件与页数一致，不证明每页公式或图像完整。

13份有原生文字，8份HN为影像，需要按问题选择页码阅读/OCR。王雪原、陈瑶瑶文件的转换警告仍按原报告保留，引用相关页前必须核图；inventory的error_log为空不代表没有转换警告。

[陈才华试跑证据卡](../workstreams/literature/pilot_evidence.md)作为结构与引用试跑可采用。主Agent查看PDF40、42页，确认显示的CCR形式与1996年1.074数值、该年产出缺失说明；因此其数值结果暂不进入南京研究的校准或证据结论。其余20篇尚未精读，不能由完成转换推断已经读完。

## 版式可实施 MathType尚未满足

[模板报告](../workstreams/template/report.md)、[版式规范](../workstreams/template/format_spec.md)和[路线图参考](../workstreams/template/route_reference.md)可作为制作规范。主Agent复核旧A表哈希、77个Equation.3对象及小样中1个旧OLE和1个新OMML，并查看最终一页渲染图。见[first_round_template_check.json](../research/first_round_template_check.json)。

旧对象复制与OMML小样没有满足全新MathType嵌入要求。当前缺少已验证的新建通道，也未完成MathType打开、修改、保存再回读。保留用户要求，不将图片或OMML替代品标为达标。渲染使用任务内字体映射，只验结构和可读性，最终须核查目标字体与分页。

旧表实际纸张是Letter；[正式通知核对](../research/official_notice_check.md)要求A4打印。后续保留用户指定的字体字号、标题与表格风格，按A4形成打印版并重新验收，避免照搬Letter造成缩放和分页偏差。

## 下一轮按缺口安排

1. 主Agent依据已读的本工作区Skill写作标准，把section-5提取模板和真实试跑固化为文献证据提取Skill；保留原生文字/影像分流、页码、公式原页与来源/推断分离标准。
2. 优先定向读取王雪原的科技计划配置、冯兆奎的效率与组态，以及一篇协同网络文献；外部科技资源ZSG原文按核心模型需要补读。按问题精读，不全量加载2122页。
3. 主Agent确定第四第五节研究设计及大纲：地区汇总、机构/项目网络、同质资源池、三初始方案、竞争条件与评价激励如何闭合。拟取得数据与已有数据分开。
4. MathType作为独立制作缺口继续验证；正文和模型设计不依赖该制作步骤，可以先推进。

## 调度检查

启动时与收口时任务树均只有三个叶子任务，未发现嵌套；未收到横向调度证据。主Agent采用的是以上明确回读的落盘材料，未以完成消息替代验收。原始参考文件保持原位只读。
