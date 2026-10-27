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

其他组目前仅继承用户提供的域名，须查找对应官方来源后逐步补充。Meta/Muse 的产品关联、旧 Azure/CDN 主机和 ChatGPT Voice 地址需优先复核。

## 维护判据

1. 新增必须记录来源、日期、用途和精确/共享属性。
2. DNS 可解析或出现在社区列表中，单独不足以证明必须固定出口。
3. 官方防火墙允许列表解决“可访问性”；不证明每个主机必须同一个出口。
4. 抓取失败、重定向或暂时无请求，不构成删除依据。
5. 共享域名范围扩张、可能破坏功能的删除先请用户确认。
6. 不公开账号、代理密码、固定出口地址或原始请求日志。
