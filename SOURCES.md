# 来源与核验状态

## 首次发布：2026-10-27

AI-Suite.list 以用户提供的现用规则为基线。首次发布没有逐个平台重新核实全部接口；来源链接不等于本次已逐条验证。原文中的地区限制和“已验证”日期未直接沿用为当前结论。

### 本次已读取并核实

- OpenAI 网络允许列表：https://help.openai.com/en/articles/9247338-network-recommendations-for-chatgpt-errors-on-web-and-apps
  - 确认 frontend-apps-multi-region.workos.com，补入精确 DOMAIN 规则。
  - 其余 OpenAI 允许列表多数已被原后缀或精确规则覆盖。
  - 文档确认语音地址持续变化；https://openai.com/chatgpt-voice.json 本次抓取失败，不能宣称现有 IP 已是最新。
- Loon 订阅规则：https://nsloon.app/docs/Rule/sub_rule/
  - 远程规则文件各行使用 Loon 规则语法，策略在订阅端绑定。

### 待逐服务复核的基线来源

下列是维护入口，不表示本次已完整读取或验证全部域名。

| 规则组 | 核查入口 |
| --- | --- |
| Apple Intelligence | https://github.com/SukkaW/Surge/blob/master/Source/non_ip/apple_intelligence.conf （社区来源，须交叉核验） |
| Cursor | https://cursor.com/docs/enterprise/network-configuration ；https://cursor.com/help/troubleshooting/sign-in-domains |
| GitHub Copilot | https://docs.github.com/en/copilot/reference/copilot-allowlist-reference |
| Gemini | https://knowledge.workspace.google.com/admin/generative-ai/gemini-app/gemini-app-firewall-settings |
| Antigravity | https://antigravity.google/docs/enterprise |
| Google DevTools AI | https://developer.chrome.com/docs/devtools/ai-assistance/get-started |
| Google Labs | https://labs.google/fx/faq |
| Google Opal | https://developers.google.com/opal/faq |
| Claude Code | https://code.claude.com/docs/en/network-config |
| Kiro | https://kiro.dev/docs/privacy-and-security/firewalls/ |
| TRAE | https://docs.trae.ai/ide/troubleshoot-general-issues |
| Cohere | https://cohere.com/saas-agreement （地域条款入口，不能替代网络清单） |

其他组目前仅继承用户提供的域名，须查找对应官方来源后逐步补充。旧 Azure/CDN 主机和 ChatGPT Voice 地址需优先复核。Meta/Muse 关联已由官方公告确认；补充域名证据见下文。

## 维护判据

1. 新增必须记录来源、日期、用途和精确/共享属性。
2. 用户于 2026-10-27 授权覆盖优先：可追溯社区规则、开发者源码、GitHub Issues/PR 和 Reddit 用户实测可作为候选收录依据，不要求等待官方确认；须明确证据等级。
3. 官方防火墙允许列表解决“可访问性”；不证明每个主机必须同一个出口。
4. 抓取失败、重定向或暂时无请求，不构成删除依据。
5. 用户已同意 Muse 共享 Meta/Facebook/Instagram 依赖及其他 AI 的合理社区依赖补充；今后同类有据新增可直接提交。可能破坏功能的删除、无明确边界的全球 CDN 整域扩大仍需确认。
6. 不公开账号、代理密码、固定出口地址或原始请求日志。

## 2026-10-27 — community-1 扩充证据

此次直接读取 GitHub 文件内容，按用户“宁可信其有、覆盖优先”的偏好收录候选；收录不等于已证实每个域名都是客户端必需。社区聚合可能互相引用，不能当作独立多源证明。

