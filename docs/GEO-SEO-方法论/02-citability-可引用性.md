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

