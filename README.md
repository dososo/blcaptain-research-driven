# Research-Driven · 研究驱动式调查

> 让 AI 从「找到一个看起来对的答案就交差」,变成「造一个经得起反驳的结论」——更准、更省、更诚实。

[English README](README.en.md) · 界面语言:中文(主) / English

![Agent Skill](https://img.shields.io/badge/Agent-Skill-d98e3a)
![Pure Methodology](https://img.shields.io/badge/Pure-Methodology-2b2622)
![Platforms](https://img.shields.io/badge/Claude_Code_·_Codex_·_Gemini_CLI-supported-2f5ea7)
[![License: Apache 2.0](https://img.shields.io/badge/License-Apache_2.0-4c9a2a)](LICENSE)

<table>
  <tr>
    <td width="50%"><img src="assets/screenshots/investigation-workflow.svg" alt="七步调查循环"></td>
    <td width="50%"><img src="assets/screenshots/claim-confidence.svg" alt="四级确定性分级"></td>
  </tr>
  <tr>
    <td align="center"><strong>调查不是检索:七步循环,该停就停</strong></td>
    <td align="center"><strong>诚实标注确定性:已确证 / 很可能 / 推测 / 未知</strong></td>
  </tr>
</table>

## TL;DR · 一句话结论

装上它,你的 AI agent 研究问题时会像**侦探**,而不是**搜索引擎**:追一手源、独立多方交叉、主动找反例、诚实标确定性、该停就停。结果——**关键答案更靠谱,token 不白烧,错误不甩锅给你。**

它是一个**纯方法论 Skill**:零脚本、零依赖、不碰你的数据。只改变 agent 怎么想,不给你加任何运行负担。

## 为什么做它 · 问题在哪

AI 给答案又快又顺,但有三个要命的毛病,你多半中过招:

1. **它最危险的时候,恰恰是它最自信的时候。** 真正坑你的不是「我不知道」(那它会去查),而是「我以为我知道」——错得越笃定,越不去核。
2. **精力全乱配。** 简单常识查到天荒地老(白烧 token),真正承重的那句结论反而一眼带过(埋雷)。
3. **把回音当印证。** 十个网页互相转载同一个错,它当成「多方证实」;把推测直接写成事实,把「模型的信心」当「证据」。

结果:你拿到一个「看着可信、其实没核过」的答案,信了它去做决策。**而一个自信的错答案,代价远超它省下的那点 token。**

## 我们的观点和原则

一句话:**把「看起来合理的答案」当成调查的起点,不是终点。**

- **调查,不是检索。** 检索问「某个来源怎么说」;调查问「什么是真的、我凭什么信、什么能推翻它」。
- **诚实高于自信。** 最大化正确性,把剩下的不确定性明明白白标给你;**绝不承诺「保证正确」。**
- **纪律,不是工具。** 可靠性不该寄托在「模型这次记得这么做」上,而在一套每次都走的方法。所以它是方法论,不是又一个脚本。

## 它怎么做

**三个杠杆,对应你要的「透 / 深 / 准」:**

| 杠杆 | 具体动作 | 避免 |
|---|---|---|
| **透**(不留盲区) | 把问题拆成 MECE 子问题 + 明确的停止条件 | 收集一堆链接却不证明覆盖 |
| **深**(不停表面) | 每条承重结论追到一手源,盘问它的日期 / 范围 / 是否真支持 | 复述互相点头的二手摘要 |
| **准**(不出错) | 独立多源交叉 + 主动证伪 + 诚实分级 | 把共识、排名、语气当证据 |

**七步调查循环**(见上方左图):界定拆解 → 铺开摸底 → 追一手源 → 独立交叉 → 主动证伪 → 缺口迭代 → 分级结论。

**两个最该盯的动作**(普通 agent 最缺,也是拉开差距的地方):

- **主动证伪 > 收集支持证据。** 从「看起来对」到「真的对」只有一条路:不是找证据证明你的假设对,是**拼命找证据证明它错**。扛住最强反驳的结论,才值得信。
- **该停就停。** 大多数 agent 研究差,不是不会查,是**太早停**(第一个合理答案就交)或**停不下来**(把海洋煮干)。给它明确的收敛判据:关键结论多源印证了吗?找过反例吗?再查一轮还有新东西吗?——到了就停。

## 它能给你带来什么

- **更准。** 主动证伪 + 独立交叉 + 一手源,把「自信的错」挡在产出之前。
- **更省 —— 这条最反直觉,也最值钱。** 它省的不是搜索那几个 token,是**省掉「信了错答案 → 做错决策 → 返工」这条最贵的路**。而且它按风险分配精力:常识直接跳过、只对承重结论深挖、收敛即停,不做过度研究。**把事情一次做对,才是真正的省钱。**
- **更诚实。** 每条结论标 已确证 / 很可能 / 推测 / 未知(见上方右图)。一个诚实的「未知」,比一个自信的错答案有用得多。

## 它的边界 · 我们不吹

诚实是这个 skill 的底色,所以它对自己也诚实:

- 它**不保证正确**,只最大化正确 + 诚实标不确定。
- 长指令会被模型逐渐遗忘,方法论靠 agent 自觉执行,这是它的软肋。对高影响结论,请人也过一眼。
- 它管的是「你有没有循证」,不替你做来源真伪的终极裁决 —— 那一步需要人。

## 最简单的用法

1. 把本目录装到你的 Agent Skill 目录(见下方「安装」)。
2. 在新会话里直接说:

   ```text
   用 research-driven 调查:Python 3.8 和 3.13 是否原生跟随 HTTP 308?
   请给一手来源、反方证据、边界条件,并给每条结论标确定性等级。
   ```

3. 你会拿到:结论 → 决定性证据 → 反证结果 → 边界与开放问题 → 逐条确定性等级。

## 安装

- **Claude Code**:把本目录复制到 `~/.claude/skills/blcaptain-research-driven/`。
- **Codex**:把本目录复制到 `$HOME/.agents/skills/blcaptain-research-driven/`。
- **Gemini CLI**:运行 `gemini skills link /绝对路径/to/blcaptain-research-driven`。

## 目录结构

```text
blcaptain-research-driven/
├── SKILL.md                         # Agent 执行的核心方法论
├── README.md / README.en.md         # 中文 / English 说明
├── LICENSE  VERSION  CHANGELOG.md    # Apache-2.0 / 版本 / 变更记录
├── .gitignore                       # 防止凭据、日志、本机文件误提交
├── agents/interface.yaml            # Agent 展示信息
├── assets/
│   ├── research-log-template.md     # 可选:研究记录模板
│   └── screenshots/                 # 公开配图
├── references/
│   ├── techniques.md                # 深度技巧:拆解 / 一手源 / 交叉 / 证伪 / 停止
│   └── tool-mapping.md              # 三平台能力映射
└── templates/
    ├── research-request.md          # 小白可复制的研究请求
    └── research-result.example.md   # 公开事实的研究示例
```

## 数据与隐私

- 本 Skill 不上传、不保存、不托管任何用户数据或密钥。
- 不要把真实 API Key、Cookie、账号、内部路径、私密 URL 或未授权导出文件放进仓库。
- 只提交公开来源、合成示例和可公开的文档。
- 研究记录模板默认留在本地;发布前请检查是否包含个人信息或内部沟通。

## 关于作者 · About the Author

由 **爆裂队长NEXT(BLCaptain)** 独立创作与维护 · Created and maintained independently by **BLCaptain**.

- GitHub:[@dososo](https://github.com/dososo)
- X / Twitter:[@thinkszyg](https://x.com/thinkszyg)
- 邮箱 / Email:blteam2026@outlook.com
- 开源中国传统纹样图录 · Traditional Chinese Pattern Catalog:[wenyang.net](https://wenyang.net)

觉得有用?欢迎 Star、分享,或在 X 上 @我聊聊。 · If it helps you, please star it, share it, or reach out on X.

## License

Apache License 2.0,见 [LICENSE](LICENSE)。
