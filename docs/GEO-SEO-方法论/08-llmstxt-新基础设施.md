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

