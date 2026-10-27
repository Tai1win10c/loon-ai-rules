# 变更记录

## 2026-10-27 — community-1

- 版本标记：2026-10-27-community-1。有效规则由 193 增至 241，新增 48 条；原有规则未删除。
- Muse 补入 metaaivm.com、metaaiusercontent.com、meta.com、facebook.com、fbcdn.net、cdninstagram.com；auth.meta.com 由 meta.com 后缀覆盖。
- 同步扩充 ChatGPT Voice、Claude、Google AI/NotebookLM/Antigravity、GitHub Copilot、Perplexity、JetBrains、Microsoft Copilot、Grok、Windsurf 的社区候选域名。
- 用户已明确授权覆盖优先，允许基于 GitHub、Reddit 和开发者用户分享收录候选，不限官方文档；用途未完全确认的条目标注社区候选。
- 共享域名会影响 Facebook、Instagram、Google、Bing、GitHub 等非 AI 请求。本轮按用户授权纳入；来源与置信度见 SOURCES.md。
- 每周任务已修改：检查全部已收录 AI，主动检索 GitHub 源码/规则/提交/Issues/PR、Reddit、开发者分享。
- 原始订阅地址保持不变。客户端更新后可搜索版本标记和 metaaivm.com 验证同步。
- 发布后回读检查规则数量、重复、语法形态和正文一致性；未替用户设备验证实际拉取。

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
