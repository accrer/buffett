# 巴菲特思维

**学习笔记·非官方**

用中文、按概念整理的伯克希尔·哈撒韦致股东信学习笔记：49 个概念的自写讲解，加一份 9 类 30 题的生意体检题。全部以第三人称讲解，只用于学习和自查。

仓库还附带 4 个按 Agent Skills 通行格式编写的技能（buffett skills），可接入 Claude Code、Codex、Cursor 等 AI agent，见下文「如何接入 agent」。

> **先读这三条**
>
> 1. 本仓库**不构成任何投资建议**，不推荐、不评价任何具体证券，也不给估值、目标价或买卖时点。
> 2. 本仓库与伯克希尔·哈撒韦公司、沃伦·巴菲特先生、查理·芒格先生及其家属没有任何关联，未获授权或背书。
> 3. 文中少量英文短引**不在本仓库的开源许可范围内**，著作权归原权利人所有（详见下文「引文说明」和 [LICENSE.md](LICENSE.md)）。

## 目录

| 路径 | 内容 |
|---|---|
| [concepts/01-valuation-and-mindset.md](concepts/01-valuation-and-mindset.md) | A. 估值与心态（第 1–4 条） |
| [concepts/02-business-quality.md](concepts/02-business-quality.md) | B. 生意质量（第 5–9 条） |
| [concepts/03-people-and-governance.md](concepts/03-people-and-governance.md) | C. 人与治理（第 10–14 条） |
| [concepts/04-capital-allocation.md](concepts/04-capital-allocation.md) | D. 资本配置（第 15–20 条） |
| [concepts/05-holding-and-portfolio.md](concepts/05-holding-and-portfolio.md) | E. 买入、持有与组合（第 21–28 条） |
| [concepts/06-accounting-and-finance.md](concepts/06-accounting-and-finance.md) | F. 会计与财务口径（第 29–36 条） |
| [concepts/07-instruments.md](concepts/07-instruments.md) | G. 投资工具（第 37–38 条） |
| [concepts/08-industries.md](concepts/08-industries.md) | H. 行业专题（第 39–49 条） |
| [checklist/business-checkup.md](checklist/business-checkup.md) | 生意体检题：9 类 30 题 |
| [docs/quotes-policy.md](docs/quotes-policy.md) | 引文规则与位置索引 |
| [skills/buffett-perspective/](skills/buffett-perspective/SKILL.md) | 技能（首推）：巴菲特视角（六步框架，第三人称分析） |
| [skills/business-quality-checkup/](skills/business-quality-checkup/SKILL.md) | 技能：生意体检（9 类 30 题追问，输出自查报告） |
| [skills/decision-process-review/](skills/decision-process-review/SKILL.md) | 技能：决策复盘自查（6 个维度反问） |
| [skills/letters-concept-guide/](skills/letters-concept-guide/SKILL.md) | 技能：股东信概念导航（49 个概念讲解与阅读年份） |
| [LICENSE.md](LICENSE.md) | 许可与排除项 |
| [.github/ISSUE_TEMPLATE/takedown.md](.github/ISSUE_TEMPLATE/takedown.md) | 删除 / 修改请求模板 |

## 怎么用

- **想理解一个概念**：在 `concepts/` 里找到对应条目。每条包括自写讲解、值得读的年份，以及对应的体检题编号。
- **想检查自己的生意或决策**：打开 [生意体检题](checklist/business-checkup.md)，逐题自己回答。题目只帮助整理思路，不给结论、不打分、不估值。
- **想读原文**：按条目里写的年份，到伯克希尔官网的股东信栏目阅读英文原信（见下文「出处」）。

## 如何接入 agent

`skills/` 下有 4 个技能，每个都是一个文件夹，里面有 `SKILL.md`（YAML 头部含 `name` 和 `description`）和精简的 `references/`：

