# 新时代 GEO + SEO 方法论（完全展开版）

> 一份从 `geo-seo-claude` 项目提炼出的、可直接用于教学和实操的完整方法论文档。
> 不绑定任何工具形式，只讲技术、方法、阈值、判断标准、对照例子。
>
> **目录**
> 0. 一句话定位
> 1. 世界观：为什么 GEO 是一个独立的方法论
> 2. 6 维总分框架
> 3. 商业类型识别（前置工作）
> 4. 维度一：AI 可引用性（Citability，25%）
> 5. 维度二：品牌权威信号（Brand Authority，20%）
> 6. 维度三：内容质量与 E-E-A-T（20%）
> 7. 维度四：技术地基（Technical，15%）
> 8. 维度五：结构化数据（Schema，10%）
> 9. 维度六：平台差异化优化（Platform，10%）
> 10. llms.txt 详解（新基础设施）
> 11. 完整审计编排流程
> 12. 完整案例：electron-srl.com 从 28 → 86 分
> 13. 30 / 90 / 365 天落地路线图
> 14. 教学补充：误区与边界
> 15. 商业化路径：GEO 服务定价与流程
> 16. 关键术语速查表
> 17. 参考资料与数据来源

---

## 0. 一句话定位

**GEO（Generative Engine Optimization，生成式引擎优化）是把内容做成"AI 系统愿意整段引用、并且能在大模型的实体图谱里被识别为同一个实体"的工程。**

它和传统 SEO 的关系是：**GEO-first, SEO-supported**——SEO 还在，但只是 GEO 的子集。一切传统 SEO 操作必须重新审视一个问题：「这件事是为了让 Google 排到第一页（→ 用户点进来），还是为了让 ChatGPT/Perplexity/Gemini/AIO 把我整段抄进它的回答里（→ 用户根本不点）」。

如果答案还是前者，你做的就是上一个时代的 SEO。

---

## 1. 世界观：为什么 GEO 是一个独立的方法论

### 1.1 这是一场流量底层迁移，不是技术升级

| 指标 | 数据 | 出处 |
|---|---|---|
| GEO 服务市场（2025） | $850M–$886M | Yahoo Finance / Superlines |
| GEO 市场预测（2031） | $7.3B（CAGR 34%） | 行业分析师 |
| AI 引荐流量增长 | +527%（2025 年 1–5 月） | SparkToro |
| AI 流量转化率 vs 传统自然搜索 | **4.4 倍**更高 | 行业数据 |
| Google AI Overviews 月活 | 15 亿人 / 200+ 国家 | Google |
| ChatGPT 周活用户 | 9 亿+ | OpenAI |
| Perplexity 月查询量 | 5 亿+ | Perplexity |
| Gartner 预测 2028 自然搜索流量 | **下降 50%** | Gartner |
| 投入 GEO 的营销人 | 仅 23% | 行业调查 |
| 品牌提及 vs 反向链接对 AI 引用相关性 | **3 倍**更强 | Ahrefs Dec 2025（75K 品牌） |
| YouTube 提及与 AI 引用相关系数 | 0.737（最强） | Ahrefs Dec 2025 |
| 域名权重（DR）与 AI 引用相关系数 | 0.266（弱） | Ahrefs Dec 2025 |

**关键判断**：传统 SEO 做的是「页面 → 排名 → 点击」，GEO 做的是「段落 → 抽取 → 引用」。中间环节完全不同，需要的工程也完全不同。

### 1.2 GEO 时代的 GEO Score 来自哪里——量化研究证据

Princeton、Georgia Tech、IIT Delhi 在 2024 年联合发表的 GEO 论文是这个领域的奠基性研究。它把"如何让内容更可能被 AI 引用"从直觉变成了**可测量的工程问题**——

| 优化手段 | AI 引用提升 | 出处 |
|---|---|---|
| 总体 GEO 优化 | **30%–115%** AI 回答可见度提升 | Princeton/Georgia Tech/IIT Delhi 2024 |
| 段落最优长度 134–167 词 | 显著提升被抽取概率 | Bortolato 2025（AIO 段落分析） |
| 加入定义模式（"X is..."） | **2.1×** 引用率 | Georgia Tech 2024 |
| 加入具体统计数据 | **+40%** 引用率 | Princeton GEO 2024 |
| 加入权威人物引语 | **+115%**（特定类别） | IIT Delhi 2024 |
| 流畅度优化 | **+30%** 全查询类型可见度 | Princeton 2024 |
| 加入来源引用 | Perplexity / ChatGPT 引用 **+20–25%** | Princeton 2024 |

**这意味着——GEO 不是玄学，是可以按 checklist 操作的工程。**

### 1.3 GEO 与传统 SEO 的 6 个根本差异

| 维度 | 传统 SEO | GEO |
|---|---|---|
| **优化粒度** | 页面 / 站点 | 段落 / 实体 |
| **核心动作** | 关键词布局、内链、外链 | 结构化答案块、实体绑定（sameAs）、品牌共识 |
| **获胜标准** | 排进前 3、获得点击 | 被整段抄进 AI 回答、被列为引用源 |
| **成功信号** | DR / PA / 排名 | Wikipedia 词条、YouTube 讨论、Reddit 提及 |
| **页面渲染要求** | Googlebot 会执行 JS（有限） | GPTBot/ClaudeBot/PerplexityBot **不执行 JS**，必须 SSR |
| **频率** | 月度审计 + 持续内链 | 月度审计 + **跨平台实体维护**（Wikipedia、YouTube、Reddit） |

### 1.4 一个范式转移：从「关键词」到「实体」到「段落」

- **关键词时代**（2000–2015）：把 keyword 塞对位置，Google 排名上升。SEO 行业在这个阶段建立。
- **实体时代**（2015–2023，Hummingbird/RankBrain/BERT/MUM 之后）：Google 已经在做实体图谱（Knowledge Graph），但权重还在传统页面层。"语义搜索"成为关键词。
- **段落时代**（2023+ AI 搜索时代）：用户不看 SERP，看的是 AI 综合后的一段话。AI 模型会从一堆候选源里**逐段抽取**最适合作为回答的内容。

**GEO 的全部技术工作 = 把网站调成"段落容易被抽 + 实体容易被识别 + 品牌容易被信任"。**

### 1.5 5 个 AI 平台的引用源画像（关键认知）

不同 AI 平台用不同的索引和不同的源偏好。**只有 11% 的域名同时被 ChatGPT 和 Google AIO 引用**——意味着不存在"一招通杀"的 GEO 策略。

| AI 平台 | 索引基础 | 顶级引用源 | 每次回答引用源数 |
|---|---|---|---|
| Google AI Overviews | Google 索引 | top 10 自然搜索 + 答案块 + 表格 | 单一答案源 + 引用 |
| ChatGPT 搜索 | Bing 索引 + OAI-SearchBot | **Wikipedia 47.9%** / Reddit 11.3% / YouTube / 主流媒体 | 2–4 源 |
| Perplexity AI | 自家 PerplexityBot + 搜索 API | **Reddit 46.7%** / Wikipedia / YouTube / 主流出版 | **5–15 源** |
| Google Gemini | Google 全生态 + KG 直读 | YouTube / Knowledge Graph / GBP / Google Scholar | 多源 + 多模态 |
| Bing Copilot | Bing 索引 + 微软生态 | LinkedIn / GitHub / Microsoft Learn / IndexNow | 3–5 源（更聚焦） |

**含义**：
- 只优化 SEO？只能拿到 AIO，丢掉 89% 的其它 AI 流量。
- 没 Wikipedia？ChatGPT 引用池里 47.9% 与你无关。
- 没 Reddit 真实存在？Perplexity 引用池里 46.7% 与你无关。
- 没 YouTube？Gemini 几乎拿不到。
- 没 LinkedIn / IndexNow？Copilot 几乎不会引用。

---

## 2. 6 维总分框架

GEO 总分（0–100）= 6 个独立维度的加权和。每个维度由不同信号驱动，**互相不能替代**——这是这套方法论最重要的一句话。

### 2.1 权重表

| 维度 | 权重 | 优化对象 | 评估方式 |
|---|---|---|---|
| 1. AI 可引用性（Citability & Visibility） | **25%** | 段落、AI 爬虫访问、llms.txt | 半确定性算法 |
| 2. 品牌权威信号（Brand Authority） | **20%** | Wikipedia / Reddit / YouTube / LinkedIn / 行业平台 | 跨平台扫描 |
| 3. 内容质量与 E-E-A-T | **20%** | 经验、专业、权威、可信 | 评估型判断 |
| 4. 技术地基（Technical） | **15%** | SSR、robots.txt、安全头、CWV | 静态分析 |
| 5. 结构化数据（Schema） | **10%** | JSON-LD、sameAs、speakable | 解析+校验 |
| 6. 平台差异化优化（Platform） | **10%** | AIO / ChatGPT / Perplexity / Gemini / Copilot | 平台画像匹配 |

### 2.2 合成公式

```
GEO_Score = Citability × 0.25
          + Brand      × 0.20
          + EEAT       × 0.20
          + Technical  × 0.15
          + Schema     × 0.10
          + Platform   × 0.10
```

伪代码：

```python
weights = {
    "citability": 0.25,
    "brand":      0.20,
    "eeat":       0.20,
    "technical":  0.15,
    "schema":     0.10,
    "platform":   0.10,
}

geo_score = sum(sub_scores[k] * w for k, w in weights.items())
# geo_score ∈ [0, 100]
```

### 2.3 5 档分级解读

| 分段 | 评级 | 商业含义 |
|---|---|---|
| 90–100 | Excellent（卓越） | 极有可能被 AI 系统引用；在领域里属顶尖 |
| 75–89 | Good（良好） | 基础扎实，仍有可优化空间 |
| 60–74 | Fair（一般） | 有部分曝光，但有显著缺口 |
| 40–59 | Poor（差） | 信号微弱，AI 系统难以引用 |
| 0–39 | Critical（严重） | 对 AI 系统几乎不可见 |

### 2.4 权重背后的判断逻辑（深度解释）

**为什么 Citability 25% 最高？**
因为 AI 系统**直接消费的对象**就是段落本身。其它一切（爬虫访问、品牌、技术、schema、平台）都是"让 AI 看到段落"的前置条件。如果段落本身不可引用，前置条件做得再好也没用。

**为什么 Brand 和 EEAT 各 20%（合计 40%）？**
AI 在生成回答时会做"信任筛选"——它需要"敢"引用一个源。被引用的本质是被信任。Brand 解决"AI 知不知道你是谁"，EEAT 解决"AI 信不信你说的"。这两块加起来 40%，反映了**信任比技巧更重要**。

**为什么 Technical 15%？**
地基。坏的地基让前面三块**全归零**。典型例子：客户端渲染单页应用（CSR SPA）——AI 爬虫不执行 JS，看到的是空 HTML，前面段落写得再好都白搭。Technical 不是高分项，是**及格线**——拿不到 80 分以上等于其它都白做。

**为什么 Schema 10%、Platform 10%？**
这两块都是"杠杆性的信号增强"——成本低但有上限。Schema 帮助 AI 识别实体，Platform 让你跨平台多吃几口。两块共占 20%，是从 60 分上 80 分的关键。

**为什么不是平均分布？**
平均分布等于不分主次。这套权重的核心判断是：**做对的事，比做更多的事重要。**

### 2.5 caveat：什么是这套分数能解决的，什么不能

**能解决的**：
- 系统性诊断网站当前在 AI 时代的可见度
- 给出一份按 ROI 排序的优化清单
- 量化对比月度变化（delta tracking）
- 给客户做提案 / 议价的信任锚点

**不能解决的**：
- 不能保证"做了 X 就一定被 AI 引用"——AI 行为还受训练数据、查询措辞、竞品内容影响
- 不能告诉你某个具体查询下你的内容会不会出现
- 不能验证 schema 内容真实性（只能验证语法）
- 不能验证 Wikipedia 信息准确性

**确定性 vs LLM 评估**：

| 类别 | 性质 | 同样输入是否同样输出 |
|---|---|---|
| Citability（脚本化的段落分） | 确定性 | 是 |
| llms.txt 校验 | 确定性 | 是 |
| 技术（部分） | 半确定性 | 大部分是 |
| Brand / EEAT / Schema / Platform | LLM 评估 | 两次结果可能略有差异 |

教课时要明确说出**哪些数字是机器算的，哪些是评估的**——这是专业度的体现。

---

## 3. 商业类型识别（前置工作）

> 不识别商业类型就开始做 GEO，等于不分病人就开药。

### 3.1 6 种商业类型与识别信号

| 类型 | 识别信号 |
|---|---|
| **SaaS** | 定价页 / "Sign up" / "Free trial" CTA / app.domain.com 子域 / 功能对比表 / 集成页 / API 文档 / dashboard 截图 |
| **本地服务（Local）** | 首页有物理地址 / Google Maps embed / "Near me" 内容 / LocalBusiness schema / 服务区页面 / 电话号码 |
| **电商（E-commerce）** | 商品列表 / 购物车 / Product schema / 类目页 / 价格 / "Add to cart" / SKU 标识 |
| **媒体出版（Publisher）** | 博客重导航 / Article schema / 作者页 / 日期归档 / RSS / 高内容量 |
| **代理/服务商（Agency）** | 案例集 / 作品集 / "Our Work" / 团队页 / 客户 logo 墙 / 服务描述 |
| **混合型（Hybrid）** | 上述信号组合——按主导模式分类 |

### 3.2 不同类型的 GEO 差异化策略

**SaaS 类**——
- 额外加权：功能对比表（极高 citability）、集成页、文档质量
- 重点 schema：`SoftwareApplication`、`FAQPage`、`HowTo`
- Citability 强项：功能对比可以直接被 AI 抽出来当回答
- 关键平台：G2、Capterra、Product Hunt（评分被 ChatGPT 大量引用）；GitHub（开发者品牌）
- Citability 风险：纯特性堆砌没人爱看，需要把"我们做什么"改成"用户问什么"

**本地服务类**——
- 额外加权：NAP（Name/Address/Phone）一致性、Google Business Profile、本地 schema
- 重点 schema：`LocalBusiness`、`GeoCoordinates`、`OpeningHoursSpecification`、`hasOfferCatalog`
- 关键平台：Google Business Profile（Gemini 直读）、Yelp、BBB、Google Maps
- Citability 强项："Where can I find X near me"型查询
- Citability 风险：内容容易做成纯介绍页，要加 Q&A 区块

**电商类**——
- 额外加权：商品描述 citability、对比内容、购买指南
- 重点 schema：`Product`（含 `offers`、`aggregateRating`、`shippingDetails`、`hasMerchantReturnPolicy`）、`BreadcrumbList`
- 关键平台：Google Merchant Center（Gemini 直接拉取产品数据）、Trustpilot
- Citability 强项："best X for Y"对比内容、产品规格表
- Citability 风险：单纯产品页几乎不可引用，要做"购买决策类"内容

**媒体出版类**——
- 额外加权：文章质量、作者资质、来源引用规范
- 重点 schema：`Article`/`NewsArticle`/`BlogPosting`、`Person`（作者）、`ClaimReview`、`speakable`
- 关键平台：Google News、Wikipedia 引用（被 Wikipedia 引用 = 进 AI 训练池的捷径）
- Citability 强项：长篇研究、原创数据、专家署名
- Citability 风险：作者必须 Person schema，否则 EEAT 拉胯

**代理/服务商类**——
- 额外加权：案例集 citability、专业度展示、思想领导力
- 重点 schema：`Organization`、`Service`、`Person`（团队）、`Review`
- 关键平台：LinkedIn（B2B）、行业奖项目录、Crunchbase
- Citability 强项：含具体数据的真实案例
- Citability 风险：泛泛的"我们能做 X"营销文，无实战案例

**混合型**——按主导业务模式归类，但要在多个 schema 上都覆盖。比如又是 SaaS 又是媒体的（如 HubSpot），需要同时部署 SoftwareApplication + Article。

### 3.3 课程教学建议

**做案例分析时第一步永远是分类**——拿到一个站，先问"这是什么类型"。所有后续诊断都建立在这个分类之上。同样的"无 Wikipedia 词条"问题，对本地理发店和对 SaaS 公司是完全不同的优先级。

---

## 4. 维度一：AI 可引用性（Citability，25%）

> 这是整个体系的核心，也是最反直觉、最值得在课里浓墨重彩讲的部分。"段落级 SEO" 概念的发源地。

### 4.1 核心洞察：AI 引用是有结构特征的

普林斯顿、Georgia Tech、IIT Delhi 在 2024 年的联合研究发现：**AI 系统优先抽取并引用的段落具有可预测的结构特征**——

- **长度 134–167 词**（中位数极窄的最优区，Bortolato 2025 对 AIO 段落的分析）
- **自包含**（脱离上下文也能读懂）
- **事实密集**（具体数字、日期、实体名）
- **答案前置**（前 1–2 句就给出答案）

按这个结构改写后，GEO 优化的内容在 AI 回答中的曝光提升 **30%–115%**。

**这是 GEO 的核心技术红利**——传统 SEO 文案是为"keyword density + 用户停留"优化，GEO 是为**抽取性（extractability）** 优化。两者不是同一份内容。

### 4.2 段落级 SEO 是什么意思——本质重定位

传统 SEO 文案的核心问题是：**"这段话能让用户读下去吗？"**
GEO 文案的核心问题是：**"这段话能不能被整段切下来当 AI 回答？"**

这两个问题导致两种完全不同的写作风格：

| 维度 | 传统 SEO 文案 | GEO 文案 |
|---|---|---|
| 开头 | 钩子（hook）/ 故事 / 共鸣 | 直接定义或答案 |
| 段长 | 不限，长短交错以维持节奏 | 134–167 词最优，120–200 可接受 |
| 主语 | 可以用"它/这个"等代词，假设读者读过前文 | 每段必须显式命名主语 |
| 数据 | 锦上添花，不是必需 | 几乎每段都要有具体数字或专有名 |
| 标题 | 吸引点击的好奇式（"你不知道的 5 件事"） | 直接对应查询的问句式（"What is X?"） |
| 结尾 | 引导下一步行动 | 段落本身完整，无需"接下文" |