| 来源 | 文件与读取时 blob SHA | 本轮用途 |
| --- | --- | --- |
| Tartarus2014/Loon-Script | [Muse.lsr](https://github.com/Tartarus2014/Loon-Script/blob/master/Rule/Other/Muse.lsr)，00467353b638053c1e47ab58b1bd2b80c4321a20 | Muse 的 meta.com、facebook.com、fbcdn.net、cdninstagram.com、metaaivm.com 共享覆盖 |
| Tartarus2014/Loon-Script | [AI.lsr](https://github.com/Tartarus2014/Loon-Script/blob/master/Rule/Other/AI.lsr)，d898ba73791eb759c053ef3b1484ef94182d6273 | LiveKit、Perplexity cloudinary、JetBrains grazie.ai、Copilot Bing 主机 |
| v2fly/domain-list-community | [data/meta](https://github.com/v2fly/domain-list-community/blob/master/data/meta)，dcbab601e4d9da424fc61f5a19159f70698ab80e | metaaiusercontent.com、metaaivm.com |
| viewer12/OverseasAI.list | [OverseasAI.list](https://github.com/viewer12/OverseasAI.list/blob/main/rule/Surge/OverseasAI/OverseasAI.list)，04cce5ab5c54fc3979dec8bcb92348b0d5eda956 | 本轮 Claude、Google、Copilot、Grok、Windsurf、LiveKit、Perplexity 候选的主要聚合来源 |
| Meta 官方 SDK | [service.py](https://github.com/facebookincubator/muse-gadget-sdk/blob/main/linux/src/musegadget/service.py)，4afd2a25931148b9e69dc7007ea28f5070015439 | 默认连接主机 hatch.metaaivm.com；证明 Muse Gadget 使用，不代表所有 Muse 客户端均使用 |
| Meta 官方公告 | https://about.fb.com/news/2026/09/introducing-muse-personal-ai-agent/ | 明确链接 muse.ai、security.muse.ai、introducing.muse.ai，产品关联已确认 |

说明：auth.meta.com 已被此次 meta.com 后缀覆盖；未重复添加。GitHub 的 github.githubassets.com、avatars.githubusercontent.com、collector.github.com、api.mcp.github.com 沿用此前官方网络清单比对候选，本轮接受共享覆盖。www.googleapis.com、www.gstatic.com 同样属于共享主机。

### 置信度与影响

- 9/10：muse.ai 官方产品关系与 SDK 中 hatch.metaaivm.com 的存在。
- 8/10：表内社区规则确实收录相关域名，文件已直接读取。
- **6/10（待验证）**：社区候选对当前客户端的具体用途、每项是否必需，以及全功能覆盖程度。本轮按用户授权先收录，未进行全服务运行时实测。
- meta.com、facebook.com、fbcdn.net、cdninstagram.com、Bing、Google 静态资源、Firebase 认证与 GitHub 公共资源会影响非 AI 流量；不是 Muse 独享。
- 未加入缺乏本轮可靠关联证据的 museai.com、ecto1.ai，也未加入整个 livekit.cloud、cloudflare.com 或 googleapis.com。

### Reddit 与其他开发者分享

每周检查全部已收录 AI 服务，必须主动检索 GitHub 规则/源码/提交/Issues/PR、Reddit 及开发者用户分享。Reddit 原帖能作为用户实测证据，但不将未经核实的故障归因写成事实。

本轮搜索到 [Gemini macOS 登录排查](https://www.reddit.com/r/GeminiAI/comments/1xemr7z/anyone_else_locked_out_of_the_gemini_mac_app/) 中提及 robinfrontend-pa.googleapis.com（本轮仅搜索返回的帖文摘录，未读全部评论；该域名原已覆盖），未据此添加新域名。其他 Reddit 检索本轮未带来足够明确的新域名。

## 2026-11-02 — non-cn-1 范围与更新核查

排除中国来源 AI；不按创始人姓名或族裔判断。不收录 TRAE、Dify，也不自动引入 DeepSeek、Qwen、豆包、Kimi、智谱、MiniMax 等。共享 Google、Microsoft、CDN 域名不因被中国服务使用而整体移除。

### 本次移除

- TRAE 项目来源：[ByteDance 官方 trae-agent](https://github.com/bytedance/trae-agent)。移除 trae.ai、traeapi.us 及两个 trae-api-*.mchost.guru 精确主机，不删除整个 mchost.guru。
- Dify 来源存在口径差异：[LangGenius 官方 GitHub 简介](https://github.com/langgenius) 表明项目由前腾讯云 DevOps 团队成员创建；[当前官方服务条款](https://www.dify.ai/legal/terms-of-service) 表示从美国加州运营。本次按用户“来自中国”的项目来源口径移除 dify.ai、udify.app，不据此将其称为中国注册公司。将 Dify 纳入排除范围是本次执行假设，置信度 **6/10（口径待用户校准）**。

### 本次补充

| 规则 | 证据 | 状态 |
| --- | --- | --- |
| DOMAIN-SUFFIX,claude.app | [Claude Desktop 官方网络要求](https://code.claude.com/docs/en/desktop#network-access-requirements) 明列 claude.app 和其子域，包含 livepreview | 9/10；补齐现有遗漏 |
| DOMAIN-SUFFIX,augment.dev | 最新 viewer12/OverseasAI.list | 社区候选，实际依赖用途 6/10 |
| DOMAIN,copilotprodattachments.blob.core.windows.net | 最新 viewer12/OverseasAI.list | 社区候选，实际依赖用途 6/10 |
| DOMAIN-SUFFIX,copilot-stg.com | 最新 viewer12/OverseasAI.list | 社区候选，可能涉及测试环境；实际依赖用途 6/10 |

社区文件：[OverseasAI.list](https://github.com/viewer12/OverseasAI.list/blob/main/rule/Surge/OverseasAI/OverseasAI.list)，读取时 blob SHA 82ce74e39f1c62cdd786f63a20faa4dd21b33e5e；最近提交 [0bf767ab](https://github.com/viewer12/OverseasAI.list/commit/0bf767abf300fe236bbd486dfcc1d9a9f3de431d)。这不证明上述域名都是最近才上线，也不能把聚合仓库视为独立多源核实。

### 检查范围与限制

对照现有所有服务分组与上述社区清单，并读取 [Cursor 网络文档](https://cursor.com/docs/enterprise/network-configuration)、[Copilot 允许列表](https://docs.github.com/en/copilot/reference/copilot-allowlist-reference)、Claude Desktop 官方要求；未逐平台抓取运行时请求。api.githubcopilot.com 已被 githubcopilot.com 覆盖；business.gemini.google 已被 gemini.google 覆盖；windsurf-telemetry.codeium.com 已被 codeium.com 覆盖，故不重复添加。

本轮搜索 GitHub 与 Reddit 新线索，Reddit 未返回足够具体的新域名证据；[LiveKit 防火墙文档](https://docs.livekit.io/deploy/admin/firewall/) 确认媒体主机形态，但不单独证明 ChatGPT 必需，不增加整个 livekit.cloud。OpenAI https://openai.com/chatgpt-voice.json 再次因抓取工具不支持返回内容类型失败，保留现有地址而不宣称已核验最新。

## 2026-11-02 — Anthropic-Shared.list

版本：2026-11-02-anthropic-shared-1，独立可选的 12 条精确 DOMAIN 规则，与主文件一起使用，不复制核心后缀。

来源：[Claude Code 网络配置](https://code.claude.com/docs/en/network-config) 的 Network access requirements / Third-party hosts for artifact fonts and libraries，以及 [Desktop 网络要求](https://code.claude.com/docs/en/desktop#network-access-requirements)。正文已读取，未仅依赖搜索摘要。

| 主机 | 官方列出的使用情境 |
| --- | --- |
| cdnjs.cloudflare.com、cdn.jsdelivr.net、cdn.tailwindcss.com、code.jquery.com、unpkg.com | Artifacts 加载 JS 库；由具体 Artifact 内容决定是否请求 |
| http-intake.logs.us5.datadoghq.com | 可选操作遥测 |
| browser-intake-us5-datadoghq.com | 可选错误报告，受功能启用条件限制 |
| storage.googleapis.com | 插件安装计数/元数据及旧版原生安装更新 |
| registry.npmjs.org | npm 插件、依赖、npx MCP、npm/bun 安装 |
| github.com | 插件/marketplace 克隆 |
| raw.githubusercontent.com | 发行说明/启动时变更记录 |
| formulae.brew.sh | Homebrew 安装的更新版本检查 |

官方文档要求的是按功能可访问，并未要求所有共享主机同出口。对于组织 IP 允许列表，官方明确提到 bridge.claudeusercontent.com 应与 claude.ai、api.anthropic.com 同出口；这些已由主文件覆盖。本次补充的同出口必要性是用户偏好，不能作为官方要求陈述。

未重复添加已在主文件的 fonts.googleapis.com、fonts.gstatic.com。未将整个 githubusercontent.com、googleapis.com、cloudflare.com 加入。googlesource 的动态检出主机、自选插件 URL、外部 MCP/账号认证及云端服务出站不作全量覆盖保证。

证据置信度 9/10（官方文档主机与用途）；**6/10（待实测）**：该用户的具体使用中是否请求每个共享主机、是否需固定出口，以及全链路完整性。精确主机被其他程序使用时同样会走其绑定策略；共享文件停用不影响核心后缀规则。
