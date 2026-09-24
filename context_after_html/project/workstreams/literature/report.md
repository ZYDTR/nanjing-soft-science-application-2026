# 导师 21 份 CAJ 家族文件：本地可读性与证据试跑报告

> 导出说明（2026-09-24）：以下为第一轮历史报告。后续已有4篇证据卡；本交接包只附这4篇转换PDF，21份原CAJ均在仓库根。inventory已加随包状态。转换环境、脚本、其余17份PDF和失败缓存不随包，相关文字仅为历史记录。

## 结果与边界

原文件未改动、未上传。按文件头识别 12 份 CAJ、8 份 HN、1 份 KDH；21 份全部已生成并校验本地 PDF，共 2,122 页。每份的 PDF 页数与原格式能提供的页数一致（KDH 原工具不报页数，使用 PDF 页树确认）；抽检封面或前部及中间页均可目视阅读。13 份 CAJ/KDH 有可选文字；8 份 HN 是影像 PDF，无可靠文字层，需要按问题选择页码做本地 OCR 并对照图像。逐份状态、原件 SHA-256、页数、证据路径见 [inventory.csv](inventory.csv) 或 [inventory.json](inventory.json)。

已深读 1 份：《江苏省区域创新资源配置研究》（2007），见 [pilot_evidence.md](pilot_evidence.md)。其余 20 份只完成转换、页数、文字层与抽样渲染验收，**没有完成全文阅读，也没有按题名生成摘要**。下一轮应依 `inputs/context/section-6.md` 的逐篇定向问题读对应章节；HN 文献优先定位目录与页图，再只对所需页 OCR。

## 可复用的本地流程

运行入口：`convert_local.py`（历史脚本，未随包），依赖与复跑命令见 `RUN.md`（历史运行说明，未随包）。脚本按魔数识别原格式，记录 SHA-256；在本目录临时子目录中调用原始 [caj2pdf](https://github.com/caj2pdf/caj2pdf) Python 解析器；CAJ/KDH 的缺损 PDF 交叉引用由本地 mutool 兼容脚本（未随包）用 PyMuPDF 修复；HN 的 JBIG1/JBIG2 影像解码库在本目录从项目源码与 [Artifex jbig2dec 源码](https://github.com/ArtifexSoftware/jbig2dec)编译。没有全局安装或修改系统设置。源码快照：caj2pdf `6c4bc32b15ce748d211f45d536f5d5511ef9f368`；jbig2dec `6e8205ba61a206a0830f4884ebe52be615735f3d`。转换后用 PyMuPDF 逐页检查页树、页数、几何尺寸和可选文字量，再抽样渲染人工看图像。每份完整运行记录在 `logs/NN_convert.log`。

本次按逐页渲染、保留原页码的原则复核，未转为丢失页码的合并正文。试跑用逐页文本文件保留 `PDF page N` 标记，核心公式和表格回读原页图像。

## 真实故障与不可靠区

- 初试 Rust 重写版：两份 CAJ 核心候选因 `Invalid cross-reference table (invalid start value)` 失败，见 `logs/pilot_1_convert.log` 与 `logs/pilot_2_convert.log`；HN 虽报告转换成功，却出现数亿点宽的页面、无正文以及黑页，见 `logs/pilot_0_convert.log`、`qa/wang-002.png`、`qa/zhejiang_rust-002.png`。不能以命令退出码认定可读。失败试验补丁保存在 `logs/rust_hn_attempt.patch`，最终交付使用原始 Python 工具链。
- 原始 Python 工具起初因缺少 `mutool` 失败，见 `logs/jiangsu_py.log`；本地修复脚本后 21 份通过。HN 的王雪原文献在转换日志 `logs/10_convert.log` 有 52 行图像数量/定位提示；PDF 第 47 页含图页已目视检查可读，但其余受提示影响的图表页在逐条引证前仍须回查。浙江文献 `logs/15_convert.log` 有两处“跳过重复图像”提示。
- 8 份 HN 的 `pdftotext` 基本无正文，Rust 的 HN `text-extract` 对王雪原文件只得到控制字符；不能把这个结果当论文文字，更不能用题名补摘要。HN 页图是可靠的当前阅读入口，OCR 必须逐页图像核对。
- 陈才华论文的纯文本公式顺序损坏（PDF 第 39–40 页），表 3-2 的 1996 年 θ>1、表 3-5 标题 12/实际 11、表 3-4 单位标签与数字量级不合，均在原页图像中可见，属于原文/复现风险。详细证据与迁移边界见试跑卡。对其余 20 篇的公式和表格尚未做逐页保真验收。

## 对后续 Skill 的实测验收建议

以四个真实样本作固定回归：陈才华（CAJ，交叉引用修复和原生文字）、何佳（KDH）、王雪原（HN/JBIG1 与混合图页）、陈瑶瑶或曹永森（HN/JBIG2）。验收不得只看退出码：必须比对原格式页数与 PDF 页数，排除异常页面尺寸及黑页，检查两个相隔较远的实际页面，区分原生文字与影像，记录转换警告。证据卡需有原文 PDF 页码及必要时正文页码，公式/表格结论必须看页图；缺失值、单位、样本进入机制和不支持假设的结果不能跳过。此轮没有创建或修改 Skill。
