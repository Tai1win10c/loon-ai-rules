# Loon AI Suite

面向个人固定出口分流的 AI 服务远程规则集。首次发布：2026-10-27。

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
| [SOURCES.md](SOURCES.md) | 来源、核验状态和维护判据 |
| [CHANGELOG.md](CHANGELOG.md) | 每次变更原因与验证情况 |

## 每周维护

已在 ChatGPT 创建独立检查任务：每周二上午（Asia/Singapore，UTC+8），首次安排在 2026-11-03。它不是 GitHub Actions，也不意味着所有接口都能由程序自动发现。

- 优先核对官方网络文档和动态语音地址，兼顾用户实际漏匹配日志。
- 有可靠依据、影响明确的精确域名新增可直接更新并记录来源。
- 扩大共享后缀范围或可能破坏功能的删除先请用户确认。
- 抓取失败保留现有规则并报告；不把未能核验写成“无变化”。
- 当前 GitHub 连接器可读，但写入返回权限不足；首次发布使用用户授权的浏览器完成。后续若连接器仍不可写，尝试已授权的浏览器；登录失效则报告阻塞，不承诺无人值守写入。
- **仅维护 Tai1win10c/loon-ai-rules，禁止修改账号下其他仓库。**

## 当前边界

首次发布继承用户规则，并非逐个平台全量复核。此次核实并补入 frontend-apps-multi-region.workos.com，依据 OpenAI 官方允许列表；其他来源状态见 SOURCES.md。

现有共享主机可能影响非 AI 服务流量。防火墙允许列表不能证明所有主机都必须同出口；规则集也不能保证未来新增域名、第三方请求或系统流量全部固定出口。

ChatGPT Voice IP 暂为用户提供的快照：本次官方 JSON 抓取失败，已标明未核实当前完整性。语音 UDP、IPv6、代理链稳定性需结合实际请求另行验证。

已完成规则文本检查和发布后回读一致性验证；用户设备上的 Loon 导入及端到端覆盖尚待实际验证。无永久完整性或零泄漏保证。