**给学员的关键判断练习**：把任意一段从你的网站上拷贝出来，扔进一个空白文档。问自己——
- 不看上下文，能看懂这段在讲什么吗？
- 这段里有具体的数字吗？
- 这段第一句就回答了一个问题吗？

如果三个答案有一个是"否"，这段就拿不到 AI 引用。

### 4.3 段落级 5 维评分细则（确定性算法）

每段独立打分，0–100 分。算法实现见 `scripts/citability_scorer.py`，所有阈值都来自这份代码。

```
段落分 = 答案块质量(30) + 自包含(25) + 结构可读性(20) + 统计密度(15) + 独特性(10)
页面分 = 页面上"得分前 5 段"的平均分（不到 5 段就用全部）
```

#### 4.3.1 答案块质量（Answer Block Quality，最高 30 分）

测量"这段是否有清晰、可被 AI 直接搬走的答案"。

**信号 1：定义模式**（+15）

5 个正则全列：

```regex
\b\w+\s+is\s+(?:a|an|the)\s     →  "X is a/an/the …"
\b\w+\s+refers?\s+to\s            →  "X refers to …"
\b\w+\s+means?\s                  →  "X means …"
\b\w+\s+(?:can be |are )?defined\s+as\s   →  "X is/can be defined as …"
\bin\s+(?:simple|other)\s+(?:terms|words)\s*,    →  "In simple/other terms,"
```

只要任一条命中即 +15。中文写作没有 `is/refers to` 但同等位置可以用："X 是…"、"X 指的是…"、"X 即…"、"换句话说…"

**信号 2：答案前置**（+15）

检查段落前 60 词是否包含以下任一模式：

```regex
\b(?:is|are|was|were|means?|refers?)\b   →  系动词
\d+%                                       →  百分比
\$[\d,]+                                   →  金额
\d+\s+(?:million|billion|thousand)         →  量级数字
```

任一命中即 +15。本质是判断"AI 抽前 60 词当回答时，能不能拿到核心信息"。

**信号 3：问句式标题**（+10）

如果该段的 H2/H3 标题以 `?` 结尾（`What is X?` / `How does X work?`），加 10 分。

**信号 4：短清晰句占比**（最高 +10）

```
clarity_ratio = (5–25 词的句子数) / (总句数)
score = int(clarity_ratio × 10)
```

平均句长太长（>25 词）AI 抽出来读不通，太短（<5 词）信息密度不够。

**信号 5：可引用断言**（+10）

```regex
according to|research shows|studies? (?:show|indicate|suggest|found)|data (?:shows|indicates|suggests)
```

任一命中即 +10。Princeton 2024 论文证明带"权威引语"的段落引用率提升 **115%**（特定类别）。

**最高 30 分封顶。**

#### 4.3.2 自包含（Self-Containment，最高 25 分）

测量"段落能否脱离上下文独立使用"。

**信号 1：词数最优区**

| 词数 | 加分 | 依据 |
|---|---|---|
| 134–167 词 | **+10**（黄金区） | Bortolato 2025 AIO 段落分析 |
| 100–200 词 | +7 | 次优 |
| 80–250 词 | +4 | 可接受 |
| 30–80 词 或 250–400 词 | +2 | 边缘 |
| <30 词 或 >400 词 | 0 | 太短或太长 |

**为什么是 134–167？**——这是对实际被 AIO 抽取的段落做长度分布分析后的中位数极窄区。短了信息不够，长了 AI 会嫌冗余切掉。

**信号 2：代词密度低**

```
pronoun_count = re.findall(r'\b(?:it|they|them|their|this|that|these|those|he|she|his|her)\b', text)
pronoun_ratio = pronoun_count / word_count
```

| 代词比 | 加分 |
|---|---|
| < 2% | +8 |
| < 4% | +5 |
| < 6% | +3 |
| ≥ 6% | 0 |

代词越多 = 越依赖前文 = 抽出来越无意义。中文里对应的是"它/这个/这一/此/这些"等指代词。

**信号 3：专有名词数**

```
proper_nouns = re.findall(r'\b[A-Z][a-z]+(?:\s+[A-Z][a-z]+)*\b', text)
```

| 专有名词数 | 加分 |
|---|---|
| ≥ 3 个 | +7 |
| ≥ 1 个 | +4 |
| 0 个 | 0 |

专有名词（公司/产品/人/地名）让段落"锚定"在具体语境里，AI 才能放心引用。

#### 4.3.3 结构可读性（Structural Readability，最高 20 分）

测量"段落的物理结构是否便于解析"。

| 信号 | 加分规则 |
|---|---|
| 平均句长 10–20 词 | +8（10–20）/ +5（8–25）/ +2（其它） |
| 列表语词出现 | +4（"first/second/third/finally/additionally/moreover/furthermore"） |
| 数字编号或步骤词 | +4（`1. 2. 3.` 或 "step 1 / tip 2 / point 3"） |
| 段落分隔符（换行） | +4 |

#### 4.3.4 统计密度（Statistical Density，最高 15 分）

| 信号 | 加分（含上限） |
|---|---|
| 百分比（`\d+%`） | 每个 +3，上限 +6 |
| 金额（`$XXX`） | 每个 +3，上限 +5 |
| 带单位的数字（"users / customers / pages / sites / companies / businesses / people / percent / times"） | 每个 +2，上限 +4 |
| 年份引用（2018–2026） | +2 |
| 命名来源（"according to / Gartner / Forrester / McKinsey / Harvard / Stanford / MIT / Google / Microsoft / OpenAI / Anthropic"） | +2 |

**Princeton 2024 论文证明**：仅仅在内容里加入具体统计就能让 AI 引用率 +40%。这是 GEO 中**最便宜的提升手段**——一个数字代替"很多/许多/大量"，引用率立涨。

**什么算统计 vs 什么不算**（教学要重点强调）：

✅ 算：
- "73% of marketers report..."
- "The average cost is $4,500 per month"
- "Implementation takes 6–8 weeks on average"
- "According to the 2025 HubSpot State of Marketing Report..."
- "The platform integrates with 340+ tools"
- "40% faster than the industry average"

❌ 不算：
- "Many companies use..."（vague）
- "A significant percentage..."（vague）
- "Studies show that..."（无具名来源）
- "Experts agree..."（无具名专家）

#### 4.3.5 独特性（Uniqueness Signals，最高 10 分）

| 信号 | 加分 |
|---|---|
| 原创研究语 | +5（"our research/our study/our data/our analysis/our survey/our findings/we found/we discovered/we analyzed/we surveyed/we measured"） |
| 案例/示例语 | +3（"case study/for example/for instance/in practice/real-world/hands-on"） |
| 具体工具/产品提及 | +2（"using/with/via/through [大写专名]"） |

### 4.4 段落级 5 档评分（A/B/C/D/F）

5 维加起来后的分数线，直接对应"AI 引用可能性"：

| 总分 | Grade | 标签 | 含义 |
|---|---|---|---|
| ≥ 80 | A | Highly Citable | 高度可引用——AI 大概率会原段引用 |
| 65–79 | B | Good Citability | 良好——AI 经常引用 |
| 50–64 | C | Moderate Citability | 中等——偶尔被引用 |
| 35–49 | D | Low Citability | 低——很少被引用 |
| < 35 | F | Poor Citability | 几乎不可引用 |

### 4.5 5 档级别的"长什么样"详细描述

教学时这 5 档要让学员能口头描述出来。

**Answer Block Quality 5 档**：

| 分数 | 长什么样 |
|---|---|
| 90–100 | 每个主要段落都用 1–2 句直接答案开头。用"X is..."或"X refers to..."模式。每段前 40–60 词能独立成完整答案 |
| 70–89 | 大部分段落有清晰答案开头。一些定义模式。答案能识别但需要少量上下文 |
| 50–69 | 一些段落有答案样式开头，但很多答案被埋在段落中间或末尾。少数明确定义 |
| 30–49 | 答案普遍被埋在长段落里。无一致定义模式。叙述驱动而非答案驱动 |
| 0–29 | 完全没有可识别的答案块。纯叙述、对话或碎片化。AI 抽不出任何引用 |

**Self-Containment 5 档**：

| 分数 | 长什么样 |
|---|---|
| 90–100 | 80%+ 段落完全自包含。每段显式命名主语。零代词依赖。每段含具体事实 |
| 70–89 | 60–79% 段落自包含。多数段落命名主语。偶尔代词需要上下文 |
| 50–69 | 40–59% 段落自包含。主语和代词混用。一些段落需要读前文 |
| 30–49 | 20–39% 段落自包含。重度代词依赖。多数段落需要上下文 |
| 0–29 | <20% 自包含。整篇连续叙述，抽出任何一段都失去意义 |

**Structural Readability 5 档**：

| 分数 | 长什么样 |
|---|---|
| 90–100 | 干净的 H1>H2>H3 层级。问句式标题用于信息型内容。短段（2–4 句）。比较用表格。流程用有序列表。功能/选项用无序列表 |
| 70–89 | 标题层级好，少数跨级。一些问句标题。多数短段。有部分表格和列表 |
| 50–69 | 有标题层级但不一致。少问句标题。长短段混合。表格列表少 |
| 30–49 | 标题结构最少。无问句标题。长段为主。罕见表格列表 |
| 0–29 | 无标题结构或严重断层。墙体段落。无表格列表 |

**Statistical Density 5 档**：

| 分数 | 长什么样 |
|---|---|
| 90–100 | 每 500 词 5+ 具体统计。所有断言有具名来源或日期。用精确数字（不是"许多""几个"）。含百分比、金额、时间段、具名研究 |
| 70–89 | 每 500 词 3–4 统计。多数断言有来源。多数具体数字偶有模糊量词 |
| 50–69 | 每 500 词 1–2 统计。一些断言有来源。具体数字与模糊数字混合 |
| 30–49 | 每 500 词 <1 统计。少数有来源断言。模糊量词为主 |
| 0–29 | 零统计。零具名来源。所有量词模糊（"many""most""a lot"） |

**Uniqueness & Original Data 5 档**：

| 分数 | 长什么样 |
|---|---|
| 90–100 | 含一手研究、专属数据、原创调查或独有数据集。提供其它任何页面找不到的分析或洞察。清晰的方法论描述 |
| 70–89 | 含一些原创洞察或对现存数据的独特分析。提供独特视角与原创案例 |
| 50–69 | 主要综合现存信息但加一些独特评论或例子 |
| 30–49 | 大部分是衍生内容，重述常识，原创贡献最小 |
| 0–29 | 完全衍生。所有信息（常常一字不差）都能在更高权威源找到 |

### 4.6 自包含 5 条 checklist（教学口诀）

**给学员的口诀**：把段落拷出来后逐条问——

1. 这段是否**显式命名主语**（不是 "it"、"this"、"they"）？
2. 是否**仅读这段**就能理解主要观点？
3. 段内**至少 1 个具体事实**（统计/具名实体）？
4. 段长是否在 **50–200 词的最优抽取区**？
5. 是否**避开了用 "But"、"However"、"And" 等连词开头**（暗示需要前文）？

5 条全过 = 段落自包含 ≥ 80。

### 4.7 高低 citability 段落对照（5 组覆盖不同场景）

#### 对照组 1：技术解释类

**A 级（约 75 分）**：

> Content delivery networks (CDNs) are distributed server systems that cache and serve web content from locations geographically close to end users. A CDN reduces latency by 50–70% on average by serving assets from edge servers rather than a single origin server. The three largest CDN providers as of 2025 are Cloudflare (serving approximately 20% of all websites), Amazon CloudFront, and Akamai Technologies.

✅ 58 词（在 100–200 加分区）／定义模式 ✅／答案前置 ✅／3 个具体数据 ✅／3 个专有名词 ✅／零代词 ✅

**F 级（约 15 分）**：

> If you've ever wondered why some websites load faster than others, the answer might surprise you. There's this amazing technology that has been around for a while now. It's changed the way we think about web performance. Let me explain how it works and why you should care about it for your business.

❌ 不知道讲什么（无主语）❌ 零数字 ❌ 全代词 ❌ 钩子开头无答案

#### 对照组 2：B2B SaaS 产品介绍

**A 级**：

> Notion is a workspace tool that combines notes, databases, project management, and wikis into a single platform. As of January 2026, Notion serves over 30 million users across 100+ countries, with pricing starting at $8 per user/month for the Plus plan. According to G2 reviews, Notion ranks #2 in the "team collaboration" category with a 4.7/5 average from 5,800+ reviews.

**F 级**：

> Our amazing platform is designed to help your team work smarter, not harder. With our innovative approach, you'll be able to streamline your workflows and unlock new levels of productivity. Whether you're a small team or a large enterprise, we've got you covered with flexible solutions that scale with your needs.

#### 对照组 3：本地服务

**A 级**：

> Joe's Plumbing is a residential plumbing service in Austin, TX, founded in 2003 by Joe Martinez (master plumber, license #M-12345). The company services a 25-mile radius around downtown Austin, with average response times of 90 minutes for emergency calls. Standard service rates as of 2025 are $125/hour with a $75 trip fee, and the business holds a 4.9/5 rating from 412 verified Google reviews.

**F 级**：

> Looking for the best plumber in your area? You've come to the right place! Our experienced team has been serving the community for years and we pride ourselves on quality work and excellent customer service. Give us a call today and let us show you why our customers keep coming back!

#### 对照组 4：电商产品页

**A 级**：

> The Patagonia Down Sweater is a 4.2-ounce hooded down jacket filled with 800-fill-power Advanced Global Traceable Down. The shell uses 100% recycled polyester ripstop with a DWR finish that retains warmth in temperatures down to 25°F (-4°C). Released in 2010 and updated in 2023 with NetPlus recycled fishing net liner, the jacket retails for $279 and has a 4.6/5 rating from 1,847 customer reviews on patagonia.com.

**F 级**：

> Stay warm and stylish with our premium down jacket! Made from high-quality materials, this jacket is perfect for any cold weather adventure. Whether you're hiking in the mountains or running errands around town, you'll love the cozy comfort and modern design. Available in multiple colors and sizes!

#### 对照组 5：媒体分析文章

**A 级**：

> AI-referred traffic grew by 527% between January and May 2025 according to SparkToro's analysis of 3,200 websites. ChatGPT alone drove 42% of this referred traffic, followed by Perplexity (28%), Gemini (18%), and Claude (12%). Industry surveys conducted by HubSpot in late 2025 found that AI-driven sessions convert at 4.4× the rate of organic search sessions, primarily because AI users arrive with higher purchase intent—they have already filtered options through the AI's response.

**F 级**：

> AI search is changing the digital marketing landscape in significant ways. As more people start using AI-powered search engines, businesses need to adapt their strategies. Traffic patterns are shifting, and savvy marketers are taking notice. The implications for the future are substantial.

### 4.8 实操 6 条强约束（写作时直接用）

1. **每个 H2 下的第一段就给答案**——而且答案能整段切出来当回答。
2. **段落控制在 134–167 词**——这是黄金区间，可以用编辑器字数统计实时反馈。
3. **段落起手就出现主语全名**——不要用 "It"、"They"、"This" 开头。中文里不要用"它/这个"开头。
4. **每段至少塞 1 个可验证的具体数字**——百分比 / 金额 / 年份 / 数量 / 评分。
5. **H2 标题尽量写成问句**——`What is X?` / `How does X work?` / `Why is X important?` 直接对齐 AI 查询的常见问法。
6. **关键词第一次出现时加粗**——这是给 AI 的"实体识别加速器"。

### 4.9 改写训练（before / after）

**Before**（原文，得分约 30）：

> Many businesses today are wondering whether they should invest in AI search optimization. It's a complex topic with various considerations. Some experts say it's the future, while others remain skeptical. There are different approaches you can take depending on your situation. The key is to understand what works best for your specific needs and goals.

**改写要求**：长度控制在 134–167 词；答案前置；至少 3 个具体数字；定义模式；专有名词。

**After**（改写后，得分约 80）：

> AI search optimization (GEO) is the practice of structuring website content so that ChatGPT, Perplexity, Google AI Overviews, and Gemini are more likely to cite it in generated answers. According to a Princeton/Georgia Tech/IIT Delhi study published in 2024, sites that apply GEO techniques see 30–115% more visibility in AI-generated responses depending on the query category. The most effective tactics are surprisingly cheap: adding specific statistics increases citation rate by 40%, using definition patterns ("X is...") increases it by 110%, and including expert quotations increases it by up to 115% for certain topics. As of 2026, only 23% of marketers have invested in GEO, while AI-referred traffic has grown 527% year-over-year and converts at 4.4× the rate of traditional organic search. The window for first-mover advantage is open, but closing fast.

✅ 158 词（黄金区）／定义模式 ✅／前 60 词含答案 ✅／6 个具体统计 ✅／7+ 专有名词 ✅／零代词依赖

**改写练习的教学价值**：
让学员**亲手把一段 30 分文案改到 75 分**，比讲一万句"段落要写好"都管用。每改一次，对 AI 引用机制的理解就深一层。

### 4.10 页面级 Citability 计算

```
页面 Citability 分 = 页面上"得分前 5 段"的平均分
                  （不到 5 段就用全部段落）
```

**为什么取前 5？**——奖励"至少有几段拿得出手"的页面，避免被一堆中等段落拖低。AI 也是只引用最好的几段，不是平均水平。

**衍生指标——Citability Coverage（教学拓展）**：
```
Coverage = 得分 ≥ 70 的段落数 / 总段落数
```
这个比例反映"页面有多少比例的段落是可引用的"。Coverage > 50% 是优质内容的基本线。

### 4.11 段落改写优先级判断

不是所有段落都该改。判断顺序：

1. **当前页面 Citability < 60，且段落本身得分 < 50** → 必改
2. **当前页面 Citability 60–80，且段落得分 < 40** → 改
3. **当前页面 Citability > 80，但单段得分 < 30** → 可改可不改（边际效益低）

**改写预期收益**：
- 单段从 30 → 70：页面分大约 +5–8
- 单段从 30 → 80：页面分大约 +8–12
- 改 5 段从 30 → 70：页面分大约 +20–30

---

## 5. 维度二：品牌权威信号（Brand Authority，20%）

> 这是整个 GEO 体系里**最反直觉、也最值钱**的一块。

