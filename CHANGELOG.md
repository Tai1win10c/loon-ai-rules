# 变更记录

## 2026-11-10 — 缩小 Bing 分流范围

- 从主表移除 `DOMAIN,www.bing.com`，避免普通 Bing 搜索命中该条。保留其他 Copilot 条目。
- `AI-Suite.list` 更新至 `2026-11-10-bing-1`，共 617 条。独立可选的 `Anthropic-Shared.list` 共 12 条。
- 重新获取 OpenAI 官方语音 JSON，402 条地址与仓库快照一致。

## 2026-11-03 — ChatGPT Voice 官方地址同步

- AI-Suite.list 更新至 2026-11-03-voice-1，共 618 条。官方语音 IPv4 /32 从 23 条增至 402 条，新增 379 条，移除 0 条。
- 2026-11-03 成功读取 [OpenAI 官方 JSON](https://openai.com/chatgpt-voice.json)，上游时间为 2026-10-27 UTC。仅同步公开目的地址，UDP 转发需另行验证。
- Anthropic-Shared.list 仍为独立可选订阅，共 12 条。

## 2026-11-02 — Anthropic 共享依赖补充

- 新增独立可选 Anthropic-Shared.list，版本 2026-11-02-anthropic-shared-1，12 条精确 DOMAIN 规则。
- 补充官方列出的 Artifacts JS CDN、可选遥测、插件/安装/发行说明/更新主机。来源与用途见 SOURCES.md。
- AI-Suite.list 内容与版本不变，仍为 239 条；两个文件无重复规则。需要补充同出口覆盖时另加订阅并绑定相同策略。
- 说明共享主机会影响其他应用，官方可访问要求不等于全部必须同出口；并未承诺任意插件/MCP/云端请求全链路固定。
- 每周任务同步维护新文件，但本次不扩充其他 AI 的共享依赖。
- 未写入固定出口地址、节点、账号、密码或订阅凭据；只操作 loon-ai-rules。
- 发布后回读校验新文件、去重与主文件不变，并验证原始下载地址。

## 2026-11-02 — non-cn-1

- 版本：2026-11-02-non-cn-1。以已发布的 241 条为基线，移除 6 条、补充 4 条，现为 239 条。
- 移除 TRAE：trae.ai、traeapi.us、trae-api-sg.mchost.guru、trae-api-us.mchost.guru。
- 按项目来源口径移除 Dify：dify.ai、udify.app。Dify 有美国运营主体；此移除不表示其注册地为中国，来源歧义见 SOURCES.md。
- 新增 claude.app（Claude 官方桌面网络文档）、augment.dev、copilotprodattachments.blob.core.windows.net、copilot-stg.com（最新社区清单）。后面三项是补齐当前遗漏，不宣称为最近新上线接口。
- 核查 viewer12 社区聚合最新文件、其最近提交、Claude/Cursor/Copilot 官方网络文档，并搜索 Reddit 线索；未给所有服务逐项实测。
- Google 的 business.gemini.google、Windsurf 的 windsurf-telemetry.codeium.com、api.githubcopilot.com 等已有后缀覆盖，未重复添加。
- 官方 chatgpt-voice.json 仍因内容类型未能读取，保留旧快照并标明待复核。
- 每周维护任务加入排除中国来源 AI 的范围限制；共享服务不会仅因同时被中国服务使用就整体移除。
- 仅修改 loon-ai-rules，原始订阅地址不变。

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
