# Easy Web Builder

> 反 AI 味儿网站开发与改造技能 —— 让 Agent 做出有独特设计感的网站，告别蓝紫渐变和 SaaS 模板脸。

一个面向 AI 编程助手（ZCode / Claude Code / Cursor / Gemini CLI 等支持 Agent Skills 的运行时）的 **Agent Skill**。它不是一个网站模板库，而是一套**强约束工作流 + 设计宪法**：通过"参照网站锚定 + 交互提问 + 静态 Demo 确认 + 差异化设计 + 最终偏差复核"，逼着 AI 偏离舒适区，产出不像 AI 生成的网站。

## 解决什么问题

直接让 AI"帮我做个网站"，你大概率会得到：

| AI 味儿特征 | 典型表现 |
|------------|---------|
| 配色死板 | 蓝紫渐变（`#6366F1` / `#8B5CF6`）用到吐 |
| 布局死板 | Hero 大标题 + 三卡片并排的标准 SaaS 模板 |
| 字体死板 | 全站 Inter / Roboto |
| Emoji 泛滥 | 满屏 🚀✨ 当功能图标 |
| 内容空洞 | 无真实图片、文案刻板套话 |

本技能用规则 + 流程双重手段规避以上所有问题。

## 核心特性

- **双模式支持**：从零新建网站 / 现有网站改造（保留功能只改视觉），工作流自动适配
- **参照网站锚定**：以用户提供的参照网站为设计锚点，支持 6 种参考维度（完全照抄 / 仅配色 / 仅布局 / 仅功能 / 仅 UI 风格 / 组合参考）
- **强制交互**：先问清楚再动手，避免 AI 自作主张
- **静态 Demo 门禁**：必须先出视觉 Demo、用户确认后才能进入完整开发，防止返工
- **最终偏差复核**：交付前逐项对比成品与参照网站的还原度，偏差超阈值必须向用户确认
- **反 AI 味儿设计宪法**：明确禁止项 + 替代方案，涵盖配色、布局、字体、图标、文案、图片
- **小众组件库路由**：按品牌调性推荐 Aceternity UI / Magic UI / DaisyUI / Radix UI 等，避开千篇一律的大众组件库
- **AGENTS.md 模板**：为生成的项目自动注入项目级设计规则

## 工作流（7 步，顺序执行）

```
1. 交互收集需求 ── 参照网站 URL + 参考维度 + 开发模式
2. 分析参照网站 ── 提取配色/字体/布局/动效/功能/亮点
3. 细节追问     ── 网站类型、品牌调性、技术偏好、动效强度（最多 4 问）
4. 生成设计方案 ── 色值、字体、布局、组件库、动效、差异化说明，等用户确认
5. 静态 Demo    ── 纯视觉页面，用户确认后才继续
6. 完整开发     ── 遵守设计宪法 + 开发规范，注入 AGENTS.md
7. 最终复核     ── 参照网站偏差对比 + 质量检查清单
```

## 安装

### ZCode

```bash
git clone https://github.com/FortC/easy-web-builder.git ~/.zcode/skills/easy-web-builder
```

### Claude Code

```bash
git clone https://github.com/FortC/easy-web-builder.git ~/.claude/skills/easy-web-builder
```

### 其他 Agent Skills 运行时（Cursor / Gemini CLI / OpenCode 等）

将本仓库克隆或复制到你的运行时对应的 skills 目录下，保持目录名 `easy-web-builder`：

```
easy-web-builder/
├── SKILL.md          # 技能主文件（入口，含 frontmatter 与完整工作流）
├── README.md         # 本文件
├── assets/
│   └── agents-template.md   # AGENTS.md 项目规则模板（生成项目时注入）
└── references/
    ├── design-rules.md        # 反 AI 味儿设计宪法（禁止项 + 必须项 + 差异化策略）
    ├── component-libraries.md # 小众组件库推荐与选择决策树
    ├── image-resources.md     # 图片资源库（插画/图标/照片/占位图）
    └── prompt-templates.md    # 提示词模板（角色/反向/文案/语境/组合）
```

## 使用

安装后无需手动调用，技能会按 description 自动触发。对 Agent 说：

- 「帮我做一个类似 linear.app 风格的产品落地页」
- 「参考这个网站的配色，给我做个作品集：<URL>」
- 「把现有项目 www.example.com 改造成复古风格」
- 「照着 stripe.com 抄一个官网」

触发关键词：`做网站`、`开发网页`、`设计官网`、`落地页`、`首页`、`改造网站`、`改版`、`参照某个网站`、`模仿某站风格`、`抄这个网站`、`参考配色/UI/布局`。

技能触发后会依次向你询问参照网站、参考维度和开发模式，然后按 7 步工作流推进。

## 设计规则速览

详细的禁止项和替代方案见 [references/design-rules.md](references/design-rules.md)，核心原则：

- **配色**：禁紫色/靛蓝/蓝紫渐变、禁纯平背景、禁 Tailwind 默认色板；必须主色 + 辅助色 + 点缀色 + 背景纹理
- **布局**：禁 Hero + 三卡片模板、禁完美居中；必须有不对称元素和呼吸节奏
- **字体**：标题字体必须有个性，避开 Inter / Roboto
- **图标**：用 Iconify，禁止 Emoji 当功能图标
- **文案**：具体、口语化，禁"赋能/抓手/闭环"式空话
- **动效**：自定义 cubic-bezier 缓动（禁 ease-in-out），滚动揭示 + hover 微反馈，动效服务内容

## 组件库路由

| 品牌调性 | 推荐组件库 | 动效强度 |
|----------|-----------|----------|
| 科技极客 | Aceternity UI | 炫酷拉满 |
| 现代简约 | Magic UI | 适中 |
| 强烈风格 | DaisyUI（对应主题） | 适中 |
| 艺术反叛 | Brutalist 风格 | 克制 |
| 深色高级 | Glass UI | 适中 |
| 完全定制 | Radix UI | 自定义 |

## License

MIT