### 5.1 关键发现：品牌提及打败反向链接

Ahrefs 在 2025 年 12 月发布了一份基于 **75,000 个品牌**样本的研究。它量化了不同信号与 AI 引用之间的相关系数：

| 信号 | 与 AI 引用相关性 | 在传统 SEO 中的价值 |
|---|---|---|
| **YouTube 提及** | **~0.737（最强）** | 低（不是排名因子） |
| Reddit 提及 | 高（Ahrefs 未公布精确系数） | 低 |
| Wikipedia 存在 | 高 | 中（信任信号） |
| LinkedIn 存在 | 中 | 低 |
| **域名权重 DR** | **~0.266（弱）** | 极高 |
| **反向链接数** | **~0.266（弱）** | 极高 |
| 自然搜索流量 | 中 | 极高 |

**关键洞察（让学员记住）**：
- 对 AI 时代最重要的信号（YouTube、Reddit），在传统 SEO 里几乎不重要。
- 对传统 SEO 最重要的信号（外链、DR），是 AI 时代的弱预测因子。
- **这要求一套根本不同的优化策略**——不是把 SEO 加上"AI 调料"，而是从优先级层面重新分配预算。

**一句话总结**：在 AI 时代，品牌建设的 ROI 高于链接建设约 **3 倍**。

### 5.2 关键引用比例（必须背下的数据）

| 平台 | 关键比例 | 含义 |
|---|---|---|
| ChatGPT 引用源中 Wikipedia 占比 | **47.9%** | 没 Wikipedia = 自动放弃 ChatGPT 一半引用池 |
| ChatGPT 引用源中 Reddit 占比 | 11.3% | Reddit 第二大引用源 |
| Perplexity 引用源中 Reddit 占比 | **46.7%** | 没 Reddit 真实存在 = 自动放弃 Perplexity 一半引用池 |
| Google 与 Reddit 数据授权 | $60M/年（2024 起） | Reddit 已是 Google 战略数据源 |
| Reddit 关键词追加搜索占比 | 10–15%（"X reddit" 后缀） | 用户主动找真实意见 |
| YouTube 提及与 AI 引用相关系数 | 0.737 | 最强单一信号 |

### 5.3 5 大平台权重分布

| 平台 | 权重 | 评估依据 |
|---|---|---|
| **YouTube** | 25% | 与 AI 引用最强相关 0.737 |
| **Reddit** | 25% | 第二强相关；产品推荐关键来源 |
| **Wikipedia / Wikidata** | 20% | 实体识别基础；AI 训练数据基石 |
| **LinkedIn** | 15% | 职业权威信号；B2B 关键 |
| **其它平台** | 15% | Quora / GitHub / Stack Overflow / Hacker News / 新闻 / 论坛 / 播客 |

```
Brand_Authority = YouTube×0.25 + Reddit×0.25 + Wikipedia×0.20 + LinkedIn×0.15 + Other×0.15
```

### 5.4 YouTube 详解（最高权重）

**为什么 YouTube 最重要**：

- 全球第二大搜索引擎，2.5B+ 月活
- AI 训练数据集大量纳入 YouTube 字幕、描述、元数据
- Gemini 和 AIO 直接引用 YouTube
- Perplexity / ChatGPT 都索引并引用 YouTube
- **YouTube 字幕特别有价值**——自然口语形式的品牌提及，与 AI 处理文本方式高度对齐

**评分细则（0–100）**：

| 分数 | 标准 |
|---|---|
| 90–100 | 活跃频道 10K+ 订阅，定期上传，品牌出现在 20+ 第三方视频中，YouTube 搜索行业词时品牌出现 |
| 70–89 | 活跃频道 1K+ 订阅，10–19 个第三方视频提及，部分 YouTube 搜索可见 |
| 50–69 | 频道存在有内容，5–9 个第三方视频提及，YouTube 搜索可见度有限 |
| 30–49 | 频道存在但不活跃，1–4 个第三方视频提及 |
| 10–29 | 无频道或空频道，仅 1–2 个视频提及 |
| 0–9 | 完全无 YouTube 存在 |

**6 项检查清单**：

1. **品牌频道**：是否有活跃官方频道？订阅数？视频数？上传频率？
2. **第三方视频提及**：其他 YouTuber / 频道是否提及品牌？语境是什么（评测、教程、对比）？
3. **视频描述**：行业相关视频的描述里是否出现品牌名？
4. **视频字幕**：相关视频的口语内容里是否提及品牌？（AI 索引字幕）
5. **YouTube 搜索存在**：搜 "[品牌名]" YouTube 是否有结果？正面吗？
6. **评论提及**：行业相关视频的评论里是否提及品牌？

**6 项快速建议**：

1. 创建频道并发 3–5 个核心主题的解释视频
2. 确保品牌名出现在视频标题、描述、口语中
3. 争取出现在行业相关频道的客串嘉宾位
4. 制作"对比"或"X 替代品"类视频（这些被 AI 大量引用于对比查询）
5. 加章节（chapters）和时间戳——AI 解析友好
6. 字幕用人工修正版本（YouTube 自动字幕可读性差）

### 5.5 Reddit 详解（与 YouTube 同权重）

**为什么 Reddit 重要**：

- AI 训练数据中 Reddit 占比极高（Google 2024 与 Reddit 签 $60M/年授权交易确认）
- AI 系统在产品推荐、对比、用户情绪类查询时重度依赖 Reddit
- "Reddit" 已被估计有 10–15% 的 Google 搜索用户主动追加，寻求真实意见
- Perplexity 频繁引用 Reddit 帖子作为来源（46.7%）
- ChatGPT 和 Claude 在产品/服务类问题上引用 Reddit 讨论（11.3%）

**评分细则（0–100）**：

| 分数 | 标准 |
|---|---|
| 90–100 | 在相关 subreddit 频繁被推荐，主导正面情绪，活跃官方存在，自有 subreddit 5K+ 成员，行业查询的 top 推荐 |
| 70–89 | 在相关 subreddit 定期被提及，主要正面情绪，有官方存在，多个推荐帖中出现 |
| 50–69 | 在多个相关帖中被提及，情绪混合，社区成员认识品牌名 |
| 30–49 | 偶尔提及，仅 1–2 个 subreddit，无官方存在 |
| 10–29 | 罕见提及，Reddit 上品牌大体不知名 |
| 0–9 | 无 Reddit 存在 |

**6 项检查清单**：

1. **subreddit 存在**：品牌是否在相关 subreddit 被讨论？哪些？
2. **提及量**：多少帖子提到品牌？趋势是什么（增/减）？
3. **情绪**：主要正面、负面、中性？常见赞点和抱怨是什么？
4. **官方存在**：品牌是否有官方 Reddit 账号？参与讨论？做过 AMA？
5. **推荐帖**：在 "What do you recommend for X?" 类帖子中出现吗？是 top 推荐还是陪跑？
6. **社区**：品牌有自己的 subreddit 吗？多活跃？

**6 项快速建议**：

1. 识别 3–5 个目标受众活跃的 subreddit
2. 真实参与（不要营销腔——Reddit 社区会识别并惩罚）
3. 如果适合品牌，做一次 AMA
4. 监控并响应品牌提及
5. 创建真正有用的内容，自然带出品牌专长
6. **Reddit authenticity matters — don't use marketing speak**

**反直觉警告（必讲给学员）**：
Reddit 是唯一一个"假装做"会反噬的渠道。一旦被识别为营销账号，会被踩、被禁、被在该 subreddit 拉黑——这种负面信号 AI 也会捕获。**只能真实运营，没有捷径**。这条规则不仅适用于 Reddit，也适用于所有社区类平台（Hacker News、Stack Overflow、行业论坛等）。

**一个反例可以让学员记一辈子**：某 SaaS 创始人雇人在 r/SaaS 发"我作为用户用了 X 半年"的"真实评价"，被 mod 识别后该品牌名被永久 ban，AI 系统至今引用 Reddit 时仍能看到那次事件。

### 5.6 Wikipedia / Wikidata 详解

**为什么 Wikipedia 是单点最关键**：

- 所有主流 LLM 都用 Wikipedia 训练
- AI 系统用 Wikipedia 做实体识别——"这个品牌是不是真实存在的实体"
- Wikidata（Wikipedia 的结构化数据库）提供机器可读事实，AI 用于知识图谱构建
- 有 Wikipedia 词条 = 强 notability 信号 = AI 把品牌当作权威实体

**评分细则（0–100）**：

| 分数 | 标准 |
|---|---|
| 90–100 | 详细 Wikipedia 文章（B-class+），完整 Wikidata 条目，多篇 Wikipedia 引用品牌作为来源，创始人有 Wikipedia 词条 |
| 70–89 | Wikipedia 文章存在（start-class+），Wikidata 存在，2+ 其它 Wikipedia 文章中被提及 |
| 50–69 | Wikipedia 文章存在（stub 或 start），基础 Wikidata 条目，其它文章中提及有限 |
| 30–49 | 无 Wikipedia 文章，但在其它文章中被提及或被引为来源；可能有 Wikidata |
| 10–29 | 仅在 1–2 篇 Wikipedia 文章中作为顺便提及 |
| 0–9 | 无 Wikipedia / Wikidata 存在 |

**6 项检查清单**：

1. **Wikipedia 词条**：品牌或公司是否有自己的 Wikipedia 文章？是否标记删除或质量问题？
2. **创始人页**：创始人/CEO 是否有 Wikipedia 词条？（强权威信号）
3. **被引用**：品牌官网是否被 Wikipedia 文章引为参考？
4. **Wikidata 条目**：是否有 Wikidata item（Q-number）？属性多完整？
5. **Wikipedia 提及**：在其它 Wikipedia 文章中被提及吗（行业文章、竞品页、类目页）？
6. **文章质量**：如果有 Wikipedia 文章，是 stub、start-class，还是更高质量？

**Wikipedia API 检测代码（实战教学用）**：

Web 搜索 `site:wikipedia.org` 频繁返回假阴性。**永远先用 API 直接查**：

```python
import requests
from urllib.parse import quote_plus

brand = "Your Brand Name"

# Wikipedia 检测
api_url = f"https://en.wikipedia.org/w/api.php?action=query&list=search&srsearch={quote_plus(brand)}&format=json"
r = requests.get(api_url, headers={"User-Agent": "GEO-Audit/1.0"}, timeout=15)
results = r.json().get("query", {}).get("search", [])
if results and brand.lower() in results[0].get("title", "").lower():
    title = results[0]["title"]
    print(f"WIKIPEDIA PAGE EXISTS: {title}")
    print(f"URL: https://en.wikipedia.org/wiki/{title.replace(' ', '_')}")
else:
    print("No direct Wikipedia page found")

# Wikidata 检测
wd_url = f"https://www.wikidata.org/w/api.php?action=wbsearchentities&search={quote_plus(brand)}&language=en&format=json"
r2 = requests.get(wd_url, headers={"User-Agent": "GEO-Audit/1.0"}, timeout=15)
entities = r2.json().get("search", [])
if entities:
    print(f'WIKIDATA: {entities[0].get("id", "")} — {entities[0].get("description", "")}')
```

**3 重检测方法的可靠性排序**：
1. ⭐⭐⭐ Wikipedia/Wikidata API 直查（最可靠）
2. ⭐⭐ 直接 WebFetch `https://en.wikipedia.org/wiki/[Brand_Name]`（第二可靠）
3. ⭐ 搜索 `site:wikipedia.org`（最不可靠，常假阴性）

**Wikipedia 策略（重要：不能想发就发）**：

- **不要自己写自己的 Wikipedia 页**——利益冲突，会被快速删除
- **先建立 notability**——通过 5+ 篇独立第三方权威媒体报道
- **先做 Wikidata**——无 notability 门槛，先拿到 Q-code
- **请专家写**——可雇懂 Wikipedia 的顾问（不是普通文案），让他帮你判断 notability 并起草
- **被引用为来源比拥有词条更稳**——在已有 Wikipedia 文章里把你的官网作为参考来源加进去

**正确顺序**：
```
独立媒体报道 → Wikidata 实体（Q-code）→ Wikipedia stub（如有 notability）→ 让外部编辑慢慢扩充
```

### 5.7 LinkedIn 详解

**为什么 LinkedIn 重要**：

- LinkedIn 内容越来越多被 AI 系统索引（专业/B2B 语境）
- 公司页 + 员工 thought leadership 帖子构建品牌实体信号
- AI 模型从 LinkedIn 拉公司信息、团队资质、专业权威
- LinkedIn 文章和帖子被搜索引擎和 AI 爬虫索引
- **是 Bing Copilot 的核心信号源**（LinkedIn 是微软资产）

**评分细则（0–100）**：

| 分数 | 标准 |
|---|---|
| 90–100 | 活跃公司页 10K+ 关注，领导层定期发 thought leadership，行业人士频繁提及，员工资料强 |
| 70–89 | 活跃公司页 5K+ 关注，部分员工 thought leadership，偶尔第三方提及 |
| 50–69 | 公司页存在，1K+ 关注，发帖不规律，第三方提及有限 |
| 30–49 | 公司页存在但稀疏或不活跃，关注少，无第三方提及 |
| 10–29 | 基础公司页，信息最少 |
| 0–9 | 无公司页 |

**6 项检查清单**：

1. **公司页**：品牌有 LinkedIn 公司页吗？关注数？发帖频率？
2. **员工 thought leadership**：员工（尤其领导层）发提及品牌的 thought leadership 吗？
3. **公司被提及**：非员工（行业分析师、客户）的 LinkedIn 帖里是否提及品牌？
4. **LinkedIn 长文**：有关于或提及品牌的 LinkedIn 长文吗？
5. **员工资料**：员工是否详细列出公司？有强专业资料吗？
6. **互动指标**：公司帖的典型互动（赞、评、分享）是多少？

**4 项快速建议**：

1. 优化公司页（完整信息 + 定期发帖）
2. 鼓励领导层每周发 thought leadership
3. 发布 LinkedIn 长文（在你独有专长的话题上）
4. 在行业讨论中互动以提升专业语境曝光

### 5.8 其它平台详解（教学常被忽略的 7 个）

**Quora**
- 适用：B2C > B2B
- 检查：Quora 答案中是否提及品牌？品牌有官方 Quora 存在吗？
- 信号强度：B2C 中等，B2B 较低
- AI 引用：Perplexity 大量引用

**Stack Overflow / Stack Exchange**
- 适用：开发者向品牌（SaaS、开发工具、API）
- 检查：品牌产品在 SO 问答中被讨论吗？品牌有 tag 吗？官方答 SO 吗？
- 信号强度：技术产品高，非技术 B2C 不相关
- AI 引用：Perplexity 重度引用技术问题

**GitHub**
- 适用：开源 + 开发者向品牌
- 检查：品牌有 GitHub 组织？仓库 stars？其它 repo 文档/讨论中提及？
- 信号强度：开发工具/开源高，非技术品牌低
- AI 引用：Copilot（微软资产）特别看重

**行业论坛 / 社区**
- 检查：是否在行业特定论坛被讨论（Hacker News for 技术、ProductHunt for 创业、行业 Slack）
- 信号强度：中，但对建立细分领域权威很重要

**新闻 / 媒体**
- 检查：是否被主流媒体或行业出版报道？多近？什么语境？
- 信号强度：中。**Recency 关键——6 个月内的提及远值于 3 年前的**
- AI 引用：所有 AI 平台对新闻源都有较高权重

**播客**
- 适用：所有
- 检查：品牌或领导层上过播客吗？播客字幕是否被搜索引擎索引提及？
- 信号强度：中，且持续上升
- 趋势：AI 训练数据越来越多吃播客字幕

**Crunchbase**
- 适用：B2B / 创业 / 融资过的公司
- 检查：完整公司画像？融资记录？团队？
- ChatGPT 直接引用 Crunchbase 数据

**G2 / Capterra / Trustpilot**
- 适用：SaaS / 服务类
- 检查：评分 + 评论数 + 最近评论时间
- ChatGPT 在产品对比类查询中大量引用 G2 评论

### 5.9 跨平台 sameAs 闭环（最重要的工程动作）

把上面所有平台的链接，统一塞到首页的 Organization JSON-LD 的 `sameAs` 数组里。**这是单点最大杠杆**——一行 JSON 解决跨平台实体识别问题。

```json
{
  "@context": "https://schema.org",
  "@type": "Organization",
  "@id": "https://yourdomain.com/#organization",
  "name": "Your Brand",
  "url": "https://yourdomain.com",
  "sameAs": [
    "https://en.wikipedia.org/wiki/Your_Brand",
    "https://www.wikidata.org/wiki/Q12345",
    "https://www.linkedin.com/company/yourbrand",
    "https://www.youtube.com/@yourbrand",
    "https://www.reddit.com/r/yourbrand",
    "https://www.crunchbase.com/organization/yourbrand",
    "https://github.com/yourbrand",
    "https://twitter.com/yourbrand",
    "https://www.facebook.com/yourbrand",
    "https://www.instagram.com/yourbrand",
    "https://www.g2.com/products/yourbrand",
    "https://www.producthunt.com/products/yourbrand"
  ]
}
```

**14 个推荐平台优先级**（按对 GEO 价值排序）：

1. Wikipedia 文章 — 最高权威实体链接
2. Wikidata 条目 — 机器可读实体标识符（如 `https://www.wikidata.org/wiki/Q12345`）
3. LinkedIn — 公司页或个人资料
4. YouTube — 频道 URL
5. Twitter/X — 资料 URL
6. Facebook — 主页 URL
7. Crunchbase — 公司画像（创业/科技重要）
8. GitHub — 组织或个人（科技重要）
9. Google Scholar — 作者资料（研究/学术）
10. ORCID — 研究者标识符（学术）
11. Instagram — 资料 URL
12. Apple App Store / Google Play — 应用列表（软件）
13. BBB（Better Business Bureau）— 美国本地企业
14. 行业垂直目录 — 相关纵向目录

**sameAs 审计 5 步**：

1. 收集该实体的所有已知 web 存在
2. 检查每个 URL 是否解析（不是 404 或重定向）
3. 验证 Organization/Person schema 包含全部
4. 验证每个平台的信息一致（名字、描述、创立日期等）
5. 标记应该有但还没有的平台

