# 图片资源库

> AI 生成的网站默认没有图片，这是 AI 味儿的重要来源。主动集成真实图片资源，网站立刻成熟。

## 一、四类图片资源

### 1. 插画库 — unDraw
- **官网**：https://undraw.co
- **类型**：SVG 矢量插画
- **特点**：可自定义主色调，与网站配色统一
- **使用方式**：
  - 搜索关键词（如 "developer", "analytics", "team"）
  - 选择与网站主色匹配的颜色
  - 下载 SVG 或直接复制 SVG 代码
- **适用场景**：功能介绍区、空状态、404 页面

### 2. 图标库 — Iconify
- **官网**：https://iconify.design
- **规模**：20 万+ 免费矢量图标
- **图标集**：Material Icons、Font Awesome、Lucide、Heroicons、Tabler 等 100+ 集合
- **使用方式**：
  - 网页：`<script src="https://code.iconify.design/iconify-icon/2.1.0/iconify-icon.min.js"></script>`
  - React：`npm install @iconify/react`
  - 搜索图标：https://icon-sets.iconify.design
- **适用场景**：导航菜单、功能列表、按钮图标、社交链接

### 3. 真实照片 — Pexels
- **官网**：https://www.pexels.com
- **类型**：免费高质量真实照片
- **特点**：提供 API 可程序化搜索
- **API 使用**：
  ```
  GET https://api.pexels.com/v1/search?query=关键词&per_page=15
  Header: Authorization: YOUR_API_KEY
  ```
- **适用场景**：Hero 背景、团队展示、产品场景图、博客封面

### 4. 占位图 — Picsum Photos
- **官网**：https://picsum.photos
- **特点**：URL 直接指定尺寸，每次刷新不同真实照片
- **使用方式**：
  - 指定尺寸：`https://picsum.photos/800/600`
  - 指定种子（固定图片）：`https://picsum.photos/seed/xxx/800/600`
  - 灰度：`https://picsum.photos/800/600?grayscale`
  - 模糊：`https://picsum.photos/800/600?blur=2`
- **适用场景**：开发阶段临时占位、图片墙、画廊

## 二、图片集成提示词模板

```
请根据网站内容，主动搜索并集成以下图片资源：

1. 插画：使用 unDraw.co，搜索与 [网站主题] 相关的 SVG 插画，
   颜色调整为网站主色 #XXXXXX

2. 图标：使用 Iconify 图标库，选择 [图标集名称] 风格的图标，
   通过 CDN 或 npm 引入

3. 真实照片：使用 Pexels 搜索 [关键词]，用于 Hero 背景和
   内容区块，图片必须与网站主题相关

4. 占位图：开发阶段使用 Picsum Photos，格式为
   https://picsum.photos/seed/{语义化名称}/{宽}/{高}

要求：
- 每个内容区块至少有 1 张图片或插画
- 图片尺寸必须与容器匹配，禁止拉伸变形
- 图片必须有 alt 文本描述
- Hero 区域图片必须加暗色遮罩以保证文字可读性
```

## 三、图片使用规范

| 场景 | 推荐资源 | 尺寸建议 | 注意事项 |
|------|----------|----------|----------|
| Hero 背景 | Pexels | 1920×1080+ | 必须加遮罩，文字对比度 ≥ 4.5:1 |
| 功能图标 | Iconify | 24×24 / 32×32 | 统一图标集，线宽一致 |
| 内容插画 | unDraw | 自适应 SVG | 颜色与主色统一 |
| 卡片配图 | Picsum/Pexels | 400×300 | 固定 seed 避免刷新变化 |
| 团队头像 | Pexels | 200×200 | 圆形裁剪，真实人脸 |
| 博客封面 | Pexels | 800×450 | 16:9 比例 |

## 四、禁止事项

- ❌ 禁止使用 AI 生成的通用感插画（千篇一律的扁平人物）
- ❌ 禁止使用 Emoji 代替功能图标
- ❌ 禁止图片拉伸变形（必须保持原始比例或 object-fit: cover）
- ❌ 禁止所有图片使用同一个占位图（必须用不同 seed）
- ❌ 禁止图片无 alt 文本（无障碍要求）
