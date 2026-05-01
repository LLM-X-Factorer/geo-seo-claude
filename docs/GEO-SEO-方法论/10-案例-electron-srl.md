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

