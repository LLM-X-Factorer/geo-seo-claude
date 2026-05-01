## 7. 维度四：技术地基（Technical，15%）

> 看起来权重不高，但**它能让前面所有维度归零**。技术不及格 = 全盘归零。

### 7.1 8 大类完整权重表

技术分（满分 100）按以下 8 大类分配。SSR 是 GEO 时代的"生死线"——和 CWV、Speed、Crawlability 并列为最高权重（各 15 分）：

| 类别 | 满分 | 含义 |
|---|---|---|
| Crawlability（可爬性） | 15 | 核心基础 |
| Indexability（可索引性） | 12 | 核心基础 |
| Security（安全） | 10 | 信任信号 |
| URL Structure | 8 | 爬取效率 |
| Mobile Optimization | 10 | Google 强制要求 |
| Core Web Vitals | 15 | 排名信号 |
| **Server-Side Rendering** | **15** | **GEO 关键** |
| Page Speed & Server | 15 | 性能 |
| **总分** | **100** | |

### 7.2 类别 1：Crawlability（15 分）

#### 7.2.1 robots.txt 校验（3 分）

- 抓取 `https://[domain]/robots.txt`
- 校验语法：`User-agent`、`Allow`、`Disallow`
- 检查常见错误：缺 User-agent、通配符封锁重要路径、`Disallow: /` 封整站
- 验证引用了 XML sitemap：`Sitemap: https://[domain]/sitemap.xml`

#### 7.2.2 AI 爬虫访问（5 分，**GEO 关键**）

**完整 14 个 AI 爬虫 user-agent 清单**：

| Crawler | User-Agent | 服务平台 |
|---|---|---|
| GPTBot | `GPTBot` | ChatGPT / OpenAI（训练 + 搜索） |
| OAI-SearchBot | `OAI-SearchBot` | OpenAI 搜索专用（独立规则） |
| ChatGPT-User | `ChatGPT-User` | ChatGPT 浏览模式 |
| ClaudeBot | `ClaudeBot` | Anthropic Claude |
| PerplexityBot | `PerplexityBot` | Perplexity AI |
| Google-Extended | `Google-Extended` | Gemini / Google AI 训练 |
| Googlebot | `Googlebot` | Google 搜索 + AI Overviews |
| Bingbot | `bingbot` | Bing Copilot + ChatGPT（via Bing） |
| Amazonbot | `Amazonbot` | Alexa / Amazon AI |
| CCBot | `CCBot` | Common Crawl（喂多个 AI 模型） |
| FacebookBot | `FacebookExternalHit` | Meta AI |
| Bytespider | `Bytespider` | TikTok / ByteDance AI |
| Applebot-Extended | `Applebot-Extended` | Apple Intelligence |
| Cohere-ai | `Cohere-ai` | Cohere 模型 |
| YouBot | `YouBot` | You.com |

**评分细则**：
- 全部主要 AI 爬虫允许：5 分
- 部分被封但 Googlebot + Bingbot 允许：3 分
- GPTBot 或 PerplexityBot 被封：1 分（GEO 重大影响）
- Googlebot 被封：0 分（致命）

**Important nuance**：封 Google-Extended **不会** 封 Googlebot。Google-Extended 仅控制 AI 训练数据使用，不影响搜索索引。但封 Google-Extended 可能减少 AI Overviews 中的曝光。**推荐允许**，除非有具体的数据授权关切。

**Crawler Access Score 详细算法**：
```
起始 = 100
关键 AI 爬虫每被封 1 个（GPTBot/ClaudeBot/PerplexityBot/OAI-SearchBot/Googlebot）→ -15
次要 AI 爬虫每被封 1 个 → -5
没在 robots.txt 引用 sitemap → -10
下限 = 0
```

**新出现的标准：Content-Signal 指令**

IETF 草案 `draft-romm-aipref-contentsignals` 引入了细粒度的内容用途声明：

```
Content-Signal: ai-train=no, search=yes, ai-personalization=no, ai-retrieval=yes
```

**4 个键的含义**：
- `ai-train`：是否允许用于训练 AI 模型
- `search`：是否允许用于搜索索引
- `ai-personalization`：是否允许用于 AI 个性化
- `ai-retrieval`：是否允许用于 AI 实时检索（如 ChatGPT 搜索时实时取页）

