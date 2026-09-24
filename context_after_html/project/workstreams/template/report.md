# 排版与 MathType 技术验证报告

## 已完成

- `format_spec.md` / `format_spec.json`：从旧 A 表原件确认页面、样式继承、第四/第五节单格表、段落、公式、图注及嵌图尺寸。深层属性与全包 SHA 见 `source_audit.json`；权威原件 SHA-256 在制作前后均为 `ddeff002de83f46497c4b40ebafc76b3ddf892d066c91b872eee20ce85ee762c`。
- `route_reference.md`：直接查看学长论文 PDF 物理第 34 页、印刷页 14 的图 1-5；保留原图页截图 `senior_route_page34.png`，记录方法列、阶段框、箭头及南京图的版式迁移建议。未决定南京的最终研究内容。
- `formula_format_probe.docx`：源 DOCX 工作副本缩到第四/第五节的单页排版小样；保留一条旧式 OLE 公式作结构对照，并新建一条 Word OMML 公式作非 MathType 对照。最终文件 SHA-256 `0067c504894479ee3da516f10307791b0655d15535c9d9a383ed8aea6b549677`。XML 检查 `m:oMath=1`、`o:OLEObject=1`，后者 ProgID `Equation.3`。bundled LibreOffice + 任务内字体映射渲染为 1 页；已实看 `probe_render_v2/page-1.png`，中文、标题、边框、两式和图注无截断/重叠。第一次渲染的 OMML 式接近边框，已补留白后重渲染确认。

## MathType 能力状态

**当前未能生成并证明一条全新、可由 MathType 再次编辑的嵌入公式。** 已查 `/Applications`、用户 Applications、Spotlight 的 `MathType.app`，以及 Word Startup/Add-in 本地路径，未发现本机 MathType 7 桌面程序或相应本地启动项；Microsoft Word 本体存在。未改动 Word、安装应用、全局配置或远程机器。旧件第四节 77 个 OLE 对象的 ProgID 全是 `Equation.3`，只能证明存在旧式方程对象，不能证明 MathType 是其创建者。小样中旧对象能被 LibreOffice 渲染，也不能证明 Word/MathType 可重新编辑；新 OMML 在结构上属于 Word 公式，不是 MathType；公式图片同样不能满足要求。现在也未在 Word UI 实际做双击修改/保存回读测试。

具体可继续路径：在具备 MathType 7 桌面版及 Word 集成的授权环境，使用 **MathType 7 选项卡“Insert Display Equation”** 新建一条测试式，保存 DOCX；重新打开并从 MathType 编辑该式（如把一个系数改值），保存后核对嵌入对象、关系目标及可见结果，再做正式公式。若使用当前 Microsoft 365 MathType Add-in，须先核验它生成的对象类型是否满足用户“MathType 嵌入”的要求；不能把 Add-in 可编辑性自动等同于旧式 OLE。Wiris 官方说明：[MathType 7 与 Word 插入/对象类型](https://docs.wiris.com/mathtype-7-with-microsoft-office-2016-or-later?kb_language=en_US)、[避免只粘成图片](https://docs.wiris.com/mathtype-equations-are-pasted-as-pictures-from-the-office-clipboard)、[MTEF 与 OLE 区别](https://docs.wiris.com/en_US/mathtype-mtef-v5-mathtype-40-and-later)。最小阻碍是当前机器缺少已验证可用的 MathType 新建通道及回编辑验证；本轮不要求降低公式要求。

## 渲染边界

未映射系统中文字体时，bundled LibreOffice 渲染旧件仅 17 页且大量缺字。任务内 `fonts.conf` 将宋体/黑体等映射到本机可见字体后为 30 页，第四节与第五节分别在渲染页 19–25、26–27；这证明结构与视觉位置，但代用字体影响换行和页数。最终申报书仍需在目标 Word 环境做原字体、分页、公式回编辑和路线图 JPG（申报说明要求不大于 400 KB）的最终验收。