### 5.10 实体歧义陷阱（容易被忽视的杀手）

**真实案例**：意大利有 4 家公司都叫 "Electron Srl"（教育设备 / 电子元件 / 工业 / 自动化）。AI 在被问 "Electron Srl" 时，要么混淆要么拒答。

**为什么这是重大问题**：
- AI 系统的 entity resolution 是基于实体唯一性的
- 同名实体让 AI 无法判断要引用谁
- 用户问"Electron Srl 怎么样"，AI 可能给出竞品（同名公司）的答案
- 严重时 AI 会拒答（"There are multiple companies named X, please specify"）

**4 步对策**：

1. **使用全名**——在所有地方使用消歧义全名（"Electron Srl Educational Equipment" 而不是 "Electron Srl"）
2. **Wikidata 加唯一标识符**——把精确标识符加进去：
   - 公司注册号（VAT number / Companies House ID）
   - GeoNames 地理编号（P1566）
   - Ringgold ID（教育/出版机构）
   - LEI（Legal Entity Identifier）
3. **Organization schema 加消歧义字段**——
   - `address`（精确到街道）
   - `foundingDate`（精确日期）
   - `description`（提及独有特征）
   - `industry`（明确分类）
4. **跨平台一致性**——LinkedIn 公司页 / Crunchbase / Wikipedia 等都使用同一全名 + 同一描述

### 5.11 品牌权威分级（教学口诀）

| 总分 | 评级 | 含义 |
|---|---|---|
| 85–100 | Dominant（统治级） | 跨平台被广泛识别，AI 高频引用推荐 |
| 70–84 | Strong（强） | 跨平台扎实存在，AI 在相关查询中引用 |
| 50–69 | Moderate（中等） | 部分平台有存在但有缺口，AI 引用不一致 |
| 30–49 | Weak（弱） | 平台存在有限，AI 可能不识别为独立实体 |
| 0–29 | Minimal（极弱） | 平台存在可忽略，AI 不太可能引用推荐 |

---

## 6. 维度三：内容质量与 E-E-A-T（20%）

### 6.1 E-E-A-T 是什么

E-E-A-T = **Experience（经验）+ Expertise（专业）+ Authoritativeness（权威）+ Trustworthiness（可信）**。

它是 Google 给质量评估员（Quality Raters）的内容评估框架。**关键更新——Google 2025 年 12 月的 Quality Rater Guidelines 把 E-E-A-T 从原本只针对 YMYL（Your Money Your Life，健康/金融/法律/安全）扩展到了所有竞争性查询**。这意味着——E-E-A-T 已经从"高风险话题专属"升级为"通用门槛"。

**对 GEO 的意义**：AI 模型在选"引用谁"时，本质上做的就是一次 E-E-A-T 筛选——它需要一个看起来可信的源头来背书。**Google 自己的判断**：四个维度里 **Trustworthiness（可信度）是地基**，没有它其它三个都失去意义。

E-E-A-T 不是排名因子（不是直接打分项），但它**通过影响 Google 内部的"质量评估"而间接影响排名**——同样地，AI 模型的"引用决策"也建立在类似的质量信号之上。

### 6.2 4 维详细信号清单

每维各 0–25 分，4 维加起来 100 分基础分。

#### 6.2.1 Experience（经验，25 分）

测量"作者亲自做过这件事吗，还是只是在写关于它"。

| 信号 | 分值 | 评分方法 |
|---|---|---|
| 第一人称叙述（"I tested..."、"We implemented..."） | 5 | 具体且具体 5 分；泛泛 3 分；无 0 分 |
| 原创研究或独有数据 | 5 | 原创数据 5 分；引用原创工作 3 分；无 0 分 |
| 含具体结果的案例研究 | 4 | 详细带数字 4 分；笼统 2 分；无 0 分 |
| 截图、照片、直接使用证据 | 3 | 真实证据 3 分；通用图 1 分；无 0 分 |
| 个人经验中的具体例子 | 4 | 具体且独特 4 分；部分具体 2 分；通用 0 分 |
| 流程演示（不仅是结果） | 4 | 来自经验的步骤 4 分；部分 2 分；无 0 分 |

**Experience 弱信号红旗**：
- 只总结他人观点，不增加新视角
- 通用建议（"It depends on your needs"）
- 不提及实际使用、测试、亲自参与
- 暗示无直接知识的对冲语（"reportedly"、"supposedly"、"some say"）

#### 6.2.2 Expertise（专业，25 分）

测量"作者真的懂这个领域吗"。

| 信号 | 分值 | 评分方法 |
|---|---|---|
| 作者资质可见（bio、学位、证书） | 5 | 完整 5 分；基础 bio 3 分；无作者 0 分 |
| 技术深度合于话题 | 5 | 透彻 5 分；够用 3 分；表面 0 分 |
| 方法论解释（如何得出结论） | 4 | 清晰 4 分；部分 2 分；无 0 分 |
| 数据支撑断言（统计、研究引用） | 4 | 来源充分 4 分；部分有数据 2 分；无支撑 0 分 |
| 行业术语用得正确 | 3 | 准确专业语言 3 分；基础 1 分；错误 0 分 |
| 详细作者页 | 4 | 专属作者页 4 分；简短 bio 2 分；无 0 分 |

**Expertise 弱信号红旗**：
- 断言无证据或来源
- 复杂话题表面覆盖
- 误用术语
- 无作者或作者无相关资质
- 内容广而泛而非深而专

#### 6.2.3 Authoritativeness（权威，25 分）

测量"别人是否承认这个作者/网站是权威"。

| 信号 | 分值 | 评分方法 |
|---|---|---|
| 来自权威源的入站引用 | 5 | 主流引用 5 分；部分 3 分；无 0 分 |
| 作者被媒体引用 | 4 | 主流媒体 4 分；行业媒体 2 分；无 0 分 |
| 行业奖项或认可 | 3 | 相关 3 分；边缘 1 分；无 0 分 |
| 演讲资质（会议、活动） | 3 | 列出 3 分；无 0 分 |
| 在同行评议或权威媒体发表 | 4 | 一线刊物 4 分；行业刊物 2 分；无 0 分 |
| 综合主题覆盖（topical authority） | 3 | 站点深度覆盖 3 分；部分 1 分；孤立 0 分 |
| 在 Wikipedia 等百科类被提及 | 3 | Wikipedia 3 分；其它百科 2 分；无 0 分 |

**Authoritativeness 弱信号红旗**：
- 单话题站，无深度覆盖
- 无外部验证
- 无权威反向链接
- 自封"专家"无证据

#### 6.2.4 Trustworthiness（可信，25 分，地基）

测量"内容和发布者是否可靠透明"。

| 信号 | 分值 | 评分方法 |
|---|---|---|
| 联系信息可见（地址、电话、邮箱） | 4 | 完整 4 分；仅邮件 2 分；无 0 分 |
| 隐私政策有且可访问 | 2 | 有 2 分；无 0 分 |
| TOS 服务条款 | 1 | 有 1 分；无 0 分 |
| HTTPS 有效证书 | 2 | 有效 2 分；无 0 分 |
| 编辑标准 / 更正政策 | 3 | 文档化 3 分；隐含 1 分；无 0 分 |
| 商业模式与利益冲突透明 | 3 | 清晰披露 3 分；部分 1 分；无 0 分 |
| 真实客户评论 | 3 | 验证评论 3 分；推荐语 1 分；无 0 分 |
| 准确的断言（无明显错误） | 4 | 全部准确 4 分；多数准确 2 分；有错误 0 分 |
| 联盟/赞助清晰披露 | 3 | 妥善披露 3 分；未披露或无 0 分 |

**Trustworthiness 弱信号红旗**：
- 无联系信息或物理地址
- 缺隐私政策或 TOS
- 未披露的联盟链接或赞助内容
- 可验证为虚假或误导的断言
- 无法联系发布者更正

### 6.3 完整内容分加权（分层结构）

内容分（0–100）采用**两层加权**——外层是组件权重，E-E-A-T 内部再 4 维平分：

**外层（5 大组件）**：

| 组件 | 权重 | 含义 |
|---|---|---|
| E-E-A-T 4 维（合并） | **60%** | 经验/专业/权威/可信 |
| 内容指标 | 15% | 字数、可读性、段落、标题层次 |
| AI 内容评估 | 10% | 是否疑似低质 AI 生成 |
| 主题权威 | 10% | 站对主题的覆盖深度 |
| 内容新鲜度 | 5% | 发布/更新日期可见性、内容当前性 |

**E-E-A-T 内部（4 维平分 60%）**：

| 维度 | 权重 | 占总分 |
|---|---|---|
| Experience | 25%（of 60%） | 15% |
| Expertise | 25%（of 60%） | 15% |
| Authoritativeness | 25%（of 60%） | 15% |
| Trustworthiness | 25%（of 60%） | 15% |

**等价的简化算法**（教学用，更易计算）：

```
E-E-A-T 子分（0–100）= (Experience + Expertise + Auth + Trust) × 1（每维 0–25，相加 0–100）
内容分（0–100）= EEAT × 0.60 + 内容指标 × 0.15 + AI 评估 × 0.10 + 主题权威 × 0.10 + 新鲜度 × 0.05
```

**拓展规则——主题权威可作为修正分**（教学进阶用）：

某些工具实现里，主题权威不计入 60/15/10/10/5 加权，而是作为整体修正分：基础分（仅 E-E-A-T 4×25%）+ 主题权威 +10/-5 修正。两种用法都见过——本课程默认使用上面那套加权，主题权威修正版作为参考。

### 6.4 字数分级（按页面类型）

**关键原则**：这些是**底线，不是目标**。词更多 ≠ 内容更好。

| 页面类型 | 最低词数 | 理想范围 | 备注 |
|---|---|---|---|
| 首页 | 500 | 500–1,500 | 清晰价值主张，不是文字墙 |
| 博客文章 | 1,500 | 1,500–3,000 | 透彻但聚焦 |
| 主柱内容 / 终极指南 | 2,000 | 2,500–5,000 | 综合主题覆盖 |
| 产品页 | 300 | 500–1,500 | 描述、规格、用例 |
| 服务页 | 500 | 800–2,000 | 是什么、怎么做、为什么、给谁 |
| About 页 | 300 | 500–1,000 | 公司/人故事 + 资质 |
| FAQ 页 | 500 | 1,000–2,500 | 透彻答案，不是一句话 |

### 6.5 可读性（Flesch Reading Ease）

**目标 Flesch 分数：60–70（8–9 年级水平）**——不是直接排名因子，但影响 citability。AI 平台偏好清晰、无歧义的内容。

**完整公式**：

```
Flesch = 206.835 - (1.015 × 平均每句词数) - (84.6 × 平均每词音节)
```

**完整 7 档对应表**：

| 分数 | 难度 | 对应水平 |
|---|---|---|
| 90–100 | Very Easy | 5 年级 |
| 80–89 | Easy | 6 年级 |
| 70–79 | Fairly Easy | 7 年级 |
| 60–69 | **Standard** | 8–9 年级 / **大众 web 内容最佳区** |
| 50–59 | Fairly Difficult | 10–12 年级 |
| 30–49 | Difficult | 大学 |
| 0–29 | Very Difficult | 大学毕业生+ |

**两个边界**：
- 太学术（< 30）→ 通用查询的 citability 下降
- 太简单（> 80）→ 缺少深度，影响专业信号

**没工具时怎么估**：
- 平均句长 15–20 词最理想
- 平均段长 2–4 句
- 行话：首次出现时定义
- 被动语态：< 15% 句子

### 6.6 段落结构（关键）

AI 平台在**段落级别**抽取内容。每段必须是自包含的语义单元。

**最优段落结构**：
- **2–4 句一段**——单句段薄弱，5+ 句段难抽取
- **每段一个想法**——不要在一段里混话题
- **以核心主张开头**——首句必须含主要观点
- **用证据支撑**——其余句子提供数据、例子、上下文
- **可独立引用**——每段抽出来都能成立

### 6.7 标题层次

| 规则 | 说明 |
|---|---|
| 每页一个 H1 | 主话题 / 标题 |
| H2 用于主要章节 | 应代表不同子话题 |
| H3 用于子节 | 嵌套于相关 H2 下 |
| 不跳级 | 不要 H1 直接跳 H3 |
| 标题描述性 | "How to Optimize for AI Search" 而非 "Section 2" |
| 适当用问句 | 直接对应 AI 查询 |

### 6.8 内链原则

- 每个内容页应链 3–5 个相关页面
- 锚文本描述性（不是 "click here"）
- 创建主题集群（pillar page 链到/被所有相关子话题页链）
- 孤立页（无内链指向）很少被 AI 引用

### 6.9 AI 生成内容评估

**Google 政策（2024 年 3 月明确）**：AI 生成内容**可接受**，只要表现出真实的 E-E-A-T 信号 + 人工审核。问题不在"如何创建"而在"是否提供价值"。

#### 8 个 AI 生成低质内容红旗

| 红旗 | 描述 | 例子 |
|---|---|---|
| **通用语病** | 千篇一律的开头/转折语 | "In today's fast-paced world..." / "It's important to note that..." / "At the end of the day..." / "delve into" |
| **零原创洞察** | 只重述广为流传的信息 | 整篇都是其它博客已经说过的话 |
| **无第一手经验** | 无个人轶事、案例、具体例子 | 全篇没有 "I/We did X" |
| **完美但空洞结构** | 标题列表都齐，每节内容浅薄 | 看着专业，读着没收获 |
| **无具体例子** | 抽象解释，无具体实例 | "Various tools are available..." |
| **重复结论** | 每节都用同一观点的不同说法收尾 | 主题陈述被换皮 3 次 |
| **过度对冲** | "Generally speaking" / "In most cases" / "It depends on various factors" 但从不说是哪些因素 |
| **缺人声** | 完全中立，无观点、偏好、专业判断 |

补充 2 个相关红旗：
- **填充内容**：删了不影响信息的段落
- **无数据无来源**：断言当事实，无归属或证据

#### 8 个高质量内容信号（无论生产方式）

| 信号 | 描述 |
|---|---|
| 原创数据 | 调查、实验、基准、专属分析 |
| 具体例子 | 具名产品、公司、日期、数字 |
| 反向或细致观点 | 与传统智慧不同，有理由支撑 |
| 第一人称经验 | "When I tested this..." 或 "Our team found..." |
| 更新信息 | 引用近期事件、当前数据 |
| 专家观点 | 清晰的专业判断，不仅是事实 |
| 实操建议 | 具体可操作，不是模糊指导 |
| 承认权衡 | "This works well for X but not for Y because..." |

### 6.10 主题权威（Topical Authority）

**定义**：站点是否综合覆盖一个主题，而不是浅尝辄止。

**评估 5 个维度**：
1. **内容广度**：站有多个页面覆盖核心主题的不同方面吗？
2. **内容深度**：单个页面对子话题深入吗？
3. **主题集群**：页面是否组织成逻辑组并内链？
4. **内容空缺**：是否有明显该覆盖但没覆盖的子话题？
5. **竞品对比**：竞品覆盖了哪些子话题，本站缺失？

**4 档评分（修正分）**：

| 等级 | 描述 | 分数修正 |
|---|---|---|
| Authority（权威） | 20+ 页综合覆盖话题，强集群 | **+10 加分** |
| Developing（发展中） | 10–20 页含一些集群 | +5 加分 |
| Emerging（萌芽） | 5–10 页含话题，集群有限 | 0 |
| Thin（薄） | <5 页，无集群 | **-5 扣分** |

### 6.11 内容新鲜度

**为什么新鲜度重要**：
- 没日期的内容被 AI 平台当作"低可信"
- 时间敏感话题（新闻、统计、技术）特别看重新鲜度
- Perplexity 的新鲜度去优先级化（deprioritize）比其它平台更激进

**5 档评分**：

| 标准 | 评分 |
|---|---|
| 3 个月内更新 | Excellent — 当前且相关 |
| 6 个月内更新 | Good — 仍较当前 |
| 12 个月内更新 | Acceptable — 可能需要刷新 |
| 12–24 个月前更新 | Warning — 审查准确性 |
| 无日期或 24+ 个月前 | Critical — AI 平台可能去优先级 |

**长青指标**（不受年龄影响）：
- 覆盖不变的基础概念（物理、数学、法律定义）
- 明确标记为持久概念的参考/指南
- 不含时间依赖的断言（"the latest"、"currently"、"in 2024"）

### 6.12 YMYL 主题特殊性（教学要点）

**YMYL（Your Money Your Life）= 健康 / 金融 / 法律 / 安全**——这些话题影响用户的钱包、健康、未来，Google 对其 E-E-A-T 要求**额外加权**。

**对 YMYL 站的特殊要求**：

| 要求 | 普通站 | YMYL 站 |
|---|---|---|
| Trustworthiness 权重 | 25% | 35–40% |
| 作者资质要求 | 推荐 | **必须**（医生执照、CFP、律师执照） |
| 来源引用要求 | 推荐 | **必须**（每个医学/金融断言要带链接） |
| 编辑标准 | 推荐 | **必须**（公开 review 流程） |
| 内容更新频率 | 季度 | **月度**（医学指南、税法变化） |

**重要扩展（Google 2025 年 12 月）**：E-E-A-T 已扩展到所有竞争性查询。YMYL 标准正在向所有领域渗透。

### 6.13 内容分级

| 总分 | 评级 | 含义 |
|---|---|---|
| 85–100 | Exceptional | AI 引用首选，跨平台强 |
| 70–84 | Good | 基础扎实，特定改进可提 citability |
| 55–69 | Average | 多个 E-E-A-T 缺口削弱 AI 可见度 |
| 40–54 | Below Average | 明显内容质量与可信问题 |
| 0–39 | Poor | 需根本内容策略重整 |

---

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

## 8. 维度五：结构化数据（Schema，10%）

### 8.1 一句话定位

**Schema 是给 AI 模型读的"机器可读说明书"**。它不是排名因子，是**实体识别加速器**。

传统 SEO 时代 schema 主要为了"赢得 Google 富片段"。GEO 时代 schema 的意义根本不同：**结构化数据是 AI 模型理解和信任你的实体的方式**。一个完整的实体图谱（通过 schema 表达）显著提升所有 AI 平台的引用概率。

