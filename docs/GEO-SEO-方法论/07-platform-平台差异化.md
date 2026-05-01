## 9. 维度六：平台差异化优化（Platform，10%）

### 9.1 关键事实：5 个 AI 平台引用源**只有 11% 重叠**

ChatGPT 引用的域和 Google AIO 引用的域**重叠率只有 11%**。这意味着不能用一套策略打所有平台。

5 大平台各自的偏好画像（再次回顾，本章会展开每个平台的细节）：

| 平台 | 引擎背景 | 偏好的信号 | 每答案引用源数 |
|---|---|---|---|
| Google AI Overviews | Google 索引 | 已排前 10、问答型标题、答案前置段、对比表 | 单一答案源 + 引用 |
| ChatGPT 搜索 | Bing 索引 + OAI-SearchBot | Wikipedia/Wikidata、专家署名、可直接引用的事实陈述 | 2–4 |
| Perplexity AI | 自家 PerplexityBot | Reddit / Stack Overflow / Quora、原始数据、新鲜度 | **5–15** |
| Google Gemini | Google 全生态 | YouTube、Knowledge Graph、GBP、长内容 | 多源 + 多模态 |
| Bing Copilot | Bing 索引 + 微软生态 | LinkedIn、IndexNow、企业向 | 3–5 |

### 9.2 Google AI Overviews（AIO）

#### 9.2.1 AIO 选源逻辑

- **92% AIO 引用来自已排进 top 10 自然搜索结果的页**——传统 SEO 是入场券
- 但 **47% 引用来自 5 名以下**——AIO 有自己的选择逻辑，偏好清晰直接而非纯排名
- 强烈偏好**清晰结构、直接答案、可扫描格式**
- 与 Featured Snippet 优化有 **70% 重叠**
- 偏好**简洁、事实、无歧义**——对冲和填充降低引用概率

#### 9.2.2 10 项优化清单

1. **问句标题**：H2/H3 用问句模式匹配真实查询。看 Google "People Also Ask" 镜像那些精确问法。
2. **第一段直接答案**：每个问句标题后立即给 1–2 句清晰答案，再展开。第一句必须能独立成引用候选。
3. **表格和结构化对比**：AIO 大量引用表格。把任何对比、定价、规格、特性数据转 HTML 表格，列头清晰。
4. **有序和无序列表**：流程用有序列表，特性用无序列表，AIO 直接抽。
5. **FAQ 区块**：加专门 FAQ 区，5–10 个真实问题，H3 标题。FAQPage schema 富片段虽受限，但内容模式仍助 AIO 抽取。
6. **定义和术语解释**：行业术语提供清晰定义，格式 `**[Term]** is [简洁定义]`。AIO 频繁引用定义。
7. **统计带来源**：精确数字 + 归属（"According to [Source], [统计]"）。AIO 偏好可引用、具体的断言。
8. **发布日期**：可见的发布日期 + 最后更新日期。AIO 对时间敏感查询的无日期内容去优先级。
9. **作者署名**：作者名 + 资质。链接到含 bio + 资质 + sameAs 的作者页。
10. **页面深度**：目标页距首页 ≤ 3 次点击。AIO 很少引用深、孤立内容。

#### 9.2.3 评分细则（满分 100）

| 标准 | 分值 | 评分方法 |
|---|---|---|
| 在目标查询排进 top 10 | 20 | 是 20；top 20 时 10；超出 0 |
| 问句标题存在 | 10 | 每个问句标题 2 分，封顶 10 |
| 标题后直接答案 | 15 | 每个直接答案 3 分，封顶 15 |
| 对比数据有表格 | 10 | 适当用表 10；部分 5；无 0 |
| 流程/特性有列表 | 10 | 有 10；部分 5 |
| FAQ 5+ 问题 | 10 | 5+ 10；1–4 5；无 0 |
| 统计带引用 | 10 | 每个有引用统计 2 分，封顶 10 |
| 发布/更新日期可见 | 5 | 都有 5；一个 3；无 0 |
| 作者署名 + 资质 | 5 | 完整 5；仅名字 3；无 0 |
| 干净 URL + 标题层级 | 5 | H1>H2>H3 干净 5；小问题 3；断 0 |

### 9.3 ChatGPT 搜索

#### 9.3.1 ChatGPT 选源逻辑

