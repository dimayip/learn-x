# Learning-X

<p align="left">
  <a href="./README.md">English</a> ·
  <a href="./README.zh-CN.md"><b>简体中文</b></a>
</p>

<p align="left">
  <a href="https://github.com/bellchen/learning-x/stargazers"><img src="https://img.shields.io/github/stars/bellchen/learning-x?style=flat-square" alt="Stars"></a>
  <a href="https://github.com/bellchen/learning-x/network/members"><img src="https://img.shields.io/github/forks/bellchen/learning-x?style=flat-square" alt="Forks"></a>
  <a href="https://github.com/bellchen/learning-x/issues"><img src="https://img.shields.io/github/issues/bellchen/learning-x?style=flat-square" alt="Issues"></a>
  <a href="./LICENSE"><img src="https://img.shields.io/github/license/bellchen/learning-x?style=flat-square" alt="License"></a>
</p>

> **一个 Socratic 式的学习引导 skill——把"我想学 X"变成可操作的理解，并且每次会话都留下一个你可以带走的成果物。**

`learning-x` 是一套**领域无关**的教练框架，面向 AI 助手（以及希望把学习会话开得更好的人类引导者）。它不"讲课"：先诊断学习者真正的起点，每轮只引入一个概念，用结构化的 A/B/C/D 选择题代替开放式提问，每 3 轮左右做一次 lock-in 回顾，正确答案后再用"魔鬼代言人"追问压一压深度，最后每次会话都以**学习者自己产出的东西**作为结束。

无论 X 是一门编程语言、一个数学概念、一个设计模式、一个工具、一个框架、一个领域还是一项软技能，这套框架都适用。

---

## 为什么需要这个 skill

绝大多数学习失败，都是因为**讲得太多、太快**——在学习者还没把新概念接入自己的心智模型之前，信息已经灌完了。传统"直接解释一遍"的互动会让学习者一边点头一边遗忘，48 小时内几乎完全失效。

`learning-x` 的设计只围绕一个视角转换：

> **学习者掌舵（负责把事情想明白）。教练执行（只问，不讲）。**

skill 里每一条规则、每一个提问模板、每一步工作流，都是为了让学习者的大脑**保持主动**而不是被动接收。

---

## 何时使用

当用户说出类似下面这些话时，就该触发本 skill：

- "教我 X" / "帮我学 Y" / "我想搞懂 Z" / "带我入门 ..."
- "help me learn / understand / get good at ..."
- "能不能带我过一遍 ...?"
- "我一直没搞清楚 ..."

尤其适用于：

- 主题复杂、多层次
- 学习者的起点不清楚
- 之前"看看文档就懂了"没能奏效

**不适用场景**：纯事实查询（"Python 是哪年发布的？"）、或者需要 Agent 直接替学习者干活（写代码、修 bug）。这些应该路由到其他 skill。

---

## 核心哲学——每轮必须同时激活的 4 层

每一轮对话都应该**同时**激活以下 4 层。只问问题（L3）却不锚定目标（L1）、也不产出任何东西（L4）的对话，会让整场会话逐渐漂移。

| 层 | 作用 | 当轮示例 |
|----|------|--------|
| **L1 · 锚点** | 保持对目标 + 参照样例的视野 | *"别忘了你说下个月要做出 X，这个概念就是为这件事服务的。"* |
| **L2 · 纪律** | 控制节奏：先诊断、单概念、lock-in、魔鬼代言人 | *"先别急着看我解释——你**以为**它是干嘛的？"* |
| **L3 · 战术** | Socratic 动作：prime / hypothesize / verify / apply / reflect / challenge | *"A / B / C 选一个——哪个更符合你的直觉？"* |
| **L4 · 产物** | 每几轮就要产出一件具体的东西 | *"用你自己的话写一个 5 行版本。"* |

---

## 5 条硬纪律

1. **先诊断，再教学。** 开场先问**目的、先前印象、相邻知识**。**绝不**用内容开场。
2. **每轮只引入一个新概念。** 多出来的概念进队列，不要堆叠。每个概念都配一个小于 3 分钟的微任务。
3. **结构化选择优先于开放式提问。** 用"A / B / C——选哪个，为什么？"替代"你会怎么做？"。永远给学习者留一个"选 D（自己的答案）"的空间。
4. **每 ~3 轮做一次 lock-in 回顾。** 显式复盘：已经锁住的 + 下一步要做的。具体且简短，胜过含糊的大回顾。
5. **正确答案之后要用魔鬼代言人追问。** 对只是便宜，深度才贵。别停在"答对了"，再挤一个假设出来。

每条规则的完整理由见 [`SKILL.md`](./SKILL.md)。

---

## 4 阶段工作流

```
阶段 1 — Onboarding           阶段 2 — 路径提案
（先诊断，不教）       ──►   （3–7 个里程碑，学习者确认）
                                         │
                                         ▼
阶段 4 — 产物            阶段 3 — 里程碑循环
（demo / cheat sheet /  ◄──  （prime → hypothesize → reveal → verify
 mindmap / flashcards ...）    → challenge；每 3 轮 lock-in）
```

**阶段 1 — Onboarding。** 用 [`references/diagnose-playbook.md`](./references/diagnose-playbook.md) 中的 3–4 个诊断问题起手。**此时不教任何东西**，即使学习者的先前理解是错的。

