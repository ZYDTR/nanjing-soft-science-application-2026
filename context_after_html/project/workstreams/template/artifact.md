# 旧 A 表第四、第五部分模板契约（技术小样范围）

- 权威原件：`@repo/2023RR软科学_A.docx`；SHA-256 `ddeff002de83f46497c4b40ebafc76b3ddf892d066c91b872eee20ce85ee762c`。
- 原件单节，Letter 8.5×11 英寸；宋体/黑体等原名见 `source_audit.json`。本地 bundled LibreOffice 用任务目录 `fonts.conf` 映射缺失字库后渲染为 30 页；未映射的 17 页严重失字，不可用作分页证据。覆盖页型：封面；各节标题+单格边框表；表格跨页续页；第五节技术路线独立图页；末尾空页。此次小样只提取第四、第五节，不作为最终申请书。
- 结构定位：`word/document.xml` 的 `w:body` 直接子节点 31/32 是第四节标题/表格；34/35 是第五节标题/表格；表格各 1 行 1 单元格，单元格包在 `w:tr/w:sdt/w:sdtContent/w:tc`。稳定标题可由 `w:pStyle=1` + 相邻表格识别。第四节表格内容约 3482 可见字符，第五节约 751 可见字符，公式与图不计入。
- 页面：左右 1800 twips（1.25 英寸），上下 1440 twips（1 英寸），页眉页脚距 720 twips；无实际页眉、页脚内容，无首页例外。正文可用宽 8640 twips；原表网格/单元格宽 8856 twips，需保留源表坐标并在目标软件检查溢出。
- 一级标题：`Heading 1`（styleId `1`），基于 Normal；东亚黑体，15 pt，黑色继承，`keepNext`、`keepLines`；尾随“（文档标题）”为白色直排字，模板残留，不属于正文。标题与表格之间不另有空行。
- 内容表：Normal Table，黑色 0.5 pt 单线外框及内框，宽 8856 twips，无显式底纹；实际只有一单元格。表内为普通段落，默认中文宋体、拉丁 Times New Roman。主要段落直接 12 pt、1.5 倍行距、首行两汉字（480 twips）；不设置段前后间距。小节标题 12 pt 加粗；公式段另用 `ae`/`af` 样式。图注为 12 pt 居中、1.15 倍行距。
- 既有公式：旧件带 77 个 `word/embeddings/oleObject*.bin`，多数与第四节内嵌对象关联；`Equation.3`/OLE 不能证明由 MathType 创建。技术路线是 `word/media/image76.png`，`rId160`，Word inline 图尺寸 5486400×3403600 EMU（6×3.72 英寸），后接居中“图2 技术路线图”。
- 小样可编辑槽：第四节标题与单元格示例正文；第五节标题与单元格示例正文；旧 OLE 只保留一条作为结构对照；新公式仅用 OMML 标明非 MathType。源文件不改；小样删去其他节属于用户要求的最小技术验证范围。原件全部 package part 路径、大小、SHA-256 见 `source_audit.json`；后续正式文件不得把本小样作为原件替代。
- 验证门槛：源 SHA 不变；样例 DOCX 可打开；OMML 结构和旧 OLE 结构可区分；bundled LibreOffice 渲染成 PNG 后逐页检查中文、标题、边框、公式、图注，不以 LibreOffice 显示证明 MathType 可编辑。
