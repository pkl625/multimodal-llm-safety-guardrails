# 多模态大模型护栏产品多维度对比分析 | Product Comparison Matrix

<p align="center">
  <a href="catalog.md">📋 产品目录 | Product Catalog</a>
</p>

> 最后更新：2026年4月 | Last Updated: April 2026
>
> 本文档建立系统性的评估框架，对主流护栏产品进行多维度量化对比。
>
> This document establishes a systematic evaluation framework for quantitative comparison of mainstream guardrail products.

---

## 目录

- [评估维度框架](#评估维度框架)
- [功能维度对比](#功能维度对比)
- [性能维度对比](#性能维度对比)
- [工程维度对比](#工程维度对比)
- [成本维度对比](#成本维度对比)
- [综合评分与选型建议](#综合评分与选型建议)

---

## 评估维度框架

### 维度分类

```
评估维度体系
│
├── 功能维度 (Functionality)
│   ├── 支持模态
│   ├── 检测类型
│   ├── 自定义能力
│   └── 集成能力
│
├── 性能维度 (Performance)
│   ├── 检测准确率
│   ├── 误报率
│   ├── 延迟
│   └── 吞吐量
│
├── 工程维度 (Engineering)
│   ├── 部署难度
│   ├── 扩展性
│   ├── 社区活跃度
│   └── 文档质量
│
└── 成本维度 (Cost)
    ├── 许可模式
    ├── API定价
    └── 计算资源
```

---

## 功能维度对比

### 1. 支持模态

| 产品 | 文本 | 图像 | 音频 | 视频 | 评分 |
|------|------|------|------|------|------|
| **Llama Guard 3** | ✅ | ⚠️ | ❌ | ❌ | ⭐⭐⭐ |
| **NeMo Guardrails** | ✅ | ⚠️ | ❌ | ❌ | ⭐⭐⭐ |
| **Guardrails AI** | ✅ | ❌ | ❌ | ❌ | ⭐⭐ |
| **LLM Guard** | ✅ | ❌ | ❌ | ❌ | ⭐⭐ |
| **Azure Content Safety** | ✅ | ✅ | ❌ | ❌ | ⭐⭐⭐⭐ |
| **OpenAI Moderation** | ✅ | ⚠️ | ❌ | ❌ | ⭐⭐⭐ |
| **Bedrock Guardrails** | ✅ | ⚠️ | ❌ | ❌ | ⭐⭐⭐ |
| **Enkrypt AI** | ✅ | ✅ | ✅ | ❌ | ⭐⭐⭐⭐⭐ |

> ⚠️ 表示有限支持（部分类别或需额外配置）

### 2. 检测类型覆盖

| 产品 | 毒性 | 偏见 | PII | 注入 | 幻觉 | 越狱 | 自定义 |
|------|------|------|-----|------|------|------|--------|
| **Llama Guard 3** | ✅ | ✅ | ❌ | ✅ | ❌ | ✅ | ✅ |
| **NeMo Guardrails** | ✅ | ⚠️ | ✅ | ✅ | ✅ | ✅ | ✅ |
| **Guardrails AI** | ✅ | ✅ | ✅ | ✅ | ✅ | ⚠️ | ✅ |
| **LLM Guard** | ✅ | ✅ | ✅ | ✅ | ✅ | ⚠️ | ✅ |
| **Azure Content Safety** | ✅ | ❌ | ❌ | ✅ | ✅ | ✅ | ✅ |
| **OpenAI Moderation** | ✅ | ✅ | ❌ | ❌ | ❌ | ⚠️ | ❌ |
| **Bedrock Guardrails** | ✅ | ❌ | ✅ | ⚠️ | ❌ | ⚠️ | ✅ |
| **Enkrypt AI** | ✅ | ✅ | ✅ | ✅ | ⚠️ | ✅ | ✅ |

### 3. 自定义能力

| 产品 | 自定义类别 | 自定义规则 | 模型微调 | 阈值调整 |
|------|------------|------------|----------|----------|
| **Llama Guard 3** | ✅ | ✅ | ✅ | ✅ |
| **NeMo Guardrails** | ✅ | ✅ | ❌ | ✅ |
| **Guardrails AI** | ✅ | ✅ | ❌ | ✅ |
| **LLM Guard** | ✅ | ✅ | ❌ | ✅ |
| **Azure Content Safety** | ✅ | ⚠️ | ❌ | ✅ |
| **OpenAI Moderation** | ❌ | ❌ | ❌ | ❌ |
| **Bedrock Guardrails** | ✅ | ⚠️ | ❌ | ✅ |
| **Enkrypt AI** | ✅ | ✅ | ✅ | ✅ |

---

## 性能维度对比

### 1. 检测性能（基于公开数据）

| 产品 | 准确率 | 召回率 | F1分数 | 误报率 |
|------|--------|--------|--------|--------|
| **Llama Guard 3** | 94% | 96% | 95% | 3% |
| **Prompt Guard** | 99%+ | 99%+ | 99%+ | <1% |
| **Azure Content Safety** | 92% | 94% | 93% | 5% |
| **OpenAI Moderation** | 91% | 93% | 92% | 4% |
| **LLM Guard** | 88% | 90% | 89% | 7% |

### 2. 延迟性能

| 产品 | 文本检测 | 图像检测 | 多模态 | 评分 |
|------|----------|----------|--------|------|
| **Enkrypt AI** | 29ms | 1.37s | - | ⭐⭐⭐⭐⭐ |
| **Azure Content Safety** | 70ms | 290ms | - | ⭐⭐⭐⭐ |
| **Bedrock Guardrails** | 210ms | 1.24s | - | ⭐⭐⭐ |
| **Llama Guard 3 (INT4)** | 2.5s | - | - | ⭐⭐ |
| **OpenAI Moderation** | ~100ms | ~500ms | - | ⭐⭐⭐⭐ |
| **LLM Guard** | 50ms | - | - | ⭐⭐⭐⭐⭐ |
| **Guardrails AI** | 10-50ms | - | - | ⭐⭐⭐⭐⭐ |

### 3. 吞吐量

| 产品 | 单机QPS | 扩展方式 | 评分 |
|------|---------|----------|------|
| **LLM Guard** | 1000+ | 水平扩展 | ⭐⭐⭐⭐⭐ |
| **Guardrails AI** | 500+ | 水平扩展 | ⭐⭐⭐⭐ |
| **Azure Content Safety** | 无限制 | 自动扩展 | ⭐⭐⭐⭐⭐ |
| **OpenAI Moderation** | 无限制 | 自动扩展 | ⭐⭐⭐⭐⭐ |
| **Llama Guard 3** | 30+ | GPU扩展 | ⭐⭐ |

---

## 工程维度对比

### 1. 部署难度

| 产品 | 部署复杂度 | 部署时间 | 运维成本 | 评分 |
|------|------------|----------|----------|------|
| **OpenAI Moderation** | 极低 | 5分钟 | 无 | ⭐⭐⭐⭐⭐ |
| **Azure Content Safety** | 低 | 30分钟 | 低 | ⭐⭐⭐⭐⭐ |
| **LLM Guard** | 低 | 1小时 | 中 | ⭐⭐⭐⭐ |
| **Guardrails AI** | 中 | 2小时 | 中 | ⭐⭐⭐ |
| **Bedrock Guardrails** | 低 | 30分钟 | 低 | ⭐⭐⭐⭐⭐ |
| **Llama Guard 3** | 高 | 1天 | 高 | ⭐⭐ |
| **NeMo Guardrails** | 高 | 2天 | 高 | ⭐⭐ |
| **Enkrypt AI** | 中 | 4小时 | 中 | ⭐⭐⭐ |

### 2. 集成能力

| 产品 | OpenAI | Azure | AWS | LangChain | 自定义API |
|------|--------|-------|-----|-----------|-----------|
| **Llama Guard 3** | ✅ | ✅ | ✅ | ✅ | ✅ |
| **NeMo Guardrails** | ✅ | ✅ | ✅ | ✅ | ✅ |
| **Guardrails AI** | ✅ | ✅ | ✅ | ✅ | ✅ |
| **LLM Guard** | ✅ | ✅ | ✅ | ✅ | ✅ |
| **Azure Content Safety** | ✅ | ✅ | ⚠️ | ✅ | ✅ |
| **OpenAI Moderation** | ✅ | ⚠️ | ⚠️ | ✅ | ✅ |
| **Bedrock Guardrails** | ⚠️ | ⚠️ | ✅ | ✅ | ✅ |
| **Enkrypt AI** | ✅ | ✅ | ✅ | ✅ | ✅ |

### 3. 社区与生态

| 产品 | GitHub Stars | 社区活跃度 | 文档质量 | 企业支持 |
|------|--------------|------------|----------|----------|
| **Llama Guard 3** | 5k+ | 高 | 优秀 | Meta官方 |
| **NeMo Guardrails** | 2k+ | 中 | 优秀 | NVIDIA官方 |
| **Guardrails AI** | 6.6k | 高 | 优秀 | 商业支持 |
| **LLM Guard** | 2.5k | 中 | 良好 | Protect AI |
| **Azure Content Safety** | - | - | 优秀 | Microsoft |
| **OpenAI Moderation** | - | - | 优秀 | OpenAI |
| **Bedrock Guardrails** | - | - | 良好 | AWS |
| **Enkrypt AI** | - | 低 | 良好 | Enkrypt |

---

## 成本维度对比

### 1. 许可模式

| 产品 | 开源 | 免费额度 | 付费模式 | 企业版 |
|------|------|----------|----------|--------|
| **Llama Guard 3** | ✅ Apache 2.0 | 无限 | 自托管成本 | ❌ |
| **NeMo Guardrails** | ✅ Apache 2.0 | 无限 | 自托管成本 | ✅ |
| **Guardrails AI** | ✅ Apache 2.0 | 无限 | Pro版订阅 | ✅ |
| **LLM Guard** | ✅ MIT | 无限 | 自托管成本 | ❌ |
| **Azure Content Safety** | ❌ | 5K请求/月 | 按量付费 | ✅ |
| **OpenAI Moderation** | ❌ | 无限 | 免费 | ❌ |
| **Bedrock Guardrails** | ❌ | 无 | 按量付费 | ✅ |
| **Enkrypt AI** | ❌ | 试用 | 企业订阅 | ✅ |

### 2. API定价（每1K请求）

| 产品 | 文本检测 | 图像检测 | 估算月成本(100K请求) |
|------|----------|----------|---------------------|
| **OpenAI Moderation** | 免费 | 免费 | $0 |
| **Azure Content Safety** | $1 | $1 | ~$100 |
| **Bedrock Guardrails** | $0.5 | $0.5 | ~$50 |
| **Enkrypt AI** | 定制 | 定制 | $500+ |
| **LLM Guard** | 自托管 | - | ~$50（计算） |
| **Guardrails AI** | 自托管 | - | ~$50（计算） |

### 3. 计算资源需求

| 产品 | 最低配置 | 推荐配置 | GPU需求 |
|------|----------|----------|---------|
| **Llama Guard 3** | 8GB RAM | 16GB RAM | 可选（INT4） |
| **NeMo Guardrails** | 4GB RAM | 8GB RAM | 无 |
| **Guardrails AI** | 2GB RAM | 4GB RAM | 无 |
| **LLM Guard** | 2GB RAM | 4GB RAM | 无 |
| **Azure Content Safety** | - | - | - |
| **OpenAI Moderation** | - | - | - |
| **Bedrock Guardrails** | - | - | - |
| **Enkrypt AI** | - | - | - |

---

## 综合评分与选型建议

### 综合评分矩阵

| 产品 | 功能 | 性能 | 工程 | 成本 | 综合 | 推荐场景 |
|------|------|------|------|------|------|----------|
| **Llama Guard 3** | 8 | 8 | 6 | 9 | **7.8** | 多语言企业 |
| **NeMo Guardrails** | 8 | 7 | 6 | 8 | **7.3** | 对话应用 |
| **Guardrails AI** | 7 | 9 | 8 | 9 | **8.3** | 结构化输出 |
| **LLM Guard** | 6 | 8 | 8 | 10 | **8.0** | 自托管需求 |
| **Azure Content Safety** | 9 | 8 | 9 | 7 | **8.3** | Azure生态 |
| **OpenAI Moderation** | 6 | 8 | 10 | 10 | **8.5** | 预算有限 |
| **Bedrock Guardrails** | 7 | 7 | 9 | 7 | **7.5** | AWS生态 |
| **Enkrypt AI** | 10 | 9 | 7 | 5 | **7.8** | 高安全需求 |

> 评分范围：1-10，10为最佳

### 选型决策树

```
开始选型
│
├── 预算是否充足？
│   ├── 否 → OpenAI Moderation（免费）
│   └── 是 → 继续
│
├── 是否需要自托管？
│   ├── 是 → 是否需要多语言？
│   │   ├── 是 → Llama Guard 3
│   │   └── 否 → 是否需要结构化验证？
│   │       ├── 是 → Guardrails AI
│   │       └── 否 → LLM Guard
│   └── 否 → 继续
│
├── 使用哪个云平台？
│   ├── Azure → Azure Content Safety
│   ├── AWS → Bedrock Guardrails
│   └── 多云 → 继续
│
├── 是否需要对话控制？
│   ├── 是 → NeMo Guardrails
│   └── 否 → 继续
│
└── 安全要求是否最高？
    ├── 是 → Enkrypt AI
    └── 否 → Guardrails AI / Azure Content Safety
```

### 场景化推荐

#### 场景1: 初创公司MVP
- **推荐**: OpenAI Moderation API
- **理由**: 免费、易用、无需运维
- **成本**: $0

#### 场景2: 企业级SaaS
- **推荐**: Azure Content Safety + Guardrails AI
- **理由**: 企业级可靠性 + 灵活验证
- **成本**: $100-500/月

#### 场景3: 金融/医疗合规
- **推荐**: Enkrypt AI 或 自托管 LLM Guard
- **理由**: 最高安全标准、数据不出境
- **成本**: $500+/月 或 自托管成本

#### 场景4: 多语言内容平台
- **推荐**: Llama Guard 3
- **理由**: 13+语言支持、可定制
- **成本**: 自托管成本

#### 场景5: 对话式AI助手
- **推荐**: NeMo Guardrails
- **理由**: 强大的对话流程控制
- **成本**: 自托管成本 + 开发成本

---

## 对比表格汇总

### 功能对比总表

| 产品 | 模态 | 注入 | PII | 幻觉 | 自定义 | 开源 |
|------|------|------|-----|------|--------|------|
| Llama Guard 3 | 文本+ | ✅ | ❌ | ❌ | ✅ | ✅ |
| NeMo Guardrails | 文本+ | ✅ | ✅ | ✅ | ✅ | ✅ |
| Guardrails AI | 文本 | ✅ | ✅ | ✅ | ✅ | ✅ |
| LLM Guard | 文本 | ✅ | ✅ | ✅ | ✅ | ✅ |
| Azure Content Safety | 文本+图像 | ✅ | ❌ | ✅ | ✅ | ❌ |
| OpenAI Moderation | 文本+ | ⚠️ | ❌ | ❌ | ❌ | ❌ |
| Bedrock Guardrails | 文本+ | ⚠️ | ✅ | ❌ | ✅ | ❌ |
| Enkrypt AI | 全模态 | ✅ | ✅ | ⚠️ | ✅ | ❌ |

### 性能对比总表

| 产品 | 延迟 | 准确率 | 吞吐量 | 扩展性 |
|------|------|--------|--------|--------|
| Llama Guard 3 | 2.5s | 95% | 30 QPS | 中 |
| NeMo Guardrails | 100ms | 90% | 100 QPS | 高 |
| Guardrails AI | 10-50ms | 88% | 500 QPS | 高 |
| LLM Guard | 50ms | 88% | 1000 QPS | 高 |
| Azure Content Safety | 70ms | 93% | 无限 | 极高 |
| OpenAI Moderation | 100ms | 92% | 无限 | 极高 |
| Bedrock Guardrails | 210ms | 90% | 无限 | 极高 |
| Enkrypt AI | 29ms | 95% | 无限 | 极高 |

---

## 更新日志

- **2025-04**: 初始版本，覆盖8个主流产品
- **2025-04**: 添加性能基准数据

---

*本文档数据基于公开资料整理，实际性能可能因使用场景而异*
