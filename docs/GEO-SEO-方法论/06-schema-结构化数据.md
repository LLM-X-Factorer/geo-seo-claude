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