### 8.2 12 组件评分细则（满分 100）

| 组件 | 满分 | 评分逻辑 |
|---|---|---|
| Organization/Person schema 完整 | 15 | 完整 15；基础 10；无 0 |
| **sameAs 链接（5+ 平台）** | **15** | 每个有效 sameAs 3 分，封顶 15 |
| Article schema + 完整作者 | 10 | 完整作者 10；仅名字 5；无 0 |
| 业务类型特定 schema | 10 | 完整 10；部分 5；缺失 0 |
| WebSite + SearchAction | 5 | 有 5；无 0 |
| 内页 BreadcrumbList | 5 | 有 5；无 0 |
| JSON-LD 格式（不是 Microdata/RDFa） | 5 | JSON-LD 5；混用 3；仅 Microdata/RDFa 0 |
| **服务端渲染（不是 JS 注入）** | **10** | HTML 源里 10；JS 但在 head 5；动态 JS 0 |
| Article 上 speakable 属性 | 5 | 有 5；无 0 |
| JSON 有效 + Schema.org 类型有效 | 10 | 无错误 10；小问题 5；大错误 0 |
| Organization/Person 的 knowsAbout 属性 | 5 | 3+ 话题 5；缺失 0 |
| 无废弃 schema | 5 | 干净 5；含废弃 schema 0 |

### 8.3 Google 富片段对应表（完整 15 行）

| 富片段类型 | 所需 schema | 关键要求 |
|---|---|---|
| Article | Article / NewsArticle / BlogPosting | headline、image、datePublished、author（Person 对象 with name + url） |
| Breadcrumb | BreadcrumbList | itemListElement 含 position、name、item |
| FAQ | FAQPage | mainEntity 含 Question/acceptedAnswer——**2023 年 8 月起仅政府/卫生当局站可显示富片段** |
| How-To | HowTo | **2023 年 9 月从 Google 富片段移除** |
| Local Business | LocalBusiness | name、address、telephone、openingHours |
| Organization | Organization | name、url、logo、sameAs |
| Person | Person | name、url、sameAs、jobTitle |
| Product | Product | name、image、offers（含 price、priceCurrency、availability） |
| Review | Review | itemReviewed、reviewRating、author |
| Sitelinks Search Box | WebSite + SearchAction | potentialAction with target URL template |
| Video | VideoObject | name、description、thumbnailUrl、uploadDate |
| Event | Event | name、startDate、location、eventAttendanceMode |
| Recipe | Recipe | name、image、author、datePublished、prepTime、cookTime、recipeIngredient |
| Course | Course | name、description、provider——**CourseInfo 已废弃** |
| Software App | SoftwareApplication | name、offers、applicationCategory |

### 8.4 6 个关键 schema 完整字段清单

#### 8.4.1 Organization（每个商业站必备）

**必填**：
- `@type`: "Organization"（或子类型：Corporation、LocalBusiness、EducationalOrganization 等）
- `name`: 官方品牌名
- `url`: 官方网站
- `logo`: logo 图片 URL（ImageObject 优于 URL 字符串）

**GEO 推荐**：
- `sameAs`: **所有平台 URL 数组**（最重要！）
- `description`: 1–2 句组织描述
- `foundingDate`: ISO 8601 日期
- `founder`: Person schema
- `address`: PostalAddress schema
- `contactPoint`: ContactPoint（含 telephone、email、contactType）
- `areaServed`: 服务地理区
- `numberOfEmployees`: QuantitativeValue
- `industry`: 行业分类
- `award`: 获得的奖项数组
- `knowsAbout`: 组织专长话题数组（**强 GEO 信号**）

**完整模板**：

```json
{
  "@context": "https://schema.org",
  "@type": "Organization",
  "@id": "https://YOURDOMAIN.com/#organization",
  "name": "YOUR_ORGANIZATION_NAME",
  "url": "https://YOURDOMAIN.com",
  "logo": {
    "@type": "ImageObject",
    "url": "https://YOURDOMAIN.com/logo.png",
    "width": 600,
    "height": 60
  },
  "description": "YOUR_ORGANIZATION_DESCRIPTION",
  "foundingDate": "YYYY-MM-DD",
  "founder": {
    "@type": "Person",
    "name": "FOUNDER_NAME",
    "url": "https://YOURDOMAIN.com/about/FOUNDER",
    "sameAs": [
      "https://www.linkedin.com/in/FOUNDER_LINKEDIN",
      "https://twitter.com/FOUNDER_TWITTER"
    ]
  },
  "contactPoint": {
    "@type": "ContactPoint",
    "telephone": "+1-XXX-XXX-XXXX",
    "contactType": "customer service",
    "email": "contact@YOURDOMAIN.com",
    "availableLanguage": ["English"]
  },
  "address": {
    "@type": "PostalAddress",
    "streetAddress": "YOUR_STREET",
    "addressLocality": "YOUR_CITY",
    "addressRegion": "YOUR_STATE",
    "postalCode": "YOUR_ZIP",
    "addressCountry": "US"
  },
  "sameAs": [
    "https://www.linkedin.com/company/YOUR_LINKEDIN",
    "https://www.youtube.com/@YOUR_YOUTUBE",
    "https://www.reddit.com/r/YOUR_SUBREDDIT",
    "https://twitter.com/YOUR_TWITTER",
    "https://www.facebook.com/YOUR_FACEBOOK",
    "https://github.com/YOUR_GITHUB",
    "https://www.crunchbase.com/organization/YOUR_CRUNCHBASE",
    "https://en.wikipedia.org/wiki/YOUR_WIKIPEDIA",
    "https://www.wikidata.org/wiki/YOUR_WIKIDATA_ID"
  ],
  "numberOfEmployees": {
    "@type": "QuantitativeValue",
    "value": "XX"
  },
  "areaServed": "US",
  "knowsAbout": [
    "TOPIC_1",
    "TOPIC_2",
    "TOPIC_3"
  ]
}
```

**关键细节**：
- `@id` 是站内固定锚点（如 `#organization`），其它 schema 通过 `@id` 引用同一实体，避免 AI 创建重复实体
- `sameAs` 越完整 = 实体识别越准确

#### 8.4.2 LocalBusiness（本地商业）

继承 Organization。本地 AI 搜索结果和 Gemini 关键。

**额外必填**：
- `address`: 完整 PostalAddress
- `telephone`: 电话
- `openingHoursSpecification`: 营业时间

**GEO 推荐**：
- `geo`: GeoCoordinates（latitude、longitude）
- `priceRange`: 价格指示（"$", "$$", "$$$", "$$$$"）
- `aggregateRating`: AggregateRating
- `review`: Review 数组
- `hasMap`: Google Maps URL

**完整模板**：

```json
{
  "@context": "https://schema.org",
  "@type": "LocalBusiness",
  "@id": "https://YOURDOMAIN.com/#localbusiness",
  "name": "YOUR_BUSINESS_NAME",
  "url": "https://YOURDOMAIN.com",
  "image": "https://YOURDOMAIN.com/images/storefront.jpg",
  "description": "YOUR_BUSINESS_DESCRIPTION",
  "telephone": "+1-XXX-XXX-XXXX",
  "email": "contact@YOURDOMAIN.com",
  "priceRange": "$$",
  "address": {
    "@type": "PostalAddress",
    "streetAddress": "YOUR_STREET",
    "addressLocality": "YOUR_CITY",
    "addressRegion": "YOUR_STATE",
    "postalCode": "YOUR_ZIP",
    "addressCountry": "US"
  },
  "geo": {
    "@type": "GeoCoordinates",
    "latitude": "XX.XXXXXX",
    "longitude": "-XX.XXXXXX"
  },
  "openingHoursSpecification": [
    {
      "@type": "OpeningHoursSpecification",
      "dayOfWeek": ["Monday", "Tuesday", "Wednesday", "Thursday", "Friday"],
      "opens": "09:00",
      "closes": "17:00"
    }
  ],
  "areaServed": {
    "@type": "GeoCircle",
    "geoMidpoint": {
      "@type": "GeoCoordinates",
      "latitude": "XX.XXXXXX",
      "longitude": "-XX.XXXXXX"
    },
    "geoRadius": "50 mi"
  },
  "sameAs": [
    "https://www.google.com/maps/place/YOUR_GOOGLE_MAPS_URL",
    "https://www.yelp.com/biz/YOUR_YELP_URL",
    "https://www.facebook.com/YOUR_FACEBOOK",
    "https://www.linkedin.com/company/YOUR_LINKEDIN",
    "https://www.bbb.org/YOUR_BBB_URL"
  ],
  "aggregateRating": {
    "@type": "AggregateRating",
    "ratingValue": "4.8",
    "reviewCount": "XX",
    "bestRating": "5"
  },
  "hasOfferCatalog": {
    "@type": "OfferCatalog",
    "name": "Services",
    "itemListElement": [
      {
        "@type": "Offer",
        "itemOffered": {
          "@type": "Service",
          "name": "SERVICE_NAME_1",
          "description": "SERVICE_DESCRIPTION_1"
        }
      }
    ]
  }
}
```

#### 8.4.3 Article + Person（媒体出版关键）

作者 schema 是 AI 平台最强 E-E-A-T 信号之一。

**Article 必填**：
- `@type`: "Article"（或 NewsArticle、BlogPosting、TechArticle）
- `headline`: 文章标题
- `datePublished`: ISO 8601
- `dateModified`: ISO 8601（**对新鲜度信号关键**）
- `author`: Person 或 Organization schema
- `publisher`: Organization schema 含 logo
- `image`: 代表图

**Person（作者）GEO 必填**：
- `name`: 全名
- `url`: 站内作者页
- `sameAs`: LinkedIn、Twitter、个人站、Google Scholar、ORCID
- `jobTitle`: 职务
- `worksFor`: Organization schema
- `knowsAbout`: 专长领域数组
- `alumniOf`: 教育机构
- `award`: 专业奖项

**完整模板**：

```json
{
  "@context": "https://schema.org",
  "@type": "Article",
  "@id": "https://YOURDOMAIN.com/blog/ARTICLE_SLUG/#article",
  "headline": "ARTICLE_TITLE",
  "description": "ARTICLE_DESCRIPTION",
  "url": "https://YOURDOMAIN.com/blog/ARTICLE_SLUG",
  "datePublished": "YYYY-MM-DD",
  "dateModified": "YYYY-MM-DD",
  "image": {
    "@type": "ImageObject",
    "url": "https://YOURDOMAIN.com/images/ARTICLE_IMAGE.jpg",
    "width": 1200,
    "height": 630
  },
  "author": {
    "@type": "Person",
    "@id": "https://YOURDOMAIN.com/about/AUTHOR_SLUG/#person",
    "name": "AUTHOR_NAME",
    "url": "https://YOURDOMAIN.com/about/AUTHOR_SLUG",
    "image": "https://YOURDOMAIN.com/images/authors/AUTHOR_IMAGE.jpg",
    "jobTitle": "AUTHOR_JOB_TITLE",
    "description": "AUTHOR_BIO_SHORT",
    "knowsAbout": ["EXPERTISE_1", "EXPERTISE_2", "EXPERTISE_3"],
    "sameAs": [
      "https://www.linkedin.com/in/AUTHOR_LINKEDIN",
      "https://twitter.com/AUTHOR_TWITTER",
      "https://github.com/AUTHOR_GITHUB",
      "https://en.wikipedia.org/wiki/AUTHOR_WIKIPEDIA"
    ],
    "alumniOf": {
      "@type": "CollegeOrUniversity",
      "name": "UNIVERSITY_NAME"
    },
    "worksFor": {
      "@type": "Organization",
      "@id": "https://YOURDOMAIN.com/#organization"
    }
  },
  "publisher": {
    "@type": "Organization",
    "@id": "https://YOURDOMAIN.com/#organization",
    "name": "YOUR_ORGANIZATION_NAME",
    "logo": {
      "@type": "ImageObject",
      "url": "https://YOURDOMAIN.com/logo.png"
    }
  },
  "mainEntityOfPage": {
    "@type": "WebPage",
    "@id": "https://YOURDOMAIN.com/blog/ARTICLE_SLUG"
  },
  "wordCount": "XXXX",
  "articleSection": "CATEGORY",
  "keywords": "KEYWORD_1, KEYWORD_2, KEYWORD_3",
  "speakable": {
    "@type": "SpeakableSpecification",
    "cssSelector": [".article-summary", ".key-takeaway", "h2"]
  },
  "isAccessibleForFree": true,
  "inLanguage": "en-US"
}
```

**两个关键细节**：
- **作者必须是 Person 对象**——不能是 `"author": "Jane Doe"` 字符串。AI 系统从对象里读 `sameAs` 完成作者身份验证
- **speakable 是被严重低估的属性**——明确告诉 AI 这部分内容适合做语音播报或 AI 助手回答

#### 8.4.4 Product（电商）

**必填**：
- `name`、`description`、`image`
- `offers`: Offer 含 price、priceCurrency、availability
- `brand`: Brand schema
- `sku` 或 `gtin`/`mpn`

**GEO 推荐**：
- `aggregateRating`
- `review`: 单条评论数组
- `category`: 产品类目
- `material`、`weight`、`width`、`height`（适用时）

**完整模板**（含 ShippingDetails + MerchantReturnPolicy）：

```json
{
  "@context": "https://schema.org",
  "@type": "Product",
  "@id": "https://YOURDOMAIN.com/products/PRODUCT_SLUG/#product",
  "name": "PRODUCT_NAME",
  "url": "https://YOURDOMAIN.com/products/PRODUCT_SLUG",
  "description": "PRODUCT_DESCRIPTION",
  "image": [
    "https://YOURDOMAIN.com/images/products/PRODUCT_1.jpg",
    "https://YOURDOMAIN.com/images/products/PRODUCT_2.jpg"
  ],
  "brand": { "@type": "Brand", "name": "YOUR_BRAND_NAME" },
  "sku": "YOUR_SKU",
  "gtin13": "YOUR_GTIN",
  "mpn": "YOUR_MPN",
  "category": "PRODUCT_CATEGORY",
  "material": "PRODUCT_MATERIAL",
  "color": "PRODUCT_COLOR",
  "weight": {
    "@type": "QuantitativeValue",
    "value": "X.X",
    "unitCode": "LBR"
  },
  "offers": {
    "@type": "Offer",
    "url": "https://YOURDOMAIN.com/products/PRODUCT_SLUG",
    "price": "XX.XX",
    "priceCurrency": "USD",
    "priceValidUntil": "YYYY-12-31",
    "availability": "https://schema.org/InStock",
    "itemCondition": "https://schema.org/NewCondition",
    "seller": { "@type": "Organization", "@id": "https://YOURDOMAIN.com/#organization" },
    "shippingDetails": {
      "@type": "OfferShippingDetails",
      "shippingRate": {
        "@type": "MonetaryAmount",
        "value": "0",
        "currency": "USD"
      },
      "deliveryTime": {
        "@type": "ShippingDeliveryTime",
        "handlingTime": {
          "@type": "QuantitativeValue",
          "minValue": "0",
          "maxValue": "1",
          "unitCode": "DAY"
        },
        "transitTime": {
          "@type": "QuantitativeValue",
          "minValue": "3",
          "maxValue": "7",
          "unitCode": "DAY"
        }
      },
      "shippingDestination": {
        "@type": "DefinedRegion",
        "addressCountry": "US"
      }
    },
    "hasMerchantReturnPolicy": {
      "@type": "MerchantReturnPolicy",
      "applicableCountry": "US",
      "returnPolicyCategory": "https://schema.org/MerchantReturnFiniteReturnWindow",
      "merchantReturnDays": "30",
      "returnMethod": "https://schema.org/ReturnByMail",
      "returnFees": "https://schema.org/FreeReturn"
    }
  },
  "aggregateRating": {
    "@type": "AggregateRating",
    "ratingValue": "4.6",
    "reviewCount": "XXX",
    "bestRating": "5"
  }
}
```

#### 8.4.5 SoftwareApplication（SaaS）

**必填**：
- `name`、`description`
- `applicationCategory`: e.g., "BusinessApplication"
- `operatingSystem`: 支持平台
- `offers`: 定价

**GEO 推荐**：
- `aggregateRating`: 用户评分
- `featureList`: 功能数组（**强引用信号**——AI 抽取功能列表）
- `screenshot`: 截图
- `softwareVersion`: 当前版本
- `releaseNotes`: changelog 链接

**完整模板**（含 AggregateOffer 多档定价）：

```json
{
  "@context": "https://schema.org",
  "@type": "SoftwareApplication",
  "@id": "https://YOURDOMAIN.com/#software",
  "name": "YOUR_SOFTWARE_NAME",
  "url": "https://YOURDOMAIN.com",
  "description": "YOUR_SOFTWARE_DESCRIPTION",
  "applicationCategory": "BusinessApplication",
  "operatingSystem": "Web, Windows, macOS, Linux",
  "offers": {
    "@type": "AggregateOffer",
    "lowPrice": "XX",
    "highPrice": "XXX",
    "priceCurrency": "USD",
    "offerCount": "3",
    "offers": [
      {
        "@type": "Offer",
        "name": "Starter Plan",
        "price": "XX",
        "priceCurrency": "USD",
        "availability": "https://schema.org/InStock"
      },
      {
        "@type": "Offer",
        "name": "Professional Plan",
        "price": "XX",
        "priceCurrency": "USD",
        "availability": "https://schema.org/InStock"
      },
      {
        "@type": "Offer",
        "name": "Enterprise Plan",
        "price": "XXX",
        "priceCurrency": "USD",
        "availability": "https://schema.org/InStock"
      }
    ]
  },
  "aggregateRating": {
    "@type": "AggregateRating",
    "ratingValue": "4.7",
    "reviewCount": "XXX",
    "bestRating": "5"
  },
  "featureList": ["FEATURE_1", "FEATURE_2", "FEATURE_3", "FEATURE_4"],
  "screenshot": "https://YOURDOMAIN.com/images/screenshot.png",
  "softwareVersion": "X.X",
  "author": { "@type": "Organization", "@id": "https://YOURDOMAIN.com/#organization" },
  "sameAs": [
    "https://www.g2.com/products/YOUR_G2",
    "https://www.capterra.com/p/YOUR_CAPTERRA",
    "https://www.producthunt.com/products/YOUR_PH",
    "https://github.com/YOUR_GITHUB"
  ]
}
```