**值**：`yes` / `no`

**应用场景**：版权敏感的内容站（媒体、出版）想"既要 AI 流量、又要保护训练版权"——可以 `ai-train=no, search=yes, ai-retrieval=yes`。

#### 7.2.3 XML Sitemap（3 分）

- 抓取（先看 robots.txt 引用，否则试 `/sitemap.xml`、`/sitemap_index.xml`）
- 校验 XML 语法
- 检查 `<lastmod>` 日期是否存在并准确
- URL 计数 vs 预期可索引页数
- 大站检查 sitemap index（每个 sitemap 最多 50,000 URL）
- 抽查所有 sitemap URL 返回 200

#### 7.2.4 爬取深度（2 分）

- 首页 = 深度 0。检查所有重要页面 ≤ 3 次点击可达
- 深度 4+ 页面爬取预算显著减少，AI 引用概率低
- 检查内链：关键内容页是否从首页或主导航链接？

#### 7.2.5 Noindex 管理（2 分）

- 检查应该被索引的页是否误加 `<meta name="robots" content="noindex">`
- 检查 HTTP `X-Robots-Tag: noindex` 头（**特别注意：可覆盖 meta robots**）
- 常见错误：分页、类目页、关键落地页误加 noindex

### 7.3 类别 2：Indexability（12 分）

#### 7.3.1 Canonical 标签（3 分）

- 每个可索引页必须有 `<link rel="canonical" href="...">`
- Canonical 必须自引用（指向自己）作为权威版本
- 检查冲突 canonical（HTML vs HTTP 头）
- 检查 canonical 链（A → B → C，应直接 A → C）

#### 7.3.2 重复内容（3 分）

- www vs 非 www（两者都解析？哪个 redirect？）
- HTTP vs HTTPS（HTTP 应 redirect 到 HTTPS）
- 尾斜杠一致性
- 参数化重复（`?sort=price` 创建重复页）

#### 7.3.3 分页（2 分）

- 如果有分页内容，检查 `rel="next"` / `rel="prev"`（注：Google 2019 起忽略，但 Bing 仍用）
- 推荐：分页用 `rel="canonical"` 指向 view-all 页或第一页
- 确保分页未被 noindex（如其有独特内容）

#### 7.3.4 Hreflang（多语言站，2 分）

- `<link rel="alternate" hreflang="xx">` 标签
- 双向：A 链 B 则 B 链 A
- x-default 兜底
- 语言/地区码合法（ISO 639-1 / ISO 3166-1）

#### 7.3.5 索引膨胀（2 分）

- 估算已索引页数（sitemap 数 + Google `site:domain.com`）
- 对比实际有价值的内容页
- 如果索引页 >> 内容页 → 索引膨胀（薄页 / 重复 / 参数页）

### 7.4 类别 3：Security（10 分）

#### 7.4.1 HTTPS 强制（4 分）

- 站必须 HTTPS 加载
- HTTP 必须 redirect 到 HTTPS（301）
- 无混合内容警告（HTTPS 页含 HTTP 资源）
- SSL/TLS 证书有效未过期

#### 7.4.2 安全头（6 分）

| 头 | 推荐值 | 用途 |
|---|---|---|
| `Strict-Transport-Security` | `max-age=31536000; includeSubDomains` | 强制 HTTPS |
| `Content-Security-Policy` | 适当策略 | 防 XSS |
| `X-Content-Type-Options` | `nosniff` | 防 MIME 嗅探 |
| `X-Frame-Options` | `DENY` 或 `SAMEORIGIN` | 防 clickjacking |
| `Referrer-Policy` | `strict-origin-when-cross-origin` 或更严 | 控制 referrer 数据 |
| `Permissions-Policy` | 适当限制 | 控制浏览器特性 |

**评分**：
- HTTPS + 有效证书：4 分
- HSTS：2 分
- X-Content-Type-Options：1 分
- X-Frame-Options：1 分
- Referrer-Policy：1 分
- CSP：1 分

### 7.5 类别 4：URL Structure（8 分）

#### 7.5.1 干净 URL（2 分）

- 人类可读：`/blog/seo-guide` 而非 `/blog?id=12345`
- URL 中无 session ID
- 仅小写
- 连字符分词（不是下划线）
- 无特殊字符或编码空格

