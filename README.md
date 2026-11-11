# Loon AI Suite

面向个人固定出口分流的 AI 服务远程规则集。首次发布：2026-10-27。

当前版本：**2026-11-11-login-1**。有效规则 **620 条**（本轮补充 X 和 Instagram 登录主机）；详见 CHANGELOG.md。

范围：排除中国来源 AI，已移除 TRAE 及按项目来源口径移除的 Dify。Dify 有美国运营主体，此处按项目起源分类，不等同于公司注册地判断；来源说明见 SOURCES.md。

## 添加到 Loon

在 Loon 的远程/订阅规则中新增下列原始文件地址，并将策略选择为你已有的 IPRoyal-Chain：

https://raw.githubusercontent.com/Tai1win10c/loon-ai-rules/main/AI-Suite.list

规则文件不包含节点账号、密码或固定 IP；代理链仍由本地 Loon 配置管理。不要将 GitHub 的 blob 网页地址当作订阅地址。

将该订阅排在宽泛的 Google、Apple、Microsoft 及通用代理规则之前，并检查更高优先级规则是否抢先匹配。首次拉取后在 Loon 请求日志检查登录、对话、文件上传及语音的实际策略。启用 Loon 提供的订阅自动更新；仓库内容更新与客户端重新拉取是两个环节。

若已有同用途 AI Suite 订阅，建议记录原地址后替换其 URL，沿用 IPRoyal-Chain 策略，避免重复导入造成排查混乱。

Loon 官方订阅规则说明：https://nsloon.app/docs/Rule/sub_rule/

## 文件

| 文件 | 用途 |
| --- | --- |
| [AI-Suite.list](AI-Suite.list) | 可订阅规则，基于用户现用清单 |
| [Anthropic-Shared.list](Anthropic-Shared.list) | Anthropic 共享依赖补充（可选，精确主机） |
| [SOURCES.md](SOURCES.md) | 来源、核验状态和维护判据 |
| [CHANGELOG.md](CHANGELOG.md) | 每次变更原因与验证情况 |

## 每周维护

已在 ChatGPT 创建独立检查任务：每周二上午（Asia/Singapore，UTC+8），首次安排在 2026-11-03。它不是 GitHub Actions，也不意味着所有接口都能由程序自动发现。

- 排除中国来源 AI，不从社区聚合清单重新加入 TRAE、Dify 等已移除项目；共享基础设施不按此整域删除。
- 对全部已收录 AI 服务查询官方文档、GitHub 规则/源码/Issues/PR/提交、Reddit 和开发者用户公开分享；用户日志仅作为补充。
- 覆盖优先：有可追溯社区依据的候选可直接更新，无须等待官方确认；注明证据等级、共享影响和用途置信度。
- 用户已授权 Muse 的 Meta/Facebook/Instagram 共享依赖及其他 AI 的合理社区依赖；同类有据新增直接更新。可能破坏功能的删除或无边界全球 CDN 扩张仍需确认。
- 抓取失败保留现有规则并报告；不把未能核验写成“无变化”。
- 当前 GitHub 连接器可读，但写入返回权限不足；首次发布使用用户授权的浏览器完成。后续若连接器仍不可写，尝试已授权的浏览器；登录失效则报告阻塞，不承诺无人值守写入。
- **仅维护 Tai1win10c/loon-ai-rules，禁止修改账号下其他仓库。**

## 当前边界

首次发布继承用户规则，并非逐个平台全量复核。此次核实并补入 frontend-apps-multi-region.workos.com，依据 OpenAI 官方允许列表；其他来源状态见 SOURCES.md。

现有共享主机可能影响非 AI 服务流量。防火墙允许列表不能证明所有主机都必须同出口；规则集也不能保证未来新增域名、第三方请求或系统流量全部固定出口。