- 用 **Bing 索引**（不是 Google）
- 顶级引用源：**Wikipedia 47.9%**、**Reddit 11.3%**、YouTube、主流新闻
- 重度依赖**实体识别**——品牌作为结构化实体存在（Wikipedia/Wikidata/Crunchbase）则更易被引用
- 偏好**权威、成熟**源 over 新或细分站
- 长综合文章引用频率高于短篇
- 倾向引用**最规范**源而非原创者

#### 9.3.2 10 项优化清单

1. **Wikipedia 存在**：检查品牌/人/产品是否有 Wikipedia 文章。如无，评估 notability。如够 notable，起草。如已有，确保准确当前。
2. **Wikidata 实体**：验证实体在 Wikidata。如无，创建含关键属性的 item：instance of、官网、社交媒体、创立日期、总部位置。
3. **Bing Webmaster Tools**：站注册并验证。提交 sitemap。检查爬错。
4. **Bing 索引覆盖**：用 `site:domain.com` 在 Bing 验证关键页索引。Bing 索引页可能与 Google 不同。
5. **Reddit 权威**：检查品牌的 Reddit 提及。识别相关 subreddit。评估真实参与度。
6. **YouTube 存在**：验证 YouTube 频道含相关内容。视频描述含完整 URL 和实体信息。
7. **权威外链**：ChatGPT/Bing 重度看重 .edu、.gov、主流出版反向链接。审计反向链接画像。
8. **实体一致性**：品牌名、创立日期、领导层、关键事实在 Wikipedia、Crunchbase、LinkedIn、官网保持一致。
9. **综合内容**：目标 ChatGPT 引用的页应 **2000+ 词**，话题透彻覆盖。ChatGPT 偏好单一权威源 over 多个薄页。
10. **清晰归属**：含 About 区块、公司描述、创立故事。ChatGPT 用这些做实体锚定。

#### 9.3.3 评分细则（满分 100）

| 标准 | 分值 | 评分方法 |
|---|---|---|
| Wikipedia 文章存在且准确 | 20 | 存在 20；stub 10；无 0 |
| Wikidata 实体含 5+ 属性 | 10 | 完整 10；基础 5；无 0 |
| Bing 索引覆盖关键页 | 10 | 完整 10；部分 5；差 0 |
| Reddit 品牌提及（正面） | 10 | 活跃讨论 10；提及 5；无 0 |
| YouTube 频道含相关内容 | 10 | 活跃 10；存在但稀疏 5；无 0 |
| 权威反向链接（.edu/.gov/出版） | 15 | 每类权威反向链接 3 分，封顶 15 |
| 跨平台实体一致性 | 10 | 一致 10；小差异 5；大差 0 |
| 内容综合度（2000+ 词） | 10 | 透彻 10；够用 5；薄 0 |
| Bing Webmaster Tools 配置 | 5 | 验证 5；无 0 |

### 9.4 Perplexity AI

#### 9.4.1 Perplexity 选源逻辑

- 顶级引用源：**Reddit 46.7%**、Wikipedia、YouTube、主流出版
- 在所有 AI 搜索平台中**最重视社区验证**
- 强烈偏好**讨论帖**——多人讨论、验证、扩展观点的地方
- 偏好近期内容——发布日期是强排名信号
- 每答案引用 **5–15 源**——中等权威站有更多机会进入引用池
- 用自家爬虫 + 搜索 API

#### 9.4.2 10 项优化清单

1. **活跃 Reddit 存在**：品牌或代表在相关 subreddit 真实参与。**不要营销腔——有用、具体、社区导向**。
2. **AMA 和讨论帖**：参与或主持 AMA、深度讨论帖、社区 Q&A。Perplexity 视这些为高信号。
3. **论坛和社区存在**：Reddit 之外，看 Hacker News、Stack Overflow、Quora、行业垂直论坛。
4. **讨论友好内容**：发观点文、研究发现、反向看法、原创数据——被分享和讨论的内容排名更高。
5. **新鲜度信号**：可见日期，定期更新。Perplexity 比其它平台对陈旧内容去优先级更激进。
6. **多源验证**：内容中的断言被其它源支持。Perplexity 交叉验证，偏好多源验证的断言。
7. **YouTube 视频内容**：标题、描述、字幕含目标信息。
8. **直接、可引用的段落**：每段独立可引。每段一个清晰观点 + 证据。
9. **原创数据和研究**：发原创调查、基准、案例研究、数据集。Perplexity 重度偏好一手源。
10. **Perplexity Pages**：检查 Perplexity 是否为你的话题/品牌创建了"Page"。这些是策展摘要，影响未来引用。

