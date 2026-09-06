# ai-agent-learning

个人 AI 概念学习资料仓库：包含一个可复用的**概念学习资料生成 Skill**（项目级），以及由该 Skill 生成、经本人核查修改的概念学习资料。

## 仓库用途

1. 沉淀"学一个新概念"的标准方法——以项目级 Skill 的形式固化，可迭代、可复用
2. 保存课程学习中生成的结构化概念学习资料（当前主题：Agent、大模型的上下文、Skill）
3. 作为后续课程项目的个人工具基础和作品集材料

## 目录结构

```
ai-agent-learning/
├── .workbuddy/
│   └── skills/
│       └── learning-material-generator/
│           └── SKILL.md            # 概念学习资料生成 Skill（项目级）
├── learning-materials/
│   ├── agent.html                  # 概念资料：Agent（智能体）
│   ├── llm-context.html            # 概念资料：大模型的上下文
│   ├── skill.html                  # 概念资料：Skill（智能体技能）
│   └── concept-relationship.html   # 三概念关系说明（文字 + 表格 + 关系图）
├── README.md
└── .gitignore
```

## Skill 的存放路径

- **项目级 Skill**：`.workbuddy/skills/learning-material-generator/SKILL.md`（本仓库，随仓库共享）
- 项目级 Skill 与用户级 Skill 的区别：用户级放在 `~/.workbuddy/skills/` 仅个人跨项目可用；项目级放在仓库内，克隆本仓库的协作者都能使用

## 如何在 WorkBuddy 中调用

1. 在 WorkBuddy 中打开本仓库文件夹作为工作区
2. 对话中说类似这样的话即可触发：
   - "用 learning-material-generator 学一下 RAG 这个概念"
   - "帮我生成'微调（fine-tuning）'的学习资料，我是初学者"
3. Skill 会自动：联网核实真实资料来源 → 按固定结构（学习目标 / 核心问题 / 我的理解 / 核心机制 / 应用场景 / 概念辨析 / 自测题 / 参考来源）生成单文件 HTML → 保存到 `learning-materials/` → 执行自检清单并提醒人工核查

## 已生成的学习资料

| 文件 | 概念 | 一句话定位 |
|---|---|---|
| `learning-materials/agent.html` | Agent（智能体） | 不只会聊天，还会自己决定"下一步做什么"去完成任务的 AI 系统 |
| `learning-materials/llm-context.html` | 大模型的上下文 | 模型生成每个字时能"看到"的全部信息，是它唯一的工作记忆 |
| `learning-materials/skill.html` | Skill（智能体技能） | 把"某类任务怎么做"写成文件夹沉淀下来，让 Agent 随用随取 |
| `learning-materials/concept-relationship.html` | 三者关系 | Agent 是干活的"人"，上下文是"工作台"，Skill 是"操作手册" |

每份资料均为单文件 HTML（无外部依赖），双击即可在浏览器打开；自测部分为**交互式单选题**——点击选项即时判分（对/错高亮）、展开解析、自动计分，可一键重新作答。

## 使用 AI 后的人工核查与修改

本仓库内容采用"AI 生成 + 人工核查修改"的方式完成，具体核查记录如下：

1. **资料来源核查（最重要）**：三份概念资料中的全部参考来源，均通过联网搜索逐一核实链接真实存在、可公开访问，无编造链接。来源以官方文档与官方工程博客为主（Anthropic《Building Effective Agents》、Anthropic 上下文窗口中文文档、Agent Skills 官方博客与开放标准 skill.md 等）
2. **概念定义核查**：核心定义与官方文档原文核对——如 Agent 与 Workflow 的分界（流程控制权归属）、上下文窗口"工作记忆"的定义、Skill 的 YAML 必需字段（name、description）与渐进式披露机制
3. **自测题答案核查**：自测题参考答案与正文表述逐条对照，确保一致
4. **"我的理解"部分**：以第一人称类比重写，未整段照搬 AI 对话或来源原文；后续会继续用自己的语言修订（每个概念至少保留一个原创类比）
5. **界面与自测形式升级（2026-09-06 二次迭代）**：四份资料统一升级视觉模板（渐变页头、吸顶目录导航、卡片式排版、每概念独立主题色）；自测由折叠问答改为交互式单选题（即时判分 + 解析 + 计分 + 重新作答），同步更新了 SKILL.md 的输出规范，保证后续生成的新资料沿用同一格式
6. **后续使用建议**：用该 Skill 学习新概念时，生成后应重点修改"我的理解"小节，使其真正成为自己的表述

## 安全说明

- 本仓库不含任何 API Key、密码或个人隐私信息
- `.gitignore` 已排除 `.env`、密钥文件、系统杂项等敏感内容
- 学习资料中引用的外部链接均为公开可访问的官方/权威来源

## 技术环境

- 生成工具：WorkBuddy（AI Agent）+ 项目级 Skill `learning-material-generator`
- 仓库创建与推送：`gh` CLI + git
- 学习资料：纯 HTML + 内联 CSS，无外部依赖