#### 8.4.6 WebSite + SearchAction

让站出现在 sitelinks 搜索框。

```json
{
  "@context": "https://schema.org",
  "@type": "WebSite",
  "@id": "https://YOURDOMAIN.com/#website",
  "name": "YOUR_SITE_NAME",
  "url": "https://YOURDOMAIN.com",
  "description": "YOUR_SITE_DESCRIPTION",
  "publisher": {
    "@type": "Organization",
    "@id": "https://YOURDOMAIN.com/#organization"
  },
  "potentialAction": {
    "@type": "SearchAction",
    "target": {
      "@type": "EntryPoint",
      "urlTemplate": "https://YOURDOMAIN.com/search?q={search_term_string}"
    },
    "query-input": "required name=search_term_string"
  },
  "inLanguage": "en-US"
}
```

### 8.5 sameAs 14 个推荐平台优先级

按对 GEO 价值排序（已在第 5 章列过，这里再贴一次方便查阅）：

1. Wikipedia 文章 — 最高
2. Wikidata 条目
3. LinkedIn — 公司页或个人
4. YouTube — 频道 URL
5. Twitter/X — 资料
6. Facebook — 主页
7. Crunchbase
8. GitHub — 组织或个人
9. Google Scholar — 作者（学术）
10. ORCID — 研究者标识符
11. Instagram
12. Apple App Store / Google Play — 应用列表
13. BBB — 美国商业改进局
14. 行业垂直目录

### 8.6 已废弃 / 受限的 schema 完整清单（必须知道）

| Schema | 状态 | 时间 | 处理建议 |
|---|---|---|---|
| **HowTo** | **从 Google 富片段移除** | 2023-09 | 删除以减页面体积；或保留作为 AI 语义信号 |
| **FAQPage** | **受限** | 2023-08 | 仅政府/卫生当局站点显示富片段。但保留对 AI 仍有 Q&A 语义价值 |
| **SpecialAnnouncement** | 已废弃 | — | 删除（COVID 用的） |
| **CourseInfo** | 已废弃 | — | 用新版 Course 结构 |
| **VideoObject `contentUrl`** | 行为变化 | 2024 | 必须指向真实视频文件，不是页面 URL |
| **Review snippet** | 强制更严 | 2024 | 产品页自家 review 可能不显示 |

**教学要点**：如果你的课件还在教 HowTo schema → 立刻更新。这是过去两年 schema 领域最大的变化之一。

### 8.7 6 条 Common Errors（schema 校验时常见错误）

| 错误 | 表现 | 修复 |
|---|---|---|
| 缺 `@context` | 没有 `@context: "https://schema.org"` | 加上 |
| 拼错属性名 | `datePublihed` 而非 `datePublished` | 校对 |
| 值类型错 | URL 字段填字符串 / 日期字段非 ISO 8601 | 修正类型 |
| 占位符值 | `name: "YOUR_NAME"` 没替换 | 替换为真实值 |
| 重复冲突 schema 块 | 两个 Organization schema 信息冲突 | 合并或保留一个 |
| 嵌套错误 | author 是字符串而非 Person 对象 | 改成对象 |

### 8.8 JS 注入 schema 的陷阱

**Google 自己 2025 年 12 月的官方指南**：JS 注入的 JSON-LD 可能被**延迟处理**。AI 爬虫直接看不到。

**判定规则**：
- Schema 在初始 HTML 响应里 → ✅ 即时处理
- Schema 由 React/Vue/Angular 在水合后插入 → ❌ Google 延迟，AI 爬虫完全看不到

**解决**：把 schema 写进 SSR 输出 / 服务端模板，不要靠前端框架的 portal 注入。

**检测方法**：用 `curl` 抓取，搜索 `<script type="application/ld+json">`。如果 curl 输出里没有但浏览器看得到 → JS 注入了。

### 8.9 Schema 分级

| 总分 | 评级 | 含义 |
|---|---|---|
| 90–100 | Excellent | 完整实体图谱，AI 可信 |
| 70–89 | Good | 基础扎实有改进空间 |
| 50–69 | Fair | 有缺口，主要 schema 有但不完整 |
| 30–49 | Poor | 显著实体识别问题 |
| 0–29 | Critical | 几乎无 schema，AI 无法识别实体 |

---

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

## 10. llms.txt 详解（新基础设施）

### 10.1 是什么 + 由谁提出

**llms.txt** 是 **Jeremy Howard（fast.ai 创始人）2024 年 9 月**提出的标准。位于网站根目录：

```
https://yourdomain.com/llms.txt
```

它给 AI 系统提供站结构、内容、关键信息的**结构化、机器可读、人类可读**摘要。

类比：
- robots.txt 告诉爬虫**不能访问什么**
- llms.txt 告诉 AI 系统**最有用的内容是什么**

### 10.2 为什么 llms.txt 重要

AI 模型在处理网站时面对一个根本挑战：**判断哪些页最重要、站讲什么、内容怎么组织**——通常通过爬许多页推断结构。llms.txt 用一个文件**显式提供**这些信息。

**5 个好处**：

1. **更快 AI 理解**：AI 从单文件理解站目的和结构，无需爬十几页
2. **掌控叙事**：你选 AI 看哪些页和事实，塑造它如何呈现你的品牌
3. **更高引用准确性**：咨询 llms.txt 的 AI 系统能引用每个话题的正确权威页
4. **减少错表**：关键事实（定价、特性、位置）显式声明，减少 AI 关于业务的幻觉
5. **早期采用者优势**：截至 2026 年初，**< 5% 的网站**有 llms.txt——是差异化点

### 10.3 完整规范

#### 10.3.1 文件格式

```markdown
# [站名]

> [一句描述：站/业务做什么。< 200 字符]

## Docs

- [Page Title](https://example.com/page-url): 简洁描述本页覆盖什么、为什么重要。
- [Another Page](https://example.com/another-page): 描述。

## Optional

- [Less Critical Page](https://example.com/optional-page): 描述。
```

#### 10.3.2 详细格式规则

**1. 标题（必需）**
```markdown
# 站名
```
- 必须是文件第一行
- 应是官方业务/站名
- H1 格式（单 `#`）

**2. 描述（必需）**
```markdown
> 简短描述
```
- 紧跟在标题后
- Markdown blockquote（`>`）
- < 200 字符
- 清晰陈述业务做什么、给谁
- **避免营销话**——事实、具体

**3. 主区块（至少一个，必需）**

H2（`##`）按类目组织页。常见区块名：

| 区块 | 用途 | 例子 |
|---|---|---|
| `## Docs` | 主文档或关键页 | 产品页、服务描述、核心内容 |
| `## Optional` | 值得知道的次要页 | 博客文章、补充资源 |
| `## API` | API 文档 | API 参考、认证指南 |
| `## Blog` | 博客或新闻 | 近期/热门文章 |
| `## Products` | 产品目录 | 产品页、定价 |
| `## Services` | 服务 | 服务描述、流程页 |
| `## About` | 公司信息 | About 页、团队、使命 |
| `## Resources` | 教育/参考内容 | 指南、教程、白皮书 |
| `## Legal` | 法律文档 | TOS、隐私政策 |
| `## Contact` | 联系信息 | 联系页、支持渠道 |

**4. 页面条目（必需）**

每条格式：
```markdown
- [Page Title](URL): 页面内容描述
```

规则：
- **标题**：实际页标题或清晰描述性标题
- **URL**：完整绝对 URL（不是相对路径）
- **描述**：10–30 词描述本页内容。具体说明可获信息。
- **顺序**：每区块内按重要性列
- **限制**：总共 10–30 条。优先最权威、有用的页。

**5. 关键事实区（推荐）**

```markdown
## Key Facts
- 创立于 [年份]，由 [创始人]
- 总部：[城市，国家]
- 服务 [X] 客户/用户在 [Y] 国家
- 关键产品：[A]、[B]、[C]
- 行业：[分类]
```

**6. 联系区（推荐）**

```markdown
## Contact
- Website: https://example.com
- Email: hello@example.com
- Support: support@example.com
- Phone: +1-555-123-4567
- Address: 123 Main St, City, State, ZIP
```

### 10.4 描述写得好 vs 写得差（教学例子）

**✅ 好的描述（具体、信息丰富）**：
- "Explains the three pricing tiers (Free, Pro, Enterprise) with feature comparison and annual/monthly costs."
- "Details the company's founding in 2018, team of 45 employees, and office locations in Austin and London."
- "Covers integration setup for Slack, Salesforce, and HubSpot with step-by-step guides and API endpoints."

**❌ 差的描述（营销腔、模糊）**：
- "Our amazing pricing page!"（营销话，无具体信息）
- "Learn more about our company."（太模糊）
- "Click here for details."（无描述性）

### 10.5 评分阈值（5 档）

| 状态 | 分数 |
|---|---|
| 不存在 | 0 |
| 存在但格式错误 | 30 |
| 存在格式有效但内容稀少 | 50 |
| 存在有效且覆盖主要内容区 | 70 |
| 完整 + 同时有 llms-full.txt | 90–100 |

### 10.6 11 项验证检查

| 元素 | 检查 | 缺失严重度 |
|---|---|---|
| H1 标题 | 存在，匹配业务名 | Critical |
| Blockquote 描述 | 存在，<200 字符，事实 | High |
| 至少一个 H2 区块 | 存在 | Critical |
| 含 URL 的页条目 | 至少 5 条 | High |
| URL 是绝对的 | 全用完整 https:// | High |
| URL 有效 | 全部返回 200 | Medium |
| 描述存在 | 每个条目含冒号后描述 | Medium |
| Key Facts 区块 | 存在含业务信息 | Medium |
| Contact 区块 | 存在至少含邮件 | Low |
| 长度合理 | 30–200 行 | Low |
| Markdown 无错 | 全文格式正确 | Medium |

### 10.7 综合评分

```
llms.txt Score = Completeness × 0.40 + Accuracy × 0.35 + Usefulness × 0.25
```

**Completeness（完整度）**：
- 覆盖所有主要导航区块？
- 最重要 / 高流量页都包括？
- Key Facts 含准确业务数据？
- 含近期 / 更新内容？

**Accuracy（准确度）**：
- 描述准确反映页内容？
- URL 有效指向正确页？
- Key Facts 可验证且当前？
- 业务描述准确？

**Usefulness（有用度）**：
- AI 仅看此文件能理解站目的？
- 描述足够具体区分页面？
- 最值得引用的页被高亮？
- 组织逻辑直观？

### 10.8 llms.txt vs llms-full.txt 对比

| 特性 | llms.txt | llms-full.txt |
|---|---|---|
| 长度 | 简洁（50–150 行） | 综合（150–500+ 行） |
| 页条目 | 10–30 关键页 | 30–100+ 页 |
| 描述 | 10–30 词/条 | 30–100 词/条，可含每页关键事实 |
| 受众 | 快 AI 理解 | 深 AI 分析 |
| 区块 | 3–6 区块 | 8–15 区块 |
| 关键事实 | 业务级 | 页面级数据点 |

**两者可共存**。AI 系统先看 llms.txt，可能加载 llms-full.txt 做深理解。

### 10.9 10 条最佳实践

1. **定期更新**：周更博客 → llms.txt 月更；季度产品变化 → 每次发布后更新
2. **领头放最强内容**：每区块第一条应是最权威综合页
3. **描述具体**："3,000-word guide to React Server Components with code examples" 远胜 "React guide"
4. **含独有差异化**：独家数据、原创研究、独有特性在描述和 Key Facts 高亮
5. **保持简洁**：< 60 秒可扫完。深度留给 llms-full.txt
6. **绝对 URL**：永远完整 `https://`
7. **部署后测**：上传后验证 `https://yourdomain.com/llms.txt` 直接可访问无重定向
8. **与 robots.txt 协调**：llms.txt 列出的页不能在 robots.txt 封 AI 爬虫
9. **镜像站结构**：区块名应大致对应主导航类目
10. **避免敏感页**：不含内部工具、admin 面板、敏感页

### 10.10 自动生成 llms.txt 的页面分类逻辑

实战中可用脚本爬整站再分类。简单的分类规则：

```python
# 路径关键词 → 区块映射
if any(kw in path for kw in ["/pricing", "/feature", "/product", "/solution", "/demo"]):
    section = "Products & Services"
elif any(kw in path for kw in ["/blog", "/article", "/resource", "/guide", "/learn", "/docs", "/documentation"]):
    section = "Resources & Blog"
elif any(kw in path for kw in ["/about", "/team", "/career", "/contact", "/press", "/partner"]):
    section = "Company"
elif any(kw in path for kw in ["/help", "/support", "/faq", "/status"]):
    section = "Support"
else:
    section = "Main Pages"
```

每区块上限 10 条（简版）或不限（完整版）。

---

## 11. 完整审计编排流程

### 11.1 三阶段流程

#### Phase 1：Discovery（发现，串行）

**Step 1：抓首页 + 检测业务类型**

抓取并提取：
- 页标题、meta description、H1
- 导航菜单项（揭示站结构）
- 页脚内容（揭示业务信息、位置、法律页）
- 首页 Schema.org 标记
- 定价页链接（SaaS 信号）
- 产品列表模式（电商信号）
- 博客/资源区（出版商信号）
- 服务页（代理商信号）
- 地址/电话/Google Maps embed（本地信号）

按第 3 章的 6 类业务模式分类。

**Step 2：抓 sitemap + 内链**

1. 试抓 `/sitemap.xml` 和 `/sitemap_index.xml`
2. 如有 sitemap，提最多 50 个 URL，优先级：
   - 首页（必含）
   - 顶级导航页
   - 高价值页（定价、about、contact、关键服务/产品）
   - 博客文章（5–10 最近）
   - 类目/落地页
3. 如无 sitemap，从首页爬内链：
   - 提取所有同域 `<a href>`
   - 跟到 2 层深
   - 优先主导航链接
4. 尊重 robots.txt——不抓 disallowed 路径
5. 强制：最多 50 页 + 30 秒 / 页超时

**Step 3：收集页级数据**

每页记录：
- URL、title、meta description、canonical URL
- H1–H6 标题结构
- 主内容字数
- Schema.org 类型
- 内/外链数
- 含/不含 alt 文本图片
- OG 和 Twitter Card meta
- 响应状态码
- 是否有结构化数据

#### Phase 2：Parallel Analysis（并行分析）

5 个专业子代理并行运行（节省时间约 5×）：

| 子代理 | 输出 |
|---|---|
| AI Visibility | citability + crawler access + llms.txt + brand mentions |
| Platform Optimization | AIO + ChatGPT + Perplexity + Gemini + Copilot |
| Technical | crawl + index + security + URL + mobile + CWV + SSR + speed |
| Content & E-E-A-T | 4 维 + 内容指标 + AI 内容评估 + 主题权威 + 新鲜度 |
| Schema | 检测 + 校验 + sameAs 审计 + 模板生成 |

每个子代理产出 0–100 的类别分 + 发现 + 建议。

#### Phase 3：Synthesis（综合）

1. 收集所有子代理报告
2. 计算合成 GEO 分（按第 2 章公式）
3. 按严重度归类发现
4. 生成优先级行动计划
5. 输出客户向报告

### 11.2 4 档严重度分类

每个发现按以下标准归类：

#### Critical（立即修）

- 所有 AI 爬虫被 robots.txt 封
- 无可索引内容（仅 JS 渲染无 SSR）
- 域级 noindex
- 关键页返回 5xx
- 完全无结构化数据
- 任何 AI 系统都不识别该品牌为实体

#### High（1 周内）

- 关键 AI 爬虫（GPTBot/ClaudeBot/PerplexityBot）被封
- 无 llms.txt
- 关键页零问答内容块
- 缺 Organization 或 LocalBusiness schema
- 内容页无作者归属
- 全部内容在登录/付费墙后无预览

#### Medium（1 个月内）

- 部分 AI 爬虫被封
- llms.txt 存在但不完整或错误
- 内容块平均 citability < 50
- 含 FAQ 内容的页缺 FAQPage schema
- 作者 bio 薄无资质
- 无 Wikipedia 或 Reddit 品牌存在

#### Low（有空再优化）

- 微小 schema 校验错误
- 部分图缺 alt
- 非关键页内容新鲜度问题
- 缺 OG 标签
- 部分页标题层级次优
- LinkedIn 公司页存在但不完整

### 11.3 质量门（Quality Gates）

执行审计的硬限制：

- **页数限制**：每次审计最多 50 页。优先高价值页。
- **超时**：每页抓取最多 30 秒。超过跳过。
- **robots.txt**：永远先检查并尊重。记录 AI 特定指令。
- **速率限制**：页间至少 1 秒间隔，避免压垮服务器。
- **错误处理**：抓取失败记录但继续审计。失败页报告附录列出。
- **内容类型**：仅分析 HTML 页。跳过 PDF、图、其它二进制。
- **去重**：抓前规范化 URL。跳过重复（HTTP vs HTTPS、www vs 非 www、尾斜杠）。

### 11.4 输出文件清单

| 阶段 | 输出 |
|---|---|
| 发现 | 业务类型分类、页清单 |
| 并行分析 | 5 份子代理报告（每份含分数 + 发现 + 建议） |
| 综合 | `GEO-AUDIT-REPORT.md`（综合报告） |
| 客户向 | `GEO-CLIENT-REPORT.md` 或 PDF（含图表） |

---

## 12. 完整案例：electron-srl.com 从 28 → 86 分

> 这是一个真实的诊断案例，演示这套方法论如何应用于一个具体客户。
> 教学价值：让学员看到"差到极致 → 优秀"的完整路径，每一步都有具体动作和分数预期。

### 12.1 客户画像

