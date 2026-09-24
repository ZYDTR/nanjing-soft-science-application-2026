# MathType制作路径第二轮检查

2026-09-23。本轮未改动原申报书、Word、MathType或远程系统。

首轮已确认本机Word存在，未找到MathType桌面程序；小样中的新OMML不是MathType。第二轮读取并使用 windows-codex-remote-connect Skill，运行一次既有持久通道只读探针。

探针结果：退出码3；`SSH transport failed (255): channel 0: open failed: connect failed: Connection refused; stdio forwarding failed`。此结果表示当前连接目标端口拒绝连接，未成功得到Windows协议响应。无法取得Windows身份、任务状态或agent哈希；无法判断目标关机、隧道未建立或其他原因，不宣称Windows上有/没有MathType。

没有继续排队执行命令，也没有为排版任务扩大到远程通道重建。新MathType嵌入与“修改—保存—重开”验收仍未完成。该缺口影响最终DOCX制作，不阻碍本轮研究设计、文献补证及路线图内容确认。

后续成功条件仍是：在实际可用MathType环境新建一式，嵌入DOCX；通过MathType修改系数或变量、保存、重开并核对可见内容与嵌入对象。旧OLE复制、文件内写入对象标签和公式图片均不能替代此证明。
