# 多模态大模型护栏产品全景目录 | Guardrail Products Catalog

<p align="center">
  <a href="comparison_matrix.md">📊 多维度对比 | Comparison Matrix</a>
</p>

> 最后更新：2026年4月 | Last Updated: April 2026
>
> 本文档系统梳理当前主流的多模态大模型护栏产品，包括开源方案和商业服务。
>
> This document systematically reviews mainstream multimodal LLM guardrail products, including open-source solutions and commercial services.

---

## 目录

- [产品概览](#产品概览)
- [开源护栏产品](#开源护栏产品)
- [商业护栏服务](#商业护栏服务)
- [多模态特定方案](#多模态特定方案)
- [快速选型指南](#快速选型指南)

---

## 产品概览

### 分类体系

```
护栏产品生态
│
├── 按部署方式
│   ├── 开源/自托管
│   ├── 云服务API
│   └── 混合部署
│
├── 按支持模态
│   ├── 纯文本
│   ├── 文本+图像
│   ├── 文本+图像+音频
│   └── 全模态
│
└── 按功能定位
    ├── 输入过滤
    ├── 输出过滤
    ├── 输入+输出
    └── 全栈护栏
```

### 产品统计

| 类型 | 数量 | 代表产品 |
|------|------|----------|
| 开源护栏 | 8 | Llama Guard, NeMo Guardrails, Guardrails AI |
| 商业服务 | 6 | Azure Content Safety, OpenAI Moderation, Bedrock Guardrails |
| 专项工具 | 4 | LLM Guard, Prompt Guard, Code Shield |

---

## 开源护栏产品

### 1. Llama Guard 3

**开发商**: Meta AI

**开源协议**: Apache 2.0

**GitHub**: [facebookresearch/PurpleLlama](https://github.com/facebookresearch/PurpleLlama)

#### 产品定位
Llama Guard 3是Meta推出的模块化安全分类器，基于Llama 3 8B架构，专门用于筛查LLM的输入提示和生成输出。

#### 核心特性

| 特性 | 详情 |
|------|------|
| **支持模态** | 文本（多语言）、图像（通过扩展） |
| **风险类别** | 13+类别（暴力、仇恨、自残、性内容、非法活动等） |
| **部署方式** | 本地部署、API服务 |
| **模型大小** | 8B参数，支持INT4量化（440MB） |
| **性能** | 违规率降低86%，TPR>99% |

#### 功能模块

- **Llama Guard 3**: 主分类器，输入/输出筛查
- **Prompt Guard**: 提示注入检测（86M参数）
- **Code Shield**: 安全代码生成

#### 优势

✅ 开源可定制  
✅ 多语言支持（13+语言）  
✅ 模块化设计  
✅ 低延迟（>30 tokens/s）  
✅ 量化支持  

#### 局限

❌ 主要支持文本  
❌ 需要GPU资源  
❌ 自定义类别需微调  

#### 适用场景

- 企业级内容审核
- 多语言应用
- 需要本地化部署的场景

---

### 2. NeMo Guardrails

**开发商**: NVIDIA

**开源协议**: Apache 2.0

**GitHub**: [NVIDIA/NeMo-Guardrails](https://github.com/NVIDIA/NeMo-Guardrails)

#### 产品定位
NVIDIA NeMo Guardrails是可编程护栏编排框架，支持对话流程控制、内容安全和工具使用安全。

#### 核心特性

| 特性 | 详情 |
|------|------|
| **支持模态** | 文本、图像（通过LLM-as-a-Judge） |
| **护栏类型** | 主题控制、PII检测、RAG grounding、越狱防护 |
| **编排能力** | 多护栏并行执行、条件路由 |
| **集成框架** | LangChain、LangGraph、LlamaIndex |
| **部署方式** | 本地、Docker、Kubernetes |

#### 功能模块

- **输入护栏**: 提示注入检测、主题控制
- **输出护栏**: 内容审核、事实核查
- **对话护栏**: 多轮对话流程控制
- **工具护栏**: 工具调用安全验证

#### 优势

✅ 强大的编排能力  
✅ 对话流程控制（Colang语言）  
✅ 多代理支持  
✅ GPU加速  
✅ 企业级支持  

#### 局限

❌ 学习曲线较陡  
❌ 复杂配置  
❌ 多模态支持有限  

#### 适用场景

- 对话式AI应用
- 多轮交互系统
- 企业级代理部署

---

### 3. Guardrails AI

**开发商**: Guardrails AI Inc.

**开源协议**: Apache 2.0

**GitHub**: [guardrails-ai/guardrails](https://github.com/guardrails-ai/guardrails)

**官网**: [guardrailsai.com](https://www.guardrailsai.com)

#### 产品定位
Guardrails AI是开源Python框架，专注于LLM输入/输出验证，提供可组合的验证器生态系统。

#### 核心特性

| 特性 | 详情 |
|------|------|
| **支持模态** | 文本、结构化数据（JSON/XML） |
| **验证器数量** | 100+社区验证器 |
| **风险覆盖** | 毒性、PII、幻觉、偏见、一致性 |
| **部署方式** | Python库、REST API、Guardrails Pro云服务 |
| **GitHub** | 6.6k stars, 561 forks |

#### 验证器生态

**输入验证器**:
- `Anonymize`: PII脱敏
- `PromptInjection`: 注入检测
- `Toxicity`: 毒性检测
- `Secrets`: 密钥检测
- `TokenLimit`: Token限制

**输出验证器**:
- `FactualConsistency`: 事实一致性
- `JSON`: JSON结构验证
- `Bias`: 偏见检测
- `MaliciousURLs`: 恶意链接
- `Relevance`: 相关性检查

#### 优势

✅ 丰富的验证器生态  
✅ 易于使用  
✅ 自动重提示  
✅ 结构化输出验证  
✅ 流式响应支持  

#### 局限

❌ 主要支持文本  
❌ 多模态支持有限  
❌ 部分高级功能需Pro  

#### 适用场景

- 结构化数据生成
- 内容审核
- 数据提取管道

---

### 4. LLM Guard

**开发商**: Protect AI

**开源协议**: MIT

**GitHub**: [protectai/llm-guard](https://github.com/protectai/llm-guard)

#### 产品定位
LLM Guard是开源安全工具包，提供15个输入扫描器和20个输出扫描器，专注于输入/输出安全扫描。

#### 核心特性

| 特性 | 详情 |
|------|------|
| **支持模态** | 文本 |
| **输入扫描器** | 15个（注入、PII、毒性、密钥等） |
| **输出扫描器** | 20个（偏见、幻觉、URL等） |
| **部署方式** | Python库、Docker API |
| **GitHub** | 2.5k stars, 342 forks |

#### 扫描器列表

**输入扫描**:
- Anonymize, BanCode, BanCompetitors, BanSubstrings
- BanTopics, Code, Gibberish, InvisibleText
- Language, PromptInjection, Regex, Secrets
- Sentiment, TokenLimit, Toxicity

**输出扫描**:
- BanCompetitors, BanSubstrings, BanTopics, Bias
- Code, Deanonymize, JSON, Language
- LanguageSame, MaliciousURLs, NoRefusal
- ReadingTime, FactualConsistency, Gibberish
- Regex, Relevance, Sensitive, Sentiment, Toxicity, URLReachability

#### 优势

✅ 完全开源免费  
✅ 自托管，数据不出境  
✅ 模块化扫描器  
✅ API服务器模式  
✅ 轻量级  

#### 局限

❌ 仅支持文本  
❌ 社区相对较小  
❌ 无对话控制能力  

#### 适用场景

- 自托管安全扫描
- 合规要求严格的场景
- 轻量级集成

---

### 5. Purple Llama

**开发商**: Meta AI

**开源协议**: Apache 2.0

**GitHub**: [facebookresearch/PurpleLlama](https://github.com/facebookresearch/PurpleLlama)

#### 产品定位
Purple Llama是Meta的综合LLM安全项目，包含评估基准和安全工具。

#### 组件清单

| 组件 | 功能 |
|------|------|
| **Llama Guard** | 输入/输出分类器 |
| **Prompt Guard** | 注入检测（86M参数） |
| **Code Shield** | 代码安全生成 |
| **CyberSec Eval** | 安全评估基准 |

#### 优势

✅ Meta官方支持  
✅ 与Llama模型深度集成  
✅ 持续更新  

#### 适用场景

- Llama模型用户
- 需要综合安全方案

---

## 商业护栏服务

### 1. Azure AI Content Safety

**开发商**: Microsoft

**服务类型**: 云服务API

**官网**: [Azure Content Safety](https://azure.microsoft.com/services/cognitive-services/content-safety/)

#### 产品定位
Azure AI Content Safety是微软的企业级内容审核服务，支持文本、图像和多模态内容分析。

#### 核心特性

| 特性 | 详情 |
|------|------|
| **支持模态** | 文本、图像、多模态 |
| **核心API** | 文本审核、图像审核、多模态API |
| **高级功能** | Prompt Shields、Groundedness检测、自定义类别 |
| **定价** | 按量付费，免费层可用 |
| **SLA** | 企业级99.9% |

#### 功能详解

**内容审核**:
- 暴力、仇恨、性内容、自残检测
- 严重度评分（Safe/Low/Medium/High）
- 自定义屏蔽列表

**Prompt Shields**:
- 直接注入检测
- 间接注入检测
- 越狱攻击防护

**Groundedness Detection**:
- 幻觉检测
- 事实一致性验证
- 自动纠正（预览）

**自定义类别**:
- 快速自定义（Rapid）
- 标准自定义（Standard）

#### 优势

✅ 企业级可靠性  
✅ 多模态原生支持  
✅ Azure生态集成  
✅ 自定义能力强  
✅ 合规认证完备  

#### 局限

❌ 云服务依赖  
❌ 成本随规模增长  
❌ 延迟受网络影响  

#### 适用场景

- 企业级应用
- Azure用户
- 多模态内容平台

---

### 2. OpenAI Moderation API

**开发商**: OpenAI

**服务类型**: 云服务API（免费）

**文档**: [OpenAI Moderation](https://platform.openai.com/docs/guides/moderation)

#### 产品定位
OpenAI Moderation API是免费的云端内容审核服务，基于GPT-4o构建。

#### 核心特性

| 特性 | 详情 |
|------|------|
| **模型** | omni-moderation-latest（基于GPT-4o） |
| **支持模态** | 文本、图像（部分类别） |
| **风险类别** | 8大类（仇恨、骚扰、自残、性、暴力、非法等） |
| **定价** | 免费 |
| **多语言** | 支持多语言，低资源语言提升70% |

#### 风险类别

| 类别 | 文本 | 图像 | 说明 |
|------|------|------|------|
| harassment | ✅ | ❌ | 骚扰内容 |
| hate | ✅ | ❌ | 仇恨言论 |
| self-harm | ✅ | ✅ | 自残内容 |
| sexual | ✅ | ✅ | 性内容 |
| violence | ✅ | ✅ | 暴力内容 |
| illicit | ✅ | ❌ | 非法行为指导 |

#### 优势

✅ 完全免费  
✅ 基于GPT-4o，准确率高  
✅ 多语言支持优秀  
✅ 易于集成  
✅ 分数校准（概率解释）  

#### 局限

❌ 图像支持类别有限  
❌ 无法自定义  
❌ 依赖OpenAI服务  
❌ 无本地部署  

#### 适用场景

- 预算有限的初创公司
- OpenAI API用户
- 快速原型开发

---

### 3. AWS Bedrock Guardrails

**开发商**: Amazon Web Services

**服务类型**: 云服务API

**官网**: [AWS Bedrock Guardrails](https://aws.amazon.com/bedrock/guardrails/)

#### 产品定位
AWS Bedrock Guardrails是Amazon的生成式AI安全服务，与Bedrock模型深度集成。

#### 核心特性

| 特性 | 详情 |
|------|------|
| **支持模态** | 文本、图像 |
| **过滤策略** | 内容过滤、PII过滤、单词过滤、主题限制 |
| **集成** | AWS Bedrock、IAM权限 |
| **定价** | 按量付费 |

#### 功能详解

**内容过滤**:
- 有害内容检测
- 可配置阈值

**PII过滤**:
- 自动PII检测
- PII脱敏/阻断

**主题限制**:
- 自定义禁止主题
- 主题描述自然语言

**单词过滤**:
- 自定义敏感词列表

#### 优势

✅ AWS生态集成  
✅ IAM权限控制  
✅ 与Bedrock无缝集成  

#### 局限

❌ 主要支持AWS生态  
❌ 自定义能力有限  
❌ 多模态支持较弱  

#### 适用场景

- AWS用户
- Bedrock模型用户
- 需要IAM集成的企业

---

### 4. Enkrypt AI Guardrails

**开发商**: Enkrypt AI

**服务类型**: 云服务API/企业部署

**官网**: [enkryptai.com](https://www.enkryptai.com)

#### 产品定位
Enkrypt AI是企业级AI安全与合规解决方案，支持隐私、安全和内容审核。

#### 核心特性

| 特性 | 详情 |
|------|------|
| **支持模态** | 文本、图像、语音 |
| **模型支持** | 700K+模型 |
| **核心功能** | PII检测、提示注入防护、偏见检测、策略违规检测 |
| **部署** | 云、本地、混合 |

#### 功能对比亮点

- **系统提示泄露检测**: 唯一支持
- **自定义策略违规**: 唯一支持
- **Token限制**: 无限制
- **延迟**: 文本0.029s（最快）

#### 优势

✅ 功能最全面  
✅ 延迟最低  
✅ 企业级部署选项  
✅ 系统提示保护  

#### 局限

❌ 商业产品，成本较高  
❌ 知名度相对较低  

#### 适用场景

- 高安全要求企业
- 金融、医疗等敏感行业
- 需要系统提示保护

---

## 多模态特定方案

### 1. SALMONN-Guard

**来源**: 清华大学

**论文**: [SACRED-Bench](https://arxiv.org/pdf/2511.10222v3)

#### 功能
首个联合检查语音、音频和文本的安全护栏模型，针对音频组合攻击。

#### 性能
- 将Gemini 2.5 Pro攻击成功率从66%降至20%

---

### 2. VERA-V

**来源**: 学术研究

**论文**: [VERA-V](https://arxiv.org/pdf/2510.17759v1)

#### 功能
变分推理框架，用于多模态越狱发现，支持文本+图像联合攻击生成。

#### 性能
- GPT-4o上ASR比最佳基线高53.75%

---

## 快速选型指南

### 按使用场景

| 场景 | 推荐产品 | 理由 |
|------|----------|------|
| 初创/MVP | OpenAI Moderation | 免费、易用 |
| 企业级应用 | Azure Content Safety | 企业级可靠性 |
| AWS生态 | Bedrock Guardrails | 原生集成 |
| 自托管需求 | LLM Guard | 开源、轻量 |
| 对话应用 | NeMo Guardrails | 对话控制 |
| 结构化输出 | Guardrails AI | JSON验证 |
| 多语言 | Llama Guard 3 | 13+语言 |
| 最高安全 | Enkrypt AI | 功能最全 |

### 按模态需求

| 需求 | 推荐产品 |
|------|----------|
| 纯文本 | Llama Guard, LLM Guard, Guardrails AI |
| 文本+图像 | Azure Content Safety, OpenAI Moderation |
| 全模态 | Enkrypt AI, SALMONN-Guard |

### 按预算

| 预算 | 推荐产品 |
|------|----------|
| 免费 | OpenAI Moderation, LLM Guard, Llama Guard |
| 中等 | Azure Content Safety, Guardrails Pro |
| 充足 | Enkrypt AI, 企业定制 |

---

## 贡献

欢迎补充新的护栏产品！请按以下格式添加：

```markdown
### 产品名称
**开发商**: 公司/组织
**开源协议**: 协议（如适用）
**官网**: 链接

#### 核心特性
| 特性 | 详情 |
|------|------|
| 支持模态 | ... |
| 核心功能 | ... |

#### 优势与局限
✅ 优势
❌ 局限

#### 适用场景
- 场景1
- 场景2
```

---

*本文档基于公开资料整理，产品信息可能随时间变化*