#### 9.4.3 评分细则（满分 100）

| 标准 | 分值 | 评分方法 |
|---|---|---|
| 在相关 subreddit 活跃存在 | 20 | 活跃贡献者 20；提及 10；无 0 |
| 论坛/社区提及（HN、SO、Quora） | 10 | 多平台 10；一个 5；无 0 |
| 内容新鲜度（6 个月内） | 10 | 近期 10；1 年内 5；旧 0 |
| 原创研究/数据发布 | 15 | 原创研究 15；案例 10；部分数据 5；无 0 |
| YouTube 含字幕的内容 | 10 | 活跃频道 10；部分视频 5；无 0 |
| 可引用、独立段落 | 10 | 每个良好结构段落 2 分，封顶 10 |
| 多源断言验证 | 10 | 良好来源 10；部分 5；无 0 |
| 生成讨论的内容 | 10 | 被分享/讨论 10；部分互动 5；无 0 |
| Wikipedia/Wikidata 存在 | 5 | 存在 5；无 0 |

### 9.5 Google Gemini

#### 9.5.1 Gemini 选源逻辑

- 用 **Google 搜索索引** + 强烈偏向 Google 自家资产
- **YouTube 内容权重显著高于标准 Google Search**
- Google Business Profile 数据被 Gemini 直接读取
- 直接用 Google **Knowledge Graph**——KG 中存在实体是重大优势
- Schema.org 结构化数据被 Gemini 直接消费做实体理解
- **多模态**——可同时引用图、视频、文本

#### 9.5.2 10 项优化清单

1. **Google Knowledge Panel**：检查品牌是否有 Knowledge Panel。如无，通过 GBP 或结构化数据 claim。确保信息准确。
2. **Google Business Profile**：完整优化 GBP 全部字段：营业时间、服务、照片、帖子、Q&A。Gemini 对本地查询直接拉 GBP。
3. **YouTube 策略**：每个关键话题创建 YouTube 内容。优化标题、描述、时间戳、闭路字幕。Gemini 引用 YouTube 比其它 AI 平台都多。
4. **YouTube 章节和时间戳**：用章节（描述里的时间戳），让 Gemini 引用视频特定段。
5. **Google Merchant Center**：电商必须商品在 GMC。Gemini 直接引用产品数据。
6. **结构化数据（Schema.org）**：实施综合 Schema.org 标记。Gemini 比其它平台用得更激进做实体理解。
7. **Google 生态存在**：跨 Google 生态：Google Scholar（研究）、Google News（出版）、Google Maps（本地）。
8. **图片优化**：Gemini 多模态。描述性 alt 文本、结构化文件名、高质量图。每个内容配相关图。
9. **Google E-E-A-T 信号**：所有标准 Google E-E-A-T 信号都额外加权。作者页、About 页、编辑政策、专长展示。
10. **Chrome Web Store / Workspace Marketplace**：软件公司在 Google 平台存在加实体信号。

#### 9.5.3 评分细则（满分 100）

| 标准 | 分值 | 评分方法 |
|---|---|---|
| Google Knowledge Panel 存在 | 15 | 完整 15；部分 10；无 0 |
| GBP 完整 | 10 | 完整优化 10；基础 5；无 0 |
| YouTube 频道含话题相关内容 | 20 | 活跃含章节 20；存在 10；无 0 |
| Schema.org 实施 | 15 | 综合 15；基础 10；最小 5；无 0 |
| Google 生态（Scholar、News、Maps） | 10 | 3+ 10；1–2 5；无 0 |
| 图片优化 | 10 | 全部 10；部分 5；无 0 |
| E-E-A-T 信号 | 10 | 强 10；部分 5；弱 0 |
| GMC（如电商） | 5 | 适用且活跃 5；不适用 N/A |
| 多模态内容 | 5 | 富多模态 5；部分 3；纯文本 0 |

### 9.6 Bing Copilot

#### 9.6.1 Copilot 选源逻辑

- 用 **Bing 索引**（与 ChatGPT 共享基础设施但不同选择逻辑）
- 支持 **IndexNow** 实时索引新/更新内容
- 倾向引用**更少源**（典型 3–5）但归属更显眼
- 微软生态集成：LinkedIn、GitHub、Microsoft Learn 加权
- 偏好清晰、结构化、快加载页

#### 9.6.2 10 项优化清单