#### 7.5.2 逻辑层级（2 分）

- URL 路径反映站结构：`/category/subcategory/page`
- 适当扁平——避免不必要的深嵌套
- 站内一致模式

#### 7.5.3 重定向链（2 分）

- 检查重定向链（A → B → C）
- 推荐最多 1 跳（A → C 直接）
- 检查重定向循环
- 全部 301（永久），除非有意临时则 302

#### 7.5.4 参数处理（2 分）

- URL 参数不应创建重复可索引页
- 用 canonical 或 robots.txt Disallow 处理参数变体
- 在 Google Search Console 和 Bing Webmaster Tools 配置参数处理

### 7.6 类别 5：Mobile Optimization（10 分）

#### 关键背景：Google Mobile-First Crawling（2024 年 7 月起完全转移）

**自 2024 年 7 月起，Google 完全使用 mobile Googlebot 抓取所有站。无 desktop 抓取**。如果你的站在移动端不工作，对 Google 就不工作。**这是过去两年最重要的技术 SEO 变化之一**。

#### 7.6.1 响应式设计（3 分）

- `<meta name="viewport" content="width=device-width, initial-scale=1">`
- 移动端无水平滚动
- 无固定宽度元素超过视口

#### 7.6.2 触控目标（2 分）

- 交互元素（按钮、链接）≥ 48×48 CSS 像素
- 触控目标间最小 8px 间距
- 移动端导航可用

#### 7.6.3 字体大小（2 分）

- 基础字号 ≥ 16px
- 无需缩放即可阅读
- 对比度（WCAG AA：正常文本 4.5:1，大文本 3:1）

#### 7.6.4 移动内容对等（3 分）

- 桌面所有内容也在移动端可见
- 不依赖 Googlebot 不能展开的 "read more" 折叠（虽 Google 2025 已改进）
- 图片和媒体在移动端加载

### 7.7 类别 6：Core Web Vitals（15 分）

#### 7.7.1 2026 三个核心指标 + 完整阈值

CWV 用真实用户字段数据的 **75 百分位**作基准。Lab 数据用于调试，但字段数据决定排名信号。

| 指标 | Good | Needs Improvement | Poor | 含义 |
|---|---|---|---|---|
| **LCP**（Largest Contentful Paint） | < 2.5s | 2.5s – 4.0s | > 4.0s | 测加载——最大可见元素渲染时间 |
| **INP**（Interaction to Next Paint） | < 200ms | 200ms – 500ms | > 500ms | **2024 年 3 月取代 FID**。测所有交互响应（不仅首次） |
| **CLS**（Cumulative Layout Shift） | < 0.1 | 0.1 – 0.25 | > 0.25 | 测视觉稳定——意外布局移动 |

**重要更新（必讲给学员）**：INP 已替代 FID。如果你的课件还讲 FID，立刻更新——这个旧指标已经从 Core Web Vitals 移除一年多了。

#### 7.7.2 LCP 风险信号（HTML 静态分析）

- 大首屏图无 `loading="lazy"` 或 `fetchpriority="high"`
- `<head>` 里阻塞渲染的 CSS/JS（无 `media` 属性的样式表，无 `async`/`defer` 的脚本）
- 字体加载无 `font-display: swap` 或 `font-display: optional`
- 关键资源无 preload 提示（`<link rel="preload">`）
- 折叠以上大图无明确 width/height

**LCP 修复**：
1. 优化首屏图：WebP/AVIF 格式、正确尺寸、`<link rel="preload">`
2. 减少服务器响应时间（TTFB < 800ms）
3. 消除阻塞渲染 CSS/JS
4. preconnect 关键第三方源

#### 7.7.3 INP 风险信号

- `<head>` 里大 JS bundle 无 `defer`/`async`
- 大量同步 script 标签
- 复杂 DOM 结构（深嵌套、过多元素）
- 第三方脚本同步加载（分析、广告、widget）
- HTML 里可见 onclick 等事件处理（暗示重 JS 交互层）

**INP 修复**：
1. 长任务（>50ms）拆小，用 `requestIdleCallback` 或 `scheduler.yield()`
2. 减第三方 JS
3. 折叠以下用 `content-visibility: auto`
4. 防抖/节流事件处理

