# 变更记录

## 2026-10-27 — 首次发布

- 将用户提供的 AI Suite 基线整理为 AI-Suite.list；按服务分组，不在文件内写死代理策略。
- 根据 OpenAI 官方网络允许列表补入精确规则 frontend-apps-multi-region.workos.com。来源见 SOURCES.md。
- 保留原先已有的共享依赖并注明对非 AI 服务的影响；没有扩大到整个 cloudflare.com、googleapis.com 或 githubusercontent.com。
- lh5.googleusercontent.com 在原始规则中已经存在；上一轮对话将其误列为遗漏，首次发布没有重复添加。
- 新的 Google/GitHub 共享依赖候选暂不加入；等待用途与影响范围核验。
- ChatGPT Voice IP 保留用户现有快照；官方 JSON 本次未成功读取，未宣称更新完成。
- IPPure/icanhazip 检测规则继续由用户本地管理，未混入 AI 服务列表。
- 完成文本语法形态、重复条目检查及发布后回读一致性检查；尚未在用户设备实测 Loon 导入与全服务请求覆盖。
- 创建独立的 ChatGPT 每周检查任务：每周二上午，Asia/Singapore；不是 GitHub Actions。可确证的精确新增直接更新，扩大共享范围的变更先确认。

维护仅限 Tai1win10c/loon-ai-rules；禁止修改账号下其他仓库。
