# Research-Driven Investigation

> 把 AI 从“找到一个看起来合理的答案”，带到“构造一个经得起反驳的结论”。

[English README](README.en.md) · 界面语言：中文（主文档）/ English

![Agent Skill](https://img.shields.io/badge/Agent-Skill-d98e3a)
![Pure Methodology](https://img.shields.io/badge/Pure-Methodology-2b2622)
![Platforms](https://img.shields.io/badge/Claude_Code_·_Codex_·_Gemini_CLI-supported-2f5ea7)
[![License: Apache 2.0](https://img.shields.io/badge/License-Apache_2.0-4c9a2a)](LICENSE)

一个面向 Claude Code、Codex、Gemini CLI 的纯方法论 Agent Skill。它不提供脚本、不保存数据、不托管密钥，只改变 Agent 研究问题时的思考和行动方式。

<table>
  <tr>
    <td width="50%"><img src="assets/screenshots/investigation-workflow.svg" alt="研究驱动七步调查流程：从问题到分级结论"></td>
    <td width="50%"><img src="assets/screenshots/claim-confidence.svg" alt="结论卡片示例：证据、反证、边界与确定性等级"></td>
  </tr>
  <tr>
    <td align="center"><strong>七步调查流程：从问题到分级结论</strong></td>
    <td align="center"><strong>结论卡片：让不确定性一目了然</strong></td>
  </tr>
</table>

## 我们做什么

Research-Driven 把普通的 retrieval（检索）升级为 investigation（调查式研究）：

- 把复杂问题拆成 MECE 子问题，避免盲点。
- 把关键事实追溯到一手来源，而不是停在搜索摘要或二手转述。
- 用至少两个真正独立的来源交叉验证关键结论。
- 主动寻找反例、边界条件和最强反方证据。
- 用 Confirmed / Probable / Speculative / Unknown 标记确定性。
- 只有在覆盖完整、反证完成、结论收敛后才停止；同时避免对琐碎问题过度研究。

## 为什么做

AI 很擅长快速生成“像答案”的文字，但常见问题是：

1. 第一个 plausible answer 就停下，遗漏关键分支。
2. 多个网页只是互相转载，却被误认为多源印证。
3. 只收集支持材料，没有主动寻找能推翻结论的证据。
4. 把推测写成事实，把模型信心写成证据。

这个 Skill 不承诺“保证正确答案”。它的目标是最大化正确性，并把剩余不确定性明确交给读者。

## 能解决什么问题

适合：

- 核对文档、API、价格、许可证、标准、版本差异和当前事实。
- 处理多部分问题、来源冲突、低置信度判断和高影响决策。
- 需要把研究过程交接给团队，或让结论可复核的任务。
- 需要同时使用 Claude Code、Codex、Gemini CLI 的跨平台研究。

不适合：

- 已经高度确定的简单事实。
- 闲聊、纯排版和机械编辑。
- 需要绕过登录、访问私密数据或处理未授权资料的任务。

## 最简单的用法

1. 把本目录安装到你的 Agent Skill 目录。
2. 在新会话里直接说：

   ```text
   使用 blcaptain-research-driven 调查：Python 3.8 和 3.13 是否原生跟随 HTTP 308？
   请给出一手来源、反方证据、边界条件和每条结论的确定性等级。
   ```

3. 你会得到：结论、决定性证据、反证结果、边界与开放问题、逐结论确定性等级。

## 安装

- Claude Code：将本目录复制到 `~/.claude/skills/blcaptain-research-driven/`。
- Codex：将本目录复制到 `$HOME/.agents/skills/blcaptain-research-driven/`。
- Gemini CLI：运行 `gemini skills link /absolute/path/to/blcaptain-research-driven`。

## 工作流

| 步骤 | Agent 要做什么 |
|---|---|
| 1. Frame and decompose | 明确决策、边界和 MECE 子问题。 |
| 2. Survey the landscape | 先建立来源地图，找出争议和盲点。 |
| 3. Trace to primary sources | 追到官方文档、原始论文、源码或原始记录。 |
| 4. Cross-verify | 用至少两个真正独立的来源核对关键结论。 |
| 5. Actively disprove | 钢人化反方，寻找反例、边界和失败证据。 |
| 6. Identify gaps and iterate | 明确未知项，继续循环直到满足 STOP 条件。 |
| 7. Synthesize with graded certainty | 先给结论，再给证据、反证、边界和确定性等级。 |

## 目录结构

```text
blcaptain-research-driven/
├── SKILL.md                         # Agent 执行的核心方法论
├── README.md                        # 中文说明
├── README.en.md                     # English documentation
├── LICENSE                          # Apache License 2.0
├── VERSION                          # 发布版本
├── CHANGELOG.md                     # 面向用户的版本记录
├── .gitignore                       # 防止凭据、日志和本机文件误提交
├── agents/
│   └── interface.yaml               # Agent 展示信息
├── assets/
│   ├── research-log-template.md     # 可选研究记录模板
│   └── screenshots/                 # 公开示例图
├── references/
│   ├── techniques.md                # 深度研究技巧
│   └── tool-mapping.md              # 三个平台的能力映射
└── templates/
    ├── research-request.md          # 小白可复制的研究请求
    └── research-result.example.md   # 公开事实研究示例
```

## 数据与隐私

- 本 Skill 不上传、不保存、不托管任何用户数据或密钥。
- 不要把真实 API Key、Cookie、账号、内部路径、私密 URL 或未授权导出文件放进仓库。
- 只提交公开来源、合成示例和可公开的文档。
- 研究记录模板默认留在本地；发布前请检查是否包含个人信息或内部沟通。

## 关于作者

由 爆裂队长NEXT（BLCaptain）独立创作与维护。

- GitHub：[@dososo](https://github.com/dososo)
- X / Twitter：[@thinkszyg](https://x.com/thinkszyg)
- 邮箱：blteam2026@outlook.com
- 开源中国传统纹样图录项目维护者：[wenyang.net](https://wenyang.net)

如果这个项目对你有帮助，欢迎 Star、分享，或在 X 上 @我交流。

## License

Apache License 2.0，见 [LICENSE](LICENSE)。
