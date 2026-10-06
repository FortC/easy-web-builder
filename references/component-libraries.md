# 反 AI 味儿组件库推荐

> AI 默认会选 Tailwind + Shadcn UI，这些库最专业但也最容易产生 AI 味儿。
> 主动指定小众但有特色的组件库，能立刻提升网站独特性。

## 一、高优先级推荐（动效强、视觉冲击大）

### Aceternity UI
- **官网**：https://ui.aceternity.com/components
- **特点**：炫酷视觉效果组件，高计算量视觉
- **代表组件**：
  - Sparkles（闪光粒子背景）
  - Aurora Background（极光背景）
  - Meteors（流星效果）
  - Spotlight（聚光灯跟随鼠标）
  - Text Generate Effect（文字逐字生成）
  - Card Spotlight（卡片聚光）
- **适用场景**：科技感产品、创意工作室、SaaS 落地页
- **使用提示**：AI 可能不熟悉用法，必须让 AI 阅读官方文档

### Magic UI
- **官网**：https://magicui.design
- **特点**：150+ 动画组件，专注微交互
- **代表组件**：
  - Shimmer Button（流光按钮）
  - Text Gradient（文字渐变动画）
  - Animated Grid（动态网格背景）
  - Number Ticker（数字滚动）
  - Marquee（无缝滚动）
  - Globe（3D 地球）
- **适用场景**：需要丰富微交互的产品页、作品集

## 二、风格化组件库（强烈个性）

### DaisyUI
- **官网**：https://daisyui.com
- **特点**：30+ 预设主题，基于 Tailwind
- **代表主题**：
  - cyberpunk（赛博朋克）
  - retro（复古）
  - cupcake（甜美）
  - forest（森林）
  - night（暗夜）
  - coffee（咖啡）
- **适用场景**：需要快速建立强烈风格的网站

### Brutalist UI（粗野主义）
- **特点**：粗边框、硬阴影、高对比、无圆角
- **视觉语言**：故意"粗糙"，反精致
- **适用场景**：艺术网站、独立品牌、反叛风格产品
- **实现方式**：可通过自定义 CSS 实现，关键是 `border-2 border-black shadow-[4px_4px_0px_#000]`

### Glass UI（玻璃拟态）
- **特点**：半透明、背景模糊、微妙边框
- **关键 CSS**：`backdrop-filter: blur(12px)` + `bg-white/10` + `border border-white/20`
- **适用场景**：深色背景网站、仪表盘、音乐类产品

## 三、高度可定制组件库

### Radix UI
- **官网**：https://www.radix-ui.com
- **特点**：无样式原语组件，完全自定义外观
- **优势**：无障碍访问内置，样式 100% 可控
- **适用场景**：需要完全独特外观的复杂应用

### Mantine
- **官网**：https://mantine.dev
- **特点**：100+ 组件，功能丰富，主题系统强大
- **优势**：比 Shadcn 更少人用，默认样式就有辨识度
- **适用场景**：中后台系统、复杂 Web 应用

### ikun-ui
- **官网**：https://ikun-ui.netlify.app
- **特点**：基于 Svelte.js + UnoCSS
- **适用场景**：Svelte 项目，追求轻量和独特性

## 四、组件库选择决策树

```
用户需求是什么？
├── 炫酷视觉效果 / 科技感 → Aceternity UI
├── 丰富微交互 / 动效 → Magic UI
├── 强烈风格主题 → DaisyUI（选对应主题）
├── 艺术 / 反叛 / 独立 → Brutalist 风格
├── 深色 / 高级 / 模糊 → Glass UI
├── 完全自定义外观 → Radix UI
└── 功能丰富的应用 → Mantine
```

## 五、使用注意事项

1. **小众组件库 AI 不熟悉**：必须在提示词中附上官方文档 URL，要求 AI 先阅读文档再使用
2. **不要混用多个组件库**：一个项目选 1 个主组件库 + 最多 1 个动效库
3. **Context7 插件**：如果开发环境支持，安装 Context7 可实时查询最新文档
4. **版本兼容**：确认组件库与项目框架（React/Vue/Svelte）兼容
5. **性能考量**：Aceternity UI 的粒子/极光效果消耗 GPU，移动端需降级