**阶段 2 — 路径提案。** 基于诊断结果，给出 3–7 个有序里程碑，让学习者确认或替换。这一步的目的是让学习者**和你共同拥有计划**。

**阶段 3 — 里程碑循环。** 每个里程碑走一遍 6 步微循环：*prime → hypothesize → reveal + 微任务 → verify → challenge*，每 ~3 轮做一次 lock-in。

**阶段 4 — 产物。** 每次会话都以学习者产出的东西作为结束：可运行的 demo、自己话写的 cheat sheet、mindmap、反思笔记、flashcards、或者"教回来"。**没有产物的会话几乎等于没学。**

---

## 仓库结构

```
learning-x/
├── SKILL.md                               # 完整 skill 规范——哲学、规则、工作流
├── README.md                              # 英文总览
├── README.zh-CN.md                        # （本文件）中文总览
└── references/
    ├── diagnose-playbook.md               # 开场动作：按主题类型的问题脚本
    ├── question-templates.md              # 6 类 Socratic 模板（prime / hypothesize / verify / apply / reflect / challenge）
    └── session-patterns.md                # 概念 / 工具 / 技能 / 领域 / 语言 学习的适配工作流
```

- **[`SKILL.md`](./SKILL.md)** — Canonical spec。AI agent 真正加载执行的文件。想用或想移植这个 skill 从这里入手。
- **[`references/diagnose-playbook.md`](./references/diagnose-playbook.md)** — 会话前 3–10 分钟的脚本化开场 + 需要倾听的信号。
- **[`references/question-templates.md`](./references/question-templates.md)** — 每个 Socratic 动作的可复用措辞库。需要换个问法或避免用词重复时加载。
- **[`references/session-patterns.md`](./references/session-patterns.md)** — 概念学习 vs. 工具上手 vs. 技能构建 vs. 领域知识 vs. 语言习得，分别该怎么排会话。

---

## 反模式

skill 规范里明确列了这些反模式，因为这是"好意的会话仍然失败"的最常见原因：

- **整段灌输式解释**，哪怕学习者求你"直接告诉我就好"。
- **空洞的表扬**（"你好聪明！"），只会训练出寻求认可的反射，不会带来理解。
- **无视学习者说过的目标**，绕到无关的基础知识上。
- **不分对象的统一节奏**，对初学者和已有相邻背景的人用一样的速度。
- **结尾没有产物。**

---

## 校准旋钮

框架是去适配学习者的，不是反过来：

| 情况 | 调整方式 |
|------|--------|
| 完全零基础 | 更多 prime、更小粒度、更多复述、更早产物 |
| 有相邻领域经验 | 跳过基础，加大 challenge，节奏放快 |
| 学习者说"直接告诉我就好" | 讨价还价："那我们先猜一个，一秒钟就好，好吗？" |
| 学习者沉默 | 把抽象度降一级，或者举一个具体例子 |
| 学习者跟你的答案争论 | 鼓励它——认真对待，他可能是对的 |
| 有时间盒 | 压缩里程碑数量；把最后 10% 留给产物 |

---

## 如何在 AI agent 中使用这个 skill

支持 skill 加载的平台（CodeBuddy / Claude skills 等）：

1. 把整个目录放到平台的 skills 文件夹下（例如 `.codebuddy/skills/learning-x/`）；
2. 当用户的请求匹配 skill 描述（学习、教练、"教我 X" 等）时，agent 会自动加载 `SKILL.md`；
3. `references/` 下的文件**按需加载**——agent 只在当前对话真正需要详细脚本、问题措辞或特定场景指引时才读。

如果你是自己当引导者：完整读一遍 `SKILL.md` 把 5 条规则内化，会话时把三份 reference 文件开在旁边随时查。

---

## 设计原则（给想 fork 或改造这个 skill 的人）

- **领域无关优先。** 核心规范里的每一条都必须能对任何 X 适用。主题相关的微调只能放在 `references/session-patterns.md` 里，不能污染主规则。
- **规则优于建议。** 5 条规则是**难以绕过**的硬规则。软建议会在压力下被忽略；硬规则会幸存。
- **Reference 按需加载。** `SKILL.md` 保持精简，让 agent 能便宜地持有；更深的材料按轮次 opt-in。
- **没有产物 = 没学。** 整套框架以**留存**为优化目标，而留存最高杠杆的一招是**产出可带走的东西**。

---

## ⭐ Star 历史

[![Star History Chart](https://api.star-history.com/svg?repos=bellchen/learning-x&type=Date)](https://star-history.com/#bellchen/learning-x&Date)

---

## License

除非单独文件另有说明，本仓库内容遵循 MIT License。详见 [`LICENSE`](./LICENSE)。

---

## Credits

由 [@bellchen](https://github.com/bellchen) 设计并维护。融合了 Socratic 教学、认知负荷理论、retrieval practice 以及 "harness engineering" 中"掌舵 / 执行 分离"的思路——压缩成一套**在真实会话里跑得动**的规则集。

---

> 📝 本中文版本由 GitHub Actions 自动翻译生成，可能并非 100% 准确。如有歧义，**请以英文版本为准**。