#### 7.7.4 CLS 风险信号

- 图无明确 `width`/`height`
- 嵌入/iframe 无尺寸
- 折叠以上动态注入内容（广告位、横幅）
- 字体加载导致文字重排（无 `font-display`）
- 媒体元素无 `aspect-ratio` CSS 或尺寸属性

**CLS 修复**：
1. 图和视频总是带 `width` 和 `height`
2. 广告和嵌入留位（CSS `aspect-ratio` 或显式尺寸）
3. 字体用 `font-display: swap` + size-adjusted fallback
4. 避免在已存在内容之上注入新内容

**评分**：
- LCP < 2.5s：5 分
- INP < 200ms：5 分
- CLS < 0.1：5 分

### 7.8 类别 7：Server-Side Rendering（15 分）— **GEO 关键**

#### 7.8.1 为什么 SSR 是 GEO 时代的"生死线"

AI 爬虫（GPTBot、ClaudeBot、PerplexityBot 等）**不执行 JavaScript**。它们抓原始 HTML 并解析。如果你的内容由 React、Vue、Angular 或任何 JS 框架在客户端渲染，**AI 爬虫看到的是空白页**。

即便 Googlebot 执行 JS，也会**降低 JS 渲染内容优先级**——因为额外爬取预算。Google 在独立的"渲染队列"处理 JS，可能延迟索引数天到数周。

#### 7.8.2 检测方法

```bash
# 不执行 JS 的方式抓取
curl -s [URL]
```

对比原始 HTML 与浏览器渲染后 DOM。如果关键内容（标题、段落、产品信息、文章正文）**缺失于 curl 输出**，则是客户端渲染。

#### 7.8.3 6 个检查点

- **主内容文本**：文章正文 / 产品描述 / 页面内容是否在原始 HTML？
- **标题**：H1/H2/H3 是否在原始 HTML？
- **导航**：主导航是否服务端渲染？
- **结构化数据**：JSON-LD 是否在原始 HTML 还是 JS 注入？
- **Meta 标签**：title、description、canonical、OG 是否在原始 HTML？
- **内链**：导航和内容链接是否在原始 HTML？（爬取关键）

#### 7.8.4 SSR 解决方案推荐

| 框架 | SSR 解决方案 |
|---|---|
| React | Next.js（SSR/SSG）、Remix、Gatsby（SSG） |
| Vue | Nuxt.js（SSR/SSG） |
| Angular | Angular Universal |
| Svelte | SvelteKit |
| Astro | Astro（默认 SSG） |
| 通用 | Prerender.io、Rendertron（预渲染服务） |

#### 7.8.5 SSR 检测信号

**客户端渲染信号（5 个）**：
1. body 接近空（`<div id="root"></div>`、`<div id="app"></div>`）
2. 客户端框架 bundle 存在但 body 无内容
3. `<noscript>` 标签含 fallback 内容（暗示 JS 依赖）
4. 内容由 fetch/XHR 在 inline script 加载
5. 框架特定路由器但无 SSR 数据

**服务端渲染信号（6 个）**：
1. 完整 HTML 内容在初始响应中
2. `__NEXT_DATA__` script 标签（Next.js SSR/SSG）
3. `__NUXT__` 或 `__NUXT_DATA__`（Nuxt.js SSR/SSG）
4. `data-reactroot` 或 `data-server-rendered` 属性
5. 完整 meta 标签出现在初始 HTML
6. 实质文本内容在 `<body>` 中（脚本执行前）

#### 7.8.6 4 档严重程度

| 等级 | 标准 | 含义 |
|---|---|---|
| **CRITICAL** | body 几乎为空（仅根 div），无 SSR 信号 | AI 爬虫看到空白 |
| **HIGH** | 主内容存在但导航/侧栏/相关内容靠 JS 注入 | 主内容可见，但站结构对 AI 不可见 |
| **MEDIUM** | 主内容 SSR 但交互组件依赖 JS | 内容 OK，交互不影响 AI |
| **LOW** | 完全 SSR，JS 仅做增强 | 理想状态 |

**评分**：
- 全部关键内容服务端渲染：15 分
- 主内容 SSR 但部分元素仅 JS：10 分
- 关键内容需 JS（产品信息、文章正文）：5 分
- 整页客户端渲染（原始 HTML body 空）：0 分