| 字段 | 值 |
|---|---|
| 域名 | electron-srl.com |
| 公司名 | Electron Srl |
| 创立 | 1991 年（35 年历史） |
| 总部（运营） | Via Massimo D'Antona 6T, 60033 Chiaravalle (AN), Italy |
| 总部（注册） | Via Cascina Torchio snc, 26833 Merlino (LO), Italy |
| 业务类型 | B2B 制造商——技术学校的教育实验设备 |
| 市场 | 70+ 国家 |
| 产品 | 电子、电气、电信、自动化、CNC 培训系统 |
| 多域名 | electron-srl.com（英）、electron-srl.it（意）、electron-srl.fr（法） |
| CMS | WordPress |
| 哲学 | "Made in Italy"——真实制造商，本地采购 |

**这是一家典型的"老牌实业公司"——35 年历史、产品扎实、市场广阔，但完全没碰过 AI 时代的优化**。这种公司在工业、教育、医疗、专业服务领域非常多见。

### 12.2 初始 GEO 分：28/100（Critical）

#### 6 维分数

| 类别 | 分数 | 权重 | 加权 | 状态 |
|---|---|---|---|---|
| AI Citability & Visibility | **18/100** | 25% | 4.5 | CRITICAL |
| Brand Authority Signals | **15/100** | 20% | 3.0 | CRITICAL |
| Content Quality & E-E-A-T | 35/100 | 20% | 7.0 | POOR |
| Technical Foundations | 38/100 | 15% | 5.7 | POOR |
| Structured Data | **8/100** | 10% | 0.8 | CRITICAL |
| Platform Optimization | 35/100 | 10% | 3.5 | POOR |
| **总分** | | | **24.5 → 28** | **CRITICAL** |

#### 5 平台分数

| AI 平台 | 分数 | 主要差距 |
|---|---|---|
| Google AI Overviews | 25/100 | 无结构化数据、无 Q&A 内容、纯目录页 |
| ChatGPT 搜索 | 18/100 | 无 Wikipedia/Wikidata、无 schema、403 封非浏览器 UA |
| Perplexity AI | 20/100 | 无 Reddit、无原创研究、无引用 |
| Google Gemini | 12/100 | 无 YouTube 频道、无 Knowledge Panel、无 sameAs |
| Bing Copilot | 28/100 | 无 LinkedIn、无 IndexNow、无 Bing Webmaster Tools |

### 12.3 8 个 Critical Findings 完整展开

#### Finding 1：服务器 403 拦截非浏览器 UA（Critical）

**证据**：所有 fetch 尝试（Python requests、WebFetch 工具）返回 HTTP 403 Forbidden。仅类浏览器请求和 Google 爬虫看起来工作。

**影响**：GPTBot、ClaudeBot、PerplexityBot 和大多数 AI 爬虫**收到 403 无法索引**。站对 5 个 AI 平台中 4 个**完全不可见**——只有 Google AIO 通过 Googlebot 可能拿到数据。

**严重度**：CRITICAL——单这一个问题让站对 80% AI 平台不可见。

**修复**：审查服务器配置（很可能是 WordPress 安全插件如 Wordfence、Sucuri 或 Cloudflare 规则封非浏览器 UA）。把 14 个 AI 爬虫 UA 加白名单。

**工时**：2–4 小时（取决于托管设置）

**教学价值**：这是 80% WordPress 站的隐疾。课程里要专门讲这一类——很多客户的"GEO 不行"根本不是优化问题，而是**服务器在屏蔽 AI 爬虫**。检测方法：用 Python 或 curl 抓 `https://domain.com`，对比浏览器抓的。403 = 服务器有问题。

#### Finding 2：零 Schema 标记（Critical）

**证据**：Google 搜 `site:electron-srl.com schema.org OR json-ld` 返回零结果。Google SERP 无富片段。

**影响**：AI 系统无法把 Electron Srl 识别为独立实体。无 Organization、Product、LocalBusiness、EducationalOrganization。**品牌无机器可读身份**。

**严重度**：CRITICAL

**修复**：实施 Organization schema（含 sameAs）、Product schemas 每个实验类目、EducationalOrganization schema。

**工时**：4–8 小时

#### Finding 3：无实体存在（Wikipedia / Wikidata / Knowledge Panel）（Critical）

**证据**：无 Wikipedia 文章。无 Wikidata 条目。无 Google Knowledge Panel。**品牌名与多个其它意大利 "Electron Srl" 公司共享**（Sovico、Lodi、Tuscany），导致实体混淆。

**影响**：**ChatGPT 引用的 47.9% 来自 Wikipedia**。无实体消歧义，AI 系统无法区分这家 Electron Srl 与其它的。

**严重度**：CRITICAL

**修复**：创建 Wikidata 实体（Q-code）→ Wikipedia stub（如 notable）→ 主张 Google Knowledge Panel。Schema 加 sameAs 链。

**工时**：2–4 周

#### Finding 4：无 LinkedIn 公司页（High）

**证据**：搜索返回 "Electron Mec Srl"、"Electron Electronics UK"、"Electron Lighting"——但**不是** Electron Srl Chiaravalle 教育设备。

**影响**：LinkedIn 是 Bing Copilot 和 ChatGPT（via Bing）的关键信号。无 LinkedIn 页 = 公司无专业实体信号。

**严重度**：HIGH

**修复**：创建并优化 LinkedIn 公司页，含完整细节、sameAs 链。

**工时**：2 小时设置 + 持续维护

#### Finding 5：无 YouTube 频道（High）

**证据**：搜 "Electron Srl educational equipment" 等查询零 YouTube 结果。

**影响**：对一家**制造视觉化培训设备**（实验室、CNC 系统、电子板）的公司，这是巨大错失。Google Gemini 重度依赖 YouTube。产品演示会非常 citable。

**严重度**：HIGH

**修复**：创建 YouTube 频道。录产品演示、实验室搭建指南、培训教程。

**工时**：持续（战略性）

#### Finding 6：无 llms.txt（Medium）

**证据**：Fetch electron-srl.com/llms.txt 返回 403。

**影响**：AI 爬虫无站结构指南。**仅 ~12% 的站有 llms.txt——早期采用是竞争优势**。

**严重度**：MEDIUM

**修复**：生成并部署含产品类目、about 信息、关键页的 llms.txt。

**工时**：30 分钟

#### Finding 7：目录式内容——零 citability（High）

**证据**：从 Google 索引描述看，所有页都是产品目录式：**"Various modules to show and experiment with circuits and principles in the field of..."**——重复、通用、不回答具体问题。

**影响**：AI 系统引用直接回答问题的内容（134–167 词块）。目录描述**永远不会被引用**。

**严重度**：HIGH

**修复**：在产品页加 Q&A 区："What is the Electricity Lab used for?"、"How does the Automation Training System work?"、"What makes Electron Srl different from competitors?"

**工时**：2–3 天（前 10 页）

#### Finding 8：品牌名混淆——实体消歧义需要（High）

**证据**：Google 返回多家 "Electron Srl" 公司：Chiaravalle（教育）、Lodi（电子元件）、Massa（工业）、Tuscany（自动化）。DNB 显示 3+ 不同公司画像。

**影响**：AI 系统难区分实体。被问 "Electron Srl" 时，AI 可能引用错误公司或拒答因模糊。

**严重度**：HIGH

**修复**：一致使用全名 "Electron Srl Educational Equipment"。创建含精确标识符（P1566 GeoNames、P3500 Ringgold ID）的 Wikidata。Organization schema 加精确地址、foundingDate、description。

**工时**：1 周

### 12.4 11 个平台的品牌存在扫描表

| 平台 | 存在? | 状态 | AI 权重 |
|---|---|---|---|
| Wikipedia | ❌ | 无文章 | 极高（ChatGPT 引用 47.9%） |
| Wikidata | ❌ | 无条目 | 极高（机器可读） |
| LinkedIn | ❌ | 未找到公司页 | 高（Bing Copilot 信号） |
| YouTube | ❌ | 无频道 | 高（Gemini 信号） |
| Facebook | ✅ | facebook.com/electronsrl | 中 |
| Reddit | ❌ | 无提及 | 极高（Perplexity 引用 46.7%） |
| Google Knowledge Panel | ❌ | 未主张 | 高 |
| CNOS-FAP | ✅ | cnos-fap.it/en/azienda/electron-srl | 中（教育垂直） |
| Energy-Xprt | ✅ | energy-xprt.com 列表 | 低 |
| RocketReach | ✅ | 公司画像存在 | 低 |
| D&B（Dun & Bradstreet） | 部分 | 多条目（实体混乱） | 中 |

**Brand Authority 分：15/100**——仅 Facebook 和细分目录。在对 AI 引用至关重要的平台上零存在。

### 12.5 竞品对比（关键的"行业基准"教学）

| 竞品 | 估算 GEO | Wikipedia | YouTube | LinkedIn | Schema |
|---|---|---|---|---|---|
| Festo Didactic（DE） | ~72/100 | ✅ | ✅（1000+ 视频） | ✅ | ✅ |
| Lucas-Nülle（DE） | ~65/100 | ❌ | ✅ | ✅ | ✅ |
| National Instruments（US） | ~80/100 | ✅ | ✅（5000+ 视频） | ✅ | ✅ |
| **Electron Srl（IT）** | **28/100** | ❌ | ❌ | ❌ | ❌ |

**关键洞察**：Electron Srl 有同等的产品力和经验，但**零 AI 基础设施**。German/US 竞品已经在 AI 引擎里建立了存在感，**每过一天 Electron Srl 都在丢市场份额**。

**意大利本土同类竞品**：经核实**全部都和 Electron Srl 一样弱**——这是一个**首吃螃蟹的机会**。谁先在意大利教育设备领域投入 GEO，谁拿走整个 AI 流量。

### 12.6 三阶段路线图：28 → 43 → 63 → 86

#### 第一阶段（第 1 个月）：Quick Wins → 43/100（+15 分）

| # | 动作 | 工时 | GEO 提升 | 受益平台 |
|---|---|---|---|---|
| 1 | **修复服务器 403**——加白名单所有 14 个 AI 爬虫 UA | 2–4h | **+6** | 全部 5 个 |
| 2 | 创建 llms.txt 在 electron-srl.com/llms.txt | 30min | +2 | ChatGPT、Perplexity |
| 3 | 加 Organization JSON-LD 到首页 | 2h | +4 | 全部 5 个 |
| 4 | 加 sameAs 链（Facebook + 未来 profile） | 30min | +2 | 全部 5 个 |
| 5 | 给所有页加发布/更新日期 | 1h | +1 | Google AIO |

**预期**：28 → 43/100（+15 分）

#### 第二阶段（第 2–3 个月）：Medium-term → 63/100（+20 分）

| # | 动作 | 工时 | GEO 提升 |
|---|---|---|---|
| 1 | 创建 LinkedIn 公司页 | 2h+持续 | +3 |
| 2 | **重写 Top 5 产品页**含 Q&A 结构 + 直接答案块 | 3 天 | **+5** |
| 3 | 加 E-E-A-T 信号：团队页、35 年经验、资质、案例 | 1 天 | +4 |
| 4 | 实施 Product 和 EducationalOrganization schemas | 2 天 | +4 |
| 5 | 注册 Bing Webmaster Tools + IndexNow | 1h | +2 |
| 6 | 给工程师创建 author/expert 页 | 1 天 | +2 |

**预期**：43 → 63/100（+20 分）

#### 第三阶段（第 4–6 个月）：Strategic → 86/100（+23 分）

| # | 动作 | 工时 | GEO 提升 |
|---|---|---|---|
| 1 | **Wikidata 实体（Q-code）+ Wikipedia 可行性评估** | 2–4 周 | **+8** |
| 2 | YouTube 频道：产品演示、实验室搭建、CNC 教程 | 持续 | +5 |
| 3 | Reddit 真实参与（r/ElectricalEngineering、r/education、r/arduino） | 持续 | +3 |
| 4 | 行业引用：IEEE 教育合作、教育机构背书 | 持续 | +4 |
| 5 | 70+ 国家案例研究（原创可量化数据） | 1–2 月 | +3 |

**预期**：63 → 86/100（+23 分）

#### 整体路径
```
Month 0: 28/100 (Critical)      ← 起点
Month 1: 43/100 (Poor)          ← Quick Wins
Month 3: 63/100 (Fair)          ← Medium-term
Month 6: 86/100 (Excellent)     ← Strategic
```

### 12.7 ROI 估算（提案中给客户的数字）

#### 4 档情景对比

| 情景 | 6 个月分数 | AI 流量增量 | 估算月增值 |
|---|---|---|---|
| 无作为 | 30/100 | +5%（自然增长） | €500 |
| Basic 套餐 | 43/100 | +30–40% | €3,000–€4,000 |
| Standard 套餐 | 55/100 | +60–90% | €6,000–€9,000 |
| **Premium 套餐** | **80+/100** | **+150–200%** | **€12,000–€20,000** |

#### Premium 投资回收

| 项 | 值 |
|---|---|
| 月投资 | €9,500 |
| 12 月投资 | €114,000 |
| AI 流量估算月增值（月 6+） | €12,000–€20,000 |
| 年值（保守） | €96,000–€160,000 |
| **回收期** | **8–12 月** |

**假设依据**：
- 基于 70+ 国家 B2B 估算自然流量
- AI 搜索预计 2026 年底驱动 25–40% 自然发现
- AI 流量转化是传统自然流量的 4.4 倍
- 保守估算——实际可能更高
- B2B 教育设备单条合格 lead 价值 €5,000–€50,000+

### 12.8 这个案例的教学价值（每节课至少讲一次）

1. **诊断顺序很重要**：先发现"403 封爬虫"再谈优化——前者解决前后者全白搭
2. **行业基准很有说服力**：客户看到自己 28、竞品 72，立刻明白严重性
3. **路径要分阶段**：客户最怕"6 个月才看效果"，所以要 Month 1 就有可见提升
4. **ROI 要具体**：泛泛说"提升 GEO" vs 具体说"8–12 月回本"——客户决策完全不同
5. **首吃螃蟹机会**：意大利本土零竞争 = 客户有强烈紧迫感
6. **真实数据带来信任**：47.9% / 46.7% / 0.737 这些数字是议价的硬通货

---

## 13. 30 / 90 / 365 天落地路线图（通用版）

### 13.1 第一周：紧急止血

任何 GEO 项目第一周必做的 7 件事：

| # | 动作 | 工时 | 优先级 |
|---|---|---|---|
| 1 | **检测服务器 403 / UA 拦截**——用 curl 测各 AI 爬虫 UA 是否能访问 | 1h | Critical |
| 2 | 修复 robots.txt——显式 Allow 所有 14 个 AI 爬虫 + 引用 sitemap | 30min | Critical |
| 3 | 加 Content-Signal 指令到 robots.txt | 15min | Medium |
| 4 | 部署 llms.txt | 30min | High |
| 5 | 给首页加 Organization JSON-LD 含 sameAs | 2h | Critical |
| 6 | 给所有内容页加可见的 datePublished + dateModified | 1h | High |
| 7 | 注册 Bing Webmaster Tools + 部署 IndexNow | 1h | High |

**预期**：基础分提升 10–15。

### 13.2 第一个月：地基扎实

| 周 | 主题 | 主要动作 |
|---|---|---|
| Week 1 | 紧急止血 | 上述 7 件事 |
| Week 2 | Schema 工程 | 完整 Organization + Person（作者）+ 业务类型特定 schema |
| Week 3 | 内容审计 | 用 citability 算法跑 Top 20 页，标记需重写的 |
| Week 4 | 首批重写 | Top 5 页按 134–167 词法则 + 答案前置改写 |

**预期**：基础分 → 50+。

### 13.3 第一个季度：内容 + 品牌建设

| 月 | 主题 | 主要动作 |
|---|---|---|
| Month 1 | 地基 | 见上 |
| Month 2 | 内容深耕 | Top 20 页全部 GEO 改写；加 FAQ 区块；加 E-E-A-T 信号（作者页、资质、编辑标准） |
| Month 3 | 品牌起步 | 创建 LinkedIn 完整公司页 + 高管 thought leadership；启动 YouTube（首批 5 个视频）；评估 Wikipedia notability + 创建 Wikidata |

**预期**：60+。

### 13.4 半年：进入良好状态

| 月 | 主题 | 主要动作 |
|---|---|---|
| Month 4 | YouTube + 行业引用 | YouTube 月发 4 个；申请行业奖项 / 媒体采访；尝试在 Wikipedia 相关词条做来源引用 |
| Month 5 | Reddit + 社区 | 高管在相关 subreddit 真实参与；做一次 AMA（如适合） |
| Month 6 | 原创研究 | 发布原创数据报告（行业调查 / 自有数据分析）→ 喂 Wikipedia + 媒体引用 + Reddit 讨论 |

**预期**：75+。

### 13.5 一年：进入卓越

| 月 | 主题 | 主要动作 |
|---|---|---|
| Month 7–9 | Wikipedia 词条争取 | 通过媒体 + 第三方引用建立 notability；让外部 Wikipedia 编辑撰写词条；持续监控防被删 |
| Month 10–12 | 持续运营 | 月度 GEO 审计；季度 schema 全站健康检查；持续 YouTube + Reddit 真实运营；新原创研究 |

**预期**：85+。

### 13.6 课程拓展：年度 GEO 运维节奏

```
每月：
- 跑全站 GEO 审计 + 月度 delta 报告
- 重写新发布内容前用 citability 算法验证
- 检查 Reddit / Wikipedia 的负面提及并响应
- 更新 llms.txt（新内容 / 新页面）

每季度：
- Schema 全站健康检查（看是否有 JS 注入风险、废弃 schema）
- 竞品 GEO 对比报告
- 客户 / 自家月度业务表现复盘（AI 流量贡献占比）

每年：
- 完整重审权重（AI 平台演变可能改权重分布）
- robots.txt 重审（新 AI 爬虫出现）
- E-E-A-T 信号大体检（作者更新、资质更新）
```

---

## 14. 教学补充：误区与边界

### 14.1 GEO 不是替代 SEO，是包含 SEO

技术地基（HTTPS / sitemap / Core Web Vitals / 移动优化）仍然必做。GEO 在 SEO 之上加了 5 块新工程：段落优化、品牌建设、AI 爬虫管理、跨平台 sameAs、llms.txt。

**不要给学员一种"SEO 已死"的错觉**——AIO 92% 引用来自 top 10 自然搜索结果，传统排名仍然是入场券。

### 14.2 E-E-A-T 不是排名因子