ChatGPT Voice 使用 2026-11-03 成功获取的 OpenAI 官方 JSON 快照，包含 402 个 IPv4 /32 目的地址。语音 UDP、IPv6、代理链稳定性需结合实际请求另行验证。

已完成规则文本检查和发布后回读一致性验证；用户设备上的 Loon 导入及端到端覆盖尚待实际验证。无永久完整性或零泄漏保证。

## 验证本地同步

手动更新 Loon 中该远程规则订阅，查看已下载规则是否包含：

```text
# Revision: 2026-11-11-login-1
DOMAIN-SUFFIX,metaaivm.com
DOMAIN-SUFFIX,metaaiusercontent.com
```

若界面隐藏注释，可搜索 `DOMAIN,x.com` 与 `DOMAIN,www.instagram.com`。当前文本含 620 条有效规则，注释不计入；客户端显示数量可能因处理方式不同而不同，可用上述规则核对。原始地址保持不变，无须换 URL。

本版已纳入 meta.com、facebook.com、fbcdn.net、cdninstagram.com 等共享域名，相关非 AI 流量也会命中 IPRoyal-Chain。社区候选的实际必需性与全功能覆盖置信度为 **6/10（待实测）**；这与“文件已发布并可下载”的验证是两回事。

本轮同步确认：搜索新增的 `claude.app`，并确认已无 `dify.ai`、`udify.app`、`trae.ai` 和 `traeapi.us` 规则。移除仅影响此 AI 远程规则集，不会自动阻断这些服务，也不保证其在本地其他规则中不再走代理。

## Anthropic 共享依赖补充

核心域名已在 AI-Suite.list 中。本次新增独立补充文件 **Anthropic-Shared.list**，版本 **2026-11-02-anthropic-shared-1**，共 **12 条精确 DOMAIN 规则**；主文件仍为 620 条。该文件不独立替代主文件。

如需将这些共享请求也统一出口，在 Loon 中另加远程规则地址，并与主文件都绑定到同一个 IPRoyal-Chain 策略：

https://raw.githubusercontent.com/Tai1win10c/loon-ai-rules/main/Anthropic-Shared.list

把此补充订阅放在可能抢先匹配这些主机的远程规则之前，并检查更高优先级本地规则；下载成功不等于实际命中，需看 Loon 请求详情。可搜索 cdn.jsdelivr.net 和 http-intake.logs.us5.datadoghq.com 确认下载内容。

### 是否必须统一所有请求出口

核心认证/API/内容连接一致最值得优先保证，现已覆盖官方列出的 Anthropic 核心主机。官方对启用组织 IP 允许列表的场景明确强调 bridge.claudeusercontent.com 与核心 API 同出口。公共字体、脚本 CDN、插件下载和遥测则不等于都被要求同出口；本次是根据用户偏好扩大覆盖，不作必需性承诺。

补充文件的 12 个主机分为 Artifacts JS 库、可选遥测、CLI 插件/安装/发行说明/更新主机。fonts.googleapis.com 和 fonts.gstatic.com 已在主文件，无须重复。

域名分流无法区分发起应用：github.com、raw.githubusercontent.com、registry.npmjs.org、storage.googleapis.com、cdnjs.cloudflare.com 等主机上的非 Claude 流量也会命中补充策略，可能包含大文件下载。精确 DOMAIN 不覆盖所有子域，也不会强制所有全球 CDN 走固定出口。仅启用主文件仍可保持核心 Anthropic 域名固定出口；补充文件可随时单独停用。

插件自选地址、第三方 MCP、外部 OAuth、用户输入的网址及特定 googlesource Gerrit 检出等仍可能产生额外请求；此补充不保证任意用法全链路同出口，也不约束 Anthropic 云端服务器自己发起的网络请求。无需为此修改手机证书或开启 HTTPS 解密。

来源：[Claude Code 官方网络要求](https://code.claude.com/docs/en/network-config)、[Desktop 官方网络要求](https://code.claude.com/docs/en/desktop)。