| 技能 | 用途 |
|---|---|
| `buffett-perspective`（首推） | 巴菲特视角：按能力圈、护城河、管理层、资本回报与再投资、安全边际、反向自查六步，用第三人称（「按巴菲特的框架看……」）分析自己的生意或项目，或学习这套框架 |
| `business-quality-checkup` | 对**自己的**生意或项目做 9 类自查，输出只列事实、缺口和风险点的报告 |
| `decision-process-review` | 复盘自己一次投资或花钱决策的**思考过程**，不评价标的 |
| `letters-concept-guide` | 讲解 49 个概念，并列出值得读的股东信年份 |

四个技能都不扮演任何人，也不以巴菲特的口吻说话，不给证券买卖、估值或目标价意见，每次输出都带「不构成投资建议」的提示。

建议先从 `buffett-perspective` 开始，需要逐题自查、复盘决策或查概念时再用另外三个。

**推荐做法：整个仓库克隆下来，再把技能放到 agent 能发现的位置。** 这样技能可以读到 `concepts/` 和 `checklist/` 里的完整内容。只复制技能文件夹也能用：这时技能会改用自带的 `references/`（精简索引和题目提纲）。

常见位置（以各工具的官方文档为准）：

| 工具 | 个人级（所有项目可用） | 项目级（只在某个仓库里可用） |
|---|---|---|
| Claude Code | `~/.claude/skills/<技能名>/` | 项目内 `.claude/skills/<技能名>/` |
| Codex | `~/.agents/skills/<技能名>/`（旧版也读 `~/.codex/skills/`） | 项目内 `.agents/skills/<技能名>/` |
| Cursor | `~/.cursor/skills/<技能名>/` 或 `~/.agents/skills/<技能名>/` | 项目内 `.cursor/skills/` 或 `.agents/skills/`；也兼容 `.claude/skills/` |

安装示例（个人级，以 Claude Code 为例，其他工具把目标目录换成上表中的位置）：

```bash
git clone <本仓库地址> buffett-mindset
mkdir -p ~/.claude/skills
cp -R buffett-mindset/skills/buffett-perspective ~/.claude/skills/
cp -R buffett-mindset/skills/business-quality-checkup ~/.claude/skills/
cp -R buffett-mindset/skills/decision-process-review ~/.claude/skills/
cp -R buffett-mindset/skills/letters-concept-guide ~/.claude/skills/
```

说明：

- 复制到个人目录后，技能读不到仓库里的 `concepts/`，会自动改用 `references/`，功能完整但讲解更精简。
- 想在 agent 里用完整讲解，可以直接在克隆下来的仓库里打开 agent，把技能放到该仓库的项目级目录（例如 `.claude/skills/`）里，再让 agent 按 `SKILL.md` 的说明读取 `concepts/` 和 `checklist/`。
- 也可以用符号链接代替复制，但各工具对符号链接的支持不同（例如 Windows 上默认可能无法创建），本仓库不依赖符号链接。
- 技能内容同样采用 CC BY 4.0；引文规则不变，技能里不含任何引文。

## 引文说明

- 全仓库共 8 条英文短引，来自 8 封不同的信，每封最多 1 句，每句不超过 40 个英文单词，不用招牌金句。
- 每条引文用引用块标出，写明年份和出处，并紧跟一段篇幅为引文 2–3 倍的自写评述。
- 每条引文都已对照伯克希尔官网发布的原文逐字核对；拿不准原话的一律不引。
- 本仓库不收录任何一封信的全文或大段原文，不提供中文译文，也不使用任何第三方译文。
- **引文不在本仓库的开源许可（CC BY 4.0 / MIT）范围内**，著作权归原权利人所有。规则和位置见 [docs/quotes-policy.md](docs/quotes-policy.md)。

## 出处

正文中的出处只写文字，例如「1992 年致股东信」。伯克希尔·哈撒韦致股东信的英文原文，请到官网的股东信索引页阅读：

- Berkshire Hathaway Inc., Shareholder Letters：https://www.berkshirehathaway.com/letters/letters.html

本仓库只放上面这一个总链接，不做逐年链接，不嵌入、不镜像、不转存原文。链接只为方便读者找到原始出处，不表示获得伯克希尔·哈撒韦或任何权利人的许可或背书；如权利人要求，会立即删除。

## 删除通道