1. **Bing Webmaster Tools**：注册并验证站。提交 XML sitemap。修爬错。
2. **IndexNow 实施**：实时通知 Bing 内容变化。在 `/.well-known/indexnow-key.txt` 提交 key 文件，发布/更新时 ping IndexNow API。
3. **LinkedIn 公司页**：完整带准确描述、员工连接、定期发帖。Copilot 索引 LinkedIn 内容。
4. **GitHub 存在**：技术公司维护活跃 GitHub 存在。Copilot 引用 repo、文档、README。
5. **Microsoft Learn / 文档**：相关时贡献到 Microsoft Learn 或符合微软文档标准。
6. **Bing Places for Business**：等同 GBP 的本地搜索。完整字段。
7. **清晰 meta description**：Bing/Copilot 比 Google 更看重 meta description。每页写吸引、含关键词的。
8. **社交信号**：Bing 历来更看重社交信号（分享、赞、互动）。维护活跃社交存在。
9. **精确匹配关键词**：Bing 算法对关键词匹配更字面。在标题、标题、正文含精确目标短语。
10. **快加载**：Copilot 去优先级慢页。目标 < 2 秒加载。优化图片、压缩、最小化阻塞渲染。

#### 9.6.3 评分细则（满分 100）

| 标准 | 分值 | 评分方法 |
|---|---|---|
| Bing Webmaster Tools 验证 + sitemap | 15 | 验证 15；部分 5；无 0 |
| **IndexNow 协议实施** | **15** | 活跃 15；无 0 |
| Bing 索引覆盖 | 10 | 完整 10；部分 5；差 0 |
| LinkedIn 公司页（完整） | 10 | 完整 10；基础 5；无 0 |
| GitHub 存在（如适用） | 5 | 活跃 5；不适用 N/A |
| Meta description 优化 | 10 | 全部关键页 10；部分 5；缺 0 |
| 社交媒体互动信号 | 10 | 活跃互动 10；存在 5；无 0 |
| 精确匹配关键词在标题/标题 | 10 | 良好优化 10；部分 5；未 0 |
| 页加载 < 2 秒 | 10 | <2s 10；<4s 5；>4s 0 |
| Bing Places 配置（本地） | 5 | 完整 5；非本地 N/A |

### 9.7 跨平台协同 vs 单平台快赢

#### 9.7.1 多平台协同动作（一次做、多个平台受益）

| 动作 | 受益平台 |
|---|---|
| Wikipedia + Wikidata 实体 | ChatGPT、Perplexity、Gemini |
| 完整 Organization sameAs | 所有 5 个 |
| YouTube 频道 + 视频 | Gemini、ChatGPT、Perplexity |
| 答案前置段 + 问句标题 | AIO、ChatGPT、Perplexity |
| robots.txt 全 Allow + Content-Signal | 所有 5 个 |
| 综合 Schema.org（Org + sameAs + Article + Person） | 所有 5 个 |
| 快加载 + SSR | 所有 5 个 |
| 作者页 + 资质 | AIO、Gemini、ChatGPT |
| 定期更新可见日期 | 所有 5 个 |

#### 9.7.2 单平台快赢

| 动作 | 平台 |
|---|---|
| 注册 Bing Webmaster Tools + IndexNow | Copilot |
| GBP 完整优化 | Gemini |
| 在 r/相关 subreddit 持续 6+ 个月真实参与 | Perplexity |
| 给老内容加 dateModified | AIO（Google 关心新鲜） |
| Crunchbase 完整画像 | ChatGPT |
| 创始人 LinkedIn thought leadership | Copilot |
| Google Scholar 作者页（学术站） | Gemini |
| Apple App Store / Google Play 优化（应用） | Gemini + ChatGPT |

#### 9.7.3 跨平台优先级矩阵（决策用）

| 优先级 | Google AIO | ChatGPT | Perplexity | Gemini | Copilot |
|---|---|---|---|---|---|
| #1 | top-10 排名 | Wikipedia | Reddit 存在 | YouTube | IndexNow |
| #2 | Q&A 结构 | 实体图 | 原创研究 | Knowledge Panel | Bing WMT |
| #3 | 表格/列表 | Bing SEO | 新鲜度 | Schema.org | LinkedIn |
| #4 | Featured Snippet | Reddit | 社区论坛 | GBP | Meta description |

### 9.8 平台分级

| 平台得分 | 状态 |
|---|---|
| 70+ | Strong |
| 40–69 | Moderate |
| 0–39 | Weak |

**Platform 总分 = 5 个平台分的平均**

---