它是 Google 给质量评估员的框架。你不能"优化 E-E-A-T 分数"。你能做的是"优化 E-E-A-T 信号的可见性"——让作者真实存在、让数据真的原创、让 HTTPS 部署到位。

### 14.3 高分 ≠ 保证被引用

GEO 总分是**结构条件**的体现，不是结果保证。AI 模型的实际行为还受训练数据、提示措辞、竞争内容影响。把 GEO 分理解成"必要条件"而不是"充分条件"。

**给客户提案时一定要写明这一点**——否则承诺与现实落差会反噬。

### 14.4 确定性评分 vs LLM 评估的区别

| 类别 | 性质 | 可重复性 |
|---|---|---|
| Citability（脚本化的段落分） | 确定性 | 同输入同输出 |
| llms.txt 校验 | 确定性 | 同上 |
| robots.txt 解析 | 确定性 | 同上 |
| 安全头检测 | 确定性 | 同上 |
| Brand / E-E-A-T / Schema / Platform | LLM 判断 | 两次结果可能略有差异 |
| Technical（部分） | 混合 | 大部分确定，少量评估 |

教课时要明确说出哪些数字是机器算的，哪些是 AI 评估的。

### 14.5 schema 校验是结构性，不是语义性

JSON-LD 通过校验只意味着"语法正确 + 类型正确 + 必填字段在"。它**不验证内容真实性**——你 schema 里写公司创立于 1991 年，校验器不会去查工商档案。

### 14.6 Reddit / YouTube 不能造假

这是 GEO 最反"传统 SEO 思维"的地方。Reddit 用户极度敏感，YouTube 算法识别 spam 极强。**只能真实运营**。一旦被识别为营销账号，反而是负向信号。

### 14.7 llms.txt 是新兴标准，不是强制标准

目前没有 AI 平台官方承诺会按 llms.txt 排序内容。它的价值在于**先发布、零成本、未来兑现**。不能把它当成万能钥匙。

### 14.8 Wikipedia 不是想发就能发

Wikipedia 有严格 notability 规则。强行发会被快速删除，留下"曾被删过"的负面记录。**正确顺序**：先有 5+ 篇权威第三方独立媒体报道 → 建 Wikidata（无门槛）→ 评估 Wikipedia 词条可行性 → 让外部编辑（不是你自己）来写。

### 14.9 weights 是观点不是定理

25/20/20/15/10/10 反映了**当前**对 AI 引用机制的理解。当 AI 平台演化（如 Gemini 2 改变 KG 用法、新平台出现），权重要重审。

**给学员的提醒**：永远说"按 X 年的研究 + 行业最佳实践"，不要说"权威定理"。

### 14.10 单平台优化的边际效益递减

**前期投入巨大、后期边际下降**——这是所有 GEO 项目的共同规律：

- 0–40 分阶段：每个动作都能带来 +3–8 分
- 40–60 分阶段：每个动作 +2–5 分
- 60–80 分阶段：每个动作 +1–3 分
- 80+ 阶段：每个动作 +0.5–1.5 分

**含义**：客户报价时不能用"线性提升"模型。从 80 → 90 比从 30 → 40 难得多。

### 14.11 内容更新 vs 新内容的优先级

| 情景 | 优先级 |
|---|---|
| 现有 Top 20 流量页 citability < 50 | **优先重写** |
| 现有 Top 20 流量页 citability 60+ | 保留 |
| 主题领域有空缺 | 创建新内容 |
| 现有内容数 > 3 个月未更新 + 时间敏感话题 | 更新 |

新手常犯的错误是**只想着"加内容"**——其实改老内容的 ROI 通常更高。

### 14.12 12 个反直觉点（值得在课里强调）

1. **CSR 单页应用对 AI 爬虫等于不存在**——技术不解决，前面所有内容功夫白费
2. **YouTube 0.737，外链 0.266**——把外链建设的预算挪到视频上 ROI 更高
3. **Reddit 必须真实运营**——这是唯一一个"假装做"会反噬的渠道
4. **作者要写成 Person schema 对象**——字符串作者名几乎没用
5. **段落起手不要用 It / They**——AI 抽取一段时不带上下文
6. **HowTo schema 已死**——别教学员加这个
7. **FID 已被 INP 取代**——别教学员看 FID 数据
8. **ChatGPT 和 AIO 重叠率只有 11%**——不存在"一招打所有平台"的玩法
9. **Wikidata 优先于 Wikipedia**——前者无门槛，后者有强 notability 规则
10. **llms.txt 现在做 = 零成本占坑**——未来兑现，不要等"标准成熟"
11. **Google 已完全转 mobile-first crawl（2024 年 7 月）**——desktop-only 站等于不存在
12. **Google-Extended 封不影响 Googlebot**——封了只影响 Gemini 训练数据

---

## 15. 商业化路径：GEO 服务定价与流程

### 15.1 GEO Agency 的服务套餐结构（参考定价）

参考 electron-srl.com 案例的真实定价（欧洲 B2B 市场）：

#### Basic — €2,500/月

**适合**：score 61–75 的站，需要定向改进。

**包含**：
- 季度完整 GEO 审计（4 次/年）
- 季度报告 + score tracking
- Schema.org 实施（Organization + 关键页）
- AI 爬虫访问优化（robots.txt）
- llms.txt 创建与维护
- 邮件支持（48 小时内回复）

**6 个月预期**：+10–20 分
**最短合约**：6 个月

#### Standard — €5,000/月

**适合**：score 40–60 的站，需要月度结构性工作。

**包含**（Basic + 以下）：
- 月度完整 GEO 审计 + delta 报告
- 月度战略会议（60 分钟）
- 内容 citability 优化（最多 10 页/月）
- 品牌权威建设（Wikipedia、Wikidata、LinkedIn）
- 平台特定优化（Google AIO、ChatGPT、Perplexity）
- E-E-A-T 改进（作者页、资质、新鲜度）
- Slack 频道沟通（24 小时内回复）

**6 个月预期**：+25–40 分
**最短合约**：6 个月

#### Premium — €9,500/月

**适合**：score 0–40 含关键问题，或竞争激烈行业。

**包含**（Standard + 以下）：
- 双周战略会议
- 技术 SEO 实施支持（CWV、SSR、速度）
- 完整内容策略 + 制作（4 篇优化文章/月）
- 主动品牌建设（Reddit、YouTube、行业引用）
- 竞品监控与响应
- 专属 account manager
- 优先支持（4 小时内回复）

**6 个月预期**：+40–60 分
**最短合约**：12 个月

### 15.2 各套餐适用判断矩阵

| 客户当前 score | 行业竞争度 | 推荐套餐 |
|---|---|---|
| 70+ | 任何 | Basic（保持 + 微调） |
| 50–70 | 低 | Basic |
| 50–70 | 中高 | Standard |
| 30–50 | 任何 | Standard |
| 0–30 | 低 | Standard |
| 0–30 | 中高 | **Premium**（必须强干预） |

### 15.3 ROI 沟通模板（给提案用）

```
当前情况：
- GEO 分数：[X]/100（[评级]）
- AI 平台覆盖：[X]/5 个平台被引用
- 与竞品差距：[竞品 GEO 分] vs [你的分]

如果不作为：
- 6 个月预期：[X+5]/100（自然增长）
- AI 流量增长：约 +5%
- 月增值估算：€[Y]

选 [推荐套餐]：
- 6 个月预期：[X+25 至 X+50]/100
- AI 流量增长：[+30% 至 +200%]
- 月增值估算：€[Y × 6 至 Y × 40]
- 投资回收期：[8–12] 个月

行业对标：
- 早期采用者优势仍开窗
- 竞品 [A]（GEO [X]）已开始捕获 AI 流量
- 不作为 = 持续丢市场份额
```

### 15.4 客户全生命周期：5 阶段流程

| 阶段 | 动作 | 输出 |
|---|---|---|
| 1. Prospect（潜在客户） | 跑 quick audit（60 秒） | quick audit MD |
| 2. Qualify（资格） | 跑 full audit | full audit MD |
| 3. Pitch（提案） | 生成提案 + ROI 估算 | proposal MD/PDF |
| 4. Engage（执行） | 月度审计 + 月度 delta 报告 + 工程实施 | 每月 delta MD |
| 5. Retain（续约） | 季度战略复盘 + 续约提案 | 续约报告 |

### 15.5 月度 delta 报告（Engage 阶段核心交付物）

每月给客户一份"上月做了什么、分数怎么变了、下月做什么"的报告：

```markdown
# GEO 月度报告：[域名] — [年-月]

## 分数 delta
- 上月：[X]/100
- 本月：[Y]/100
- 变化：+[Z]（[评级转换]）

## 6 维变化
| 维度 | 上月 | 本月 | 变化 |
|---|---|---|---|
| Citability | [X] | [Y] | +[Z] |
| Brand | [X] | [Y] | +[Z] |
| ...

## 本月完成
1. [动作] — 影响：+[Z] 分
2. [动作] — 影响：+[Z] 分

## 下月计划
1. [动作] — 预期：+[Z] 分
2. [动作] — 预期：+[Z] 分

## 业务指标（如能拿到）
- AI 引荐流量：[N] sessions（vs 上月 +[X]%）
- AI 来源转化：[N] conversions
```

### 15.6 课程教学价值

**讲到这部分时学员最关心两件事**：
1. "我能不能靠这个赚钱？"——答案是能，B2B 市场愿意付 €2.5K–€10K/月
2. "我从哪里找客户？"——任何 GEO 分数 < 60 的 B2B 站都是潜在客户

**给学员的练习作业**：
- 选 5 家自己行业的公司，跑 quick audit
- 选其中分最低的 1 家，写完整 audit + proposal
- 不需要真的发——目的是**亲手过一遍商业流程**

---

## 16. 关键术语速查表

### 核心概念

| 术语 | 定义 |
|---|---|
| **GEO** | Generative Engine Optimization，生成式引擎优化 |
| **AEO** | Answer Engine Optimization，部分行业等同 GEO |
| **Citability** | 段落被 AI 系统抽取并整段引用的难易度 |
| **134–167 词法则** | AI 系统优先抽取的段落黄金长度（Bortolato 2025） |
| **答案前置（Answer-first）** | 段落开头 1–2 句直接给出答案，不铺垫 |
| **Self-Containment** | 段落脱离上下文也能读懂的属性 |
| **Statistical Density** | 段落内具体数字密度 |

### Schema 相关

| 术语 | 定义 |
|---|---|
| **JSON-LD** | JSON Linked Data，Schema.org 推荐的结构化数据格式 |
| **sameAs** | Schema.org 属性，把不同平台的同一实体链接起来——GEO 单点最大杠杆 |
| **speakable** | Schema.org 属性，标记适合语音/AI 助手朗读的内容片段 |
| **knowsAbout** | Schema.org 属性，标记实体的专长领域 |
| **@id** | Schema.org 实体的站内固定锚点，用于跨 schema 引用同一实体 |
| **@graph** | 在一个 JSON-LD 块中含多个 schema 的模式 |

### E-E-A-T 与内容质量

| 术语 | 定义 |
|---|---|
| **E-E-A-T** | Experience / Expertise / Authoritativeness / Trustworthiness |
| **YMYL** | Your Money Your Life——健康/金融/法律/安全等高风险话题 |
| **Topical Authority** | 主题权威——站对一个主题的综合覆盖深度 |
| **Flesch Reading Ease** | 可读性指数，60–70 是 web 内容最佳区 |
| **Content Coverage** | 内容覆盖度——citability ≥ 70 的段落占比 |

### 技术 SEO

| 术语 | 定义 |
|---|---|
| **SSR / SSG / CSR** | 服务端渲染 / 静态生成 / 客户端渲染 |
| **CWV** | Core Web Vitals |
| **LCP** | Largest Contentful Paint，最大内容绘制 |
| **INP** | Interaction to Next Paint——2024 年取代 FID 的 CWV |
| **CLS** | Cumulative Layout Shift，累积布局偏移 |
| **TTFB** | Time to First Byte，首字节时间 |
| **HSTS** | HTTP Strict Transport Security，强制 HTTPS |
| **CSP** | Content Security Policy |
| **Mobile-First Crawling** | Google 自 2024-07 起完全用移动 Googlebot 抓取 |
| **IndexNow** | 实时索引协议，Bing/Yandex/Seznam/Naver 支持 |

### AI 爬虫与新基建

| 术语 | 定义 |
|---|---|
| **GPTBot** | OpenAI 训练 + ChatGPT 搜索爬虫 |
| **ClaudeBot** | Anthropic Claude 爬虫 |
| **PerplexityBot** | Perplexity AI 爬虫 |
| **Google-Extended** | Google Gemini 训练爬虫（不影响 Googlebot） |
| **OAI-SearchBot** | OpenAI 搜索专用爬虫 |
| **llms.txt** | 网站根目录的 markdown 文件，告诉 AI 爬虫优先读什么（Jeremy Howard 2024 提出） |
| **llms-full.txt** | llms.txt 的详尽版本 |
| **Content-Signal** | IETF 草案，在 robots.txt 里声明内容用途允许度 |

### 实体与品牌

| 术语 | 定义 |
|---|---|
| **Wikipedia** | 维基百科，AI 训练数据基石 |
| **Wikidata** | 维基百科的结构化数据库，无 notability 门槛 |
| **Q-code** | Wikidata 实体唯一标识符（如 Q12345） |
| **Knowledge Graph** | Google 的实体图谱，触发 Knowledge Panel |
| **Knowledge Panel** | Google 搜索结果右侧实体卡片 |
| **Entity Resolution** | 实体识别——AI 判断"这是哪个实体"的过程 |
| **Entity Disambiguation** | 实体消歧义——区分同名实体 |

### AI 平台

| 术语 | 定义 |
|---|---|
| **AIO** | Google AI Overviews |
| **GBP** | Google Business Profile |
| **GMC** | Google Merchant Center |
| **BWT** | Bing Webmaster Tools |
| **Featured Snippet** | Google 答案精选片段，与 AIO 70% 优化重叠 |

---

## 17. 参考资料与数据来源

### 学术研究

- **Princeton + Georgia Tech + IIT Delhi（2024）**：GEO 优化使 AI 回答可见度提升 30%–115%；定义模式 +110%；统计 +40%；权威引语 +115%（特定类别）
- **Bortolato（2025）**：AIO 段落分析，134–167 词最优长度
- **Princeton（2024）**：流畅度优化 +30% 全查询；来源引用使 Perplexity/ChatGPT 引用率 +20–25%

### 行业研究

- **Ahrefs（2025-12）**：75,000 品牌研究，YouTube 提及与 AI 引用相关系数 0.737，DR/外链 0.266
- **SparkToro（2025）**：AI 引荐流量 +527% 同比增长（2025 年 1–5 月）
- **Profound（2025）**：corroborating 平台引用研究
- **Terakeet（2025）**：corroborating 平台引用研究
- **Gartner**：预测 2028 自然搜索流量 -50%
- **HubSpot（2025 年末）**：AI 流量转化是自然搜索的 4.4 倍

### 平台官方文档

- **Schema.org**：完整 schema 类型与属性 - https://schema.org
- **Google Search Central**：搜索文档与 AIO 指南
- **Google Quality Rater Guidelines（2025-12 更新）**：E-E-A-T 扩展到所有竞争查询
- **Google（2025-12）**：JS 注入 schema 延迟处理警告
- **Bing Webmaster Tools 文档**：IndexNow 协议
- **OpenAI**：GPTBot 和 OAI-SearchBot 爬虫文档
- **Anthropic**：ClaudeBot 文档
- **Perplexity AI**：PerplexityBot 文档

### 关键引用比例

- **ChatGPT 引用源 Wikipedia 占 47.9%**
- **ChatGPT 引用源 Reddit 占 11.3%**
- **Perplexity 引用源 Reddit 占 46.7%**
- **AIO 92% 引用来自 top 10 自然搜索；47% 来自 5 名以下**
- **AIO 与 Featured Snippet 优化 70% 重叠**
- **ChatGPT 和 AIO 引用域重叠仅 11%**
- **每答案引用源数**：ChatGPT 2–4，Perplexity 5–15，Copilot 3–5

### 标准与协议

- **llms.txt**：Jeremy Howard 2024-09 提出，2025–2026 采用扩展中
- **IETF `draft-romm-aipref-contentsignals`**：robots.txt 的 Content-Signal 指令
- **IndexNow**：Bing 主导的实时索引协议
- **Schema.org**：W3C 工作组维护

### 重要时间节点

- 2023-08：FAQPage 富片段限制为政府/卫生站
- 2023-09：HowTo 富片段从 Google 移除
- 2024-03：INP 替代 FID 成为 CWV
- 2024-07：Google 完全转 mobile-only crawling
- 2024-09：llms.txt 标准提出
- 2024 全年：Google 与 Reddit 签 $60M/年数据授权
- 2025-12：E-E-A-T 扩展到所有竞争查询；JS 注入 schema 延迟处理警告
- 2025-12：Ahrefs 发布 75K 品牌研究

### 工具与项目

- **geo-seo-claude 项目**：本文档的源材料 - https://github.com/zubair-trabzada/geo-seo-claude

---

## 文档说明

本方法论文档基于 `geo-seo-claude` 项目（commit 5d8c0af，2026-05-01）的源材料系统提炼。

源材料：
- 主 SKILL 文件 `geo/SKILL.md`
- 14 个子 SKILL 文档（`skills/geo-*/SKILL.md`）
- 5 个 agent 文件（`agents/geo-*.md`）
- 4 个 Python 脚本（`scripts/*.py`）
- 6 个 schema 模板（`schema/*.json`）
- 完整审计案例（`examples/electron-srl.com-*`）
- 项目架构文档（`docs/architecture.md`、`docs/scoring-methodology.md`）

文档特点：
- 不绑定任何工具实现
- 所有阈值带出处（论文 / 行业研究 / 官方文档）
- 所有评分公式可复现
- 所有 schema 模板可直接使用
- 包含完整真实案例（28 → 86 分路径）
- 包含商业化定价与流程

适用场景：
- 课程教学（建议拆为 10–12 节）
- 客户咨询的方法论参考
- GEO agency 的内部培训资料
- 自己网站的 GEO 改造手册

最后更新：2026-05-01


