如果你是权利人，或者认为本仓库的任何内容不当，请在本仓库提交 Issue，选择「删除 / 修改请求（Takedown request）」模板，并确保 Issue 带有标签 `takedown`。维护者会在核实后尽快删除或修改相关内容。

## 许可

- 自写文字：CC BY 4.0。
- 代码：本仓库当前不含代码；日后如有，采用 MIT License。
- 排除项：英文短引及其他第三方材料不在上述许可范围内。
- 详见 [LICENSE.md](LICENSE.md)。

## Using with AI agents

The `skills/` folder contains four skills in the common Agent Skills format. Each skill is a folder with a `SKILL.md` file (YAML frontmatter with `name` and `description`) and a compact `references/` folder:

| Skill | What it does |
|---|---|
| `buffett-perspective` (start here) | Analyzes the user's own business or project, or teaches the framework, in six steps drawn from the shareholder letters: circle of competence, moat, management, returns on capital and reinvestment, margin of safety, and inversion. Always written in the third person, for example 「按巴菲特的框架看……」 |
| `business-quality-checkup` | Walks the user through a 9-part self-check of **their own** business or project and produces a report of facts, gaps, and risk points |
| `decision-process-review` | Reviews the **reasoning process** behind the user's own investment or spending decision, without judging any specific security |
| `letters-concept-guide` | Explains 49 value-investing concepts in plain words and lists which shareholder-letter years to read |

We recommend starting with `buffett-perspective` and using the other three for question-by-question self-checks, decision reviews, or concept lookups.

None of the skills impersonate anyone, speak in Buffett's voice, or give buy/sell, valuation, or price-target opinions on any security, and every output ends with a not-investment-advice notice (「不构成投资建议」).

**Recommended: clone the whole repository**, then place the skills where your agent can discover them. With the full repository available, the skills can read `concepts/` and `checklist/`. Copying only a skill folder also works: the skill then falls back to its bundled `references/` (compact index and question outline).