### 7.9 类别 8：Page Speed & Server Performance（15 分）

#### 7.9.1 TTFB（Time to First Byte，3 分）

- 目标：**< 800ms**（理想 < 200ms）
- 测：`curl -o /dev/null -s -w 'TTFB: %{time_starttransfer}s\n' [URL]`
- TTFB > 800ms：检查服务器位置、缓存、数据库查询、CDN

#### 7.9.2 资源优化（2 + 2 分）

- **总页重 < 2MB**（关键页 < 1MB）
- gzip/brotli 压缩
- CSS/JS 压缩
- 未用 CSS/JS（很多站可达 50%+ 字节）

#### 7.9.3 图片优化（3 分）

- 格式：WebP 或 AVIF 优于 JPEG/PNG
- 不超尺寸（图片不大于显示尺寸）
- 折叠以下用 `loading="lazy"`
- 显式宽高（防 CLS）
- **折叠以上图不要 lazy load**（伤 LCP）

#### 7.9.4 代码拆分与懒加载（2 分）

- JavaScript 拆分，每页只加载所需
- 大 JS bundle 警告：> 200KB 压缩后；严重：> 500KB
- 第三方脚本异步（`async` 或 `defer`）
- `<head>` 无阻塞渲染资源

#### 7.9.5 缓存（2 分）

- `Cache-Control` 头检查
- 静态资源长缓存：`max-age=31536000`（1 年）+ 内容哈希文件名
- HTML 短缓存或 `no-cache` + 验证（`ETag` 或 `Last-Modified`）

#### 7.9.6 CDN 使用（1 分）

- 静态资源是否从 CDN 服务（不同域名或 CDN 特定头）
- 全球受众必须 CDN
- CDN 头：`CF-Ray`（Cloudflare）、`X-Cache`（CloudFront）、`X-Served-By`（Fastly）

### 7.10 IndexNow 协议（Bing Copilot 关键）

**什么是 IndexNow**：
开放协议，允许网站即时通知搜索引擎内容创建/更新/删除。**Bing、Yandex、Seznam、Naver 支持。Google 不支持但监控**。

**为什么对 GEO 重要**：
- ChatGPT 用 Bing 索引
- Bing Copilot 用 Bing 索引
- 更快 Bing 索引 = 更快两大 AI 平台可见

**实现检查**：
1. 检查 IndexNow key 文件：`https://[domain]/.well-known/indexnow-key.txt` 或类似
2. 检查 CMS 是否有 IndexNow 插件（WordPress 有插件，许多现代 CMS 原生支持）
3. 如未实现，加上去（约 1 小时工作量，立即生效）

### 7.11 Meta tags 完整 9 行表

| 标签 | 检查 | 缺失/错误后果 |
|---|---|---|
| `<title>` | 有，50–60 字符，含主关键词 | 无标题 = 无搜索 snippet 控制 |
| `<meta name="description">` | 有，150–160 字符，吸引人，含关键词 | 缺 = Google 自己生成 |
| `<link rel="canonical">` | 有，自引用或指向首选版本 | 缺 = 潜在重复内容 |
| `<meta name="robots">` | 检查 noindex/nofollow/noarchive/nosnippet/max-snippet | noindex = 页面排除于搜索 |
| `<meta name="viewport">` | 有 `width=device-width, initial-scale=1` | 缺 = 移动可用性失败 |
| `<html lang="...">` | 有正确语言码 | 缺 = 语言检测问题 |
| Open Graph | og:title/og:description/og:image/og:url/og:type | 缺 = 社交/AI 预览差 |
| Twitter Card | twitter:card/title/description/image | 缺 = X/Twitter 预览差 |
| `<link rel="alternate" hreflang>` | 多语言站需要 | 缺于多语言 = 错误语言 |

### 7.12 技术分级

| 总分 | 评级 | 含义 |
|---|---|---|
| 90–100 | Excellent | 传统 SEO + GEO 都技术扎实 |
| 70–89 | Good | 微调，根本扎实 |
| 50–69 | Needs Work | 显著技术债务影响可见度 |
| 30–49 | Poor | 严重问题阻碍爬取/索引/AI 可见 |
| 0–29 | Critical | 根本技术失败需立即处理 |

---