Common locations (refer to each tool's official documentation for the current details):

| Tool | Personal (all projects) | Project (one repository) |
|---|---|---|
| Claude Code | `~/.claude/skills/<skill-name>/` | `.claude/skills/<skill-name>/` in the project |
| Codex | `~/.agents/skills/<skill-name>/` (older versions also read `~/.codex/skills/`) | `.agents/skills/<skill-name>/` in the project |
| Cursor | `~/.cursor/skills/<skill-name>/` or `~/.agents/skills/<skill-name>/` | `.cursor/skills/` or `.agents/skills/` in the project; `.claude/skills/` is also supported |

Example (personal install for Claude Code; for other tools, replace the target folder with one from the table):

```bash
git clone <this-repository-url> buffett-mindset
mkdir -p ~/.claude/skills
cp -R buffett-mindset/skills/buffett-perspective ~/.claude/skills/
cp -R buffett-mindset/skills/business-quality-checkup ~/.claude/skills/
cp -R buffett-mindset/skills/decision-process-review ~/.claude/skills/
cp -R buffett-mindset/skills/letters-concept-guide ~/.claude/skills/
```

Notes:

- A copied skill cannot see the repository's `concepts/`, so it uses `references/` instead. It still works, with shorter explanations.
- For the full explanations, open your agent inside the cloned repository and put the skills in that repository's project-level folder (for example `.claude/skills/`).
- Symlinks also work in many tools, but support varies (for example, they may not be available by default on Windows), so this repository does not rely on them.
- The skills are licensed under CC BY 4.0 like the rest of the text. They contain no quotations.

## 免责声明 / Disclaimer

> **免责声明**
>
> 1. **无关联、无背书。** 本仓库是个人的学习笔记，属于非官方项目，与伯克希尔·哈撒韦公司（Berkshire Hathaway Inc.）、沃伦·巴菲特先生、查理·芒格先生及其家属**没有任何关联**，也未获得其授权、认可或背书。仓库名称和正文中出现的上述名称，只用于描述性地说明本仓库讨论的主题。
> 2. **不模仿本人。** 本仓库不包含上述人士的肖像、声音或签名，也不以任何方式模仿或代表其发言。文中的框架、问题清单和评述都是仓库作者用自己的话写的，代表仓库作者的个人理解，不代表上述人士的观点。
> 3. **引文版权与许可排除。** 文中少量英文引文出自沃伦·巴菲特致伯克希尔·哈撒韦股东的信，每条都注明了年份和出处，只用于评论和学习。这些引文以及其他第三方材料的著作权归原权利人所有，**不适用**本仓库的 CC BY 4.0（文字）或 MIT（代码）许可。转载、改编本仓库时，请勿把引文当作 CC BY 4.0 内容再授权。
> 4. **以原文为准。** 引文可能有转录错误，请以伯克希尔·哈撒韦官网发布的原文为准。本仓库不收录股东信全文或大段原文，也不含任何第三方中文译文。
> 5. **链接。** 本仓库提及或链接伯克希尔·哈撒韦官网，只是为了方便读者找到原始出处，不表示获得该网站或权利人的许可或背书。如权利人要求，我们会立即删除相关链接或引文。
> 6. **商标。** 「Berkshire Hathaway」「伯克希尔·哈撒韦」及相关名称、标识，可能是其各自权利人的商标或商号，归各自权利人所有。本仓库使用这些名称只是为了指称和描述，不表示存在任何关联。
> 7. **非投资建议。** 本仓库只用于学习投资理念和自查思考过程，**不构成任何投资建议**，不推荐、不评价任何具体证券或金融产品，不提供估值、目标价、买卖时点或资产配置建议。投资有风险，决策请独立判断，必要时咨询持牌专业人士。
> 8. **无担保。** 本仓库内容按「现状」提供，不保证准确、完整或及时，也不构成法律、税务或其他专业意见。
> 9. **联系与删除。** 如果你是权利人，或者认为本仓库的任何内容不当，请在本仓库提交 Issue，并加上标签 `takedown`。这是本仓库唯一的删除请求入口。我们会在核实后尽快删除或修改。

> **Disclaimer**
>
> 1. **No affiliation or endorsement.** This repository is an unofficial personal study project. It is **not affiliated with, authorized, sponsored, or endorsed by** Berkshire Hathaway Inc., Mr. Warren E. Buffett, Mr. Charles T. Munger, or their families. These names appear in the repository name and text solely to describe the subject matter discussed.
> 2. **No impersonation.** This repository contains no likeness, voice, or signature of any of these individuals and does not imitate or speak for them. All frameworks, checklists, and commentary are written by the repository author in their own words and reflect only the author's personal understanding.
> 3. **Quotations and license exclusion.** A small number of short English quotations from Warren E. Buffett's letters to Berkshire Hathaway shareholders are included, each with its year and source, for commentary and educational purposes only. Copyright in these quotations and any other third-party material remains with the respective rights holders. They are **not licensed** under this repository's CC BY 4.0 (text) or MIT (code) licenses; please do not relicense them as CC BY 4.0 content when reusing this repository.
> 4. **Refer to the original.** Quotations may contain transcription errors; the original letters as published on the Berkshire Hathaway website prevail. This repository does not reproduce full letters or long excerpts and contains no third-party translations.
> 5. **Links.** Any reference or link to the Berkshire Hathaway website is provided only to help readers locate the original source and does not imply permission or endorsement by that website or any rights holder. We will promptly remove any link or quotation upon the rights holder's request.
> 6. **Trademarks.** "Berkshire Hathaway" and related names and marks may be trademarks or trade names of their respective owners. They are used here only for identification and description, and no affiliation is implied.
> 7. **Not investment advice.** This repository is for learning about investment principles and reviewing one's own thinking process only. It **does not constitute investment advice**, does not recommend or evaluate any specific security or financial product, and provides no valuations, price targets, trade timing, or asset-allocation advice. Investing involves risk; make your own decisions and consult a licensed professional where appropriate.
> 8. **No warranty.** All content is provided "as is" without any warranty of accuracy, completeness, or timeliness, and is not legal, tax, or other professional advice.
> 9. **Contact & takedown.** If you are a rights holder or believe any content here is inappropriate, please open an Issue in this repository with the label `takedown`. This is the only channel for takedown requests. We will review and remove or revise the content promptly.

## 作者

1379
