# 多模态大模型安全前沿论文汇总 | Multimodal LLM Safety Papers

<p align="center">
  <a href="../../data/papers_data_zh.md">📊 论文数据列表 (中文)</a> •
  <a href="../../data/papers_data_en.md">📊 Paper Data List (English)</a>
</p>

> 最后更新：2026年4月 | Last Updated: April 2026
> 
> 本文档系统梳理多模态大模型（MLLM）安全领域的最新研究成果，涵盖攻击方法、防御机制、评估基准等方向。
> 
> This document systematically reviews the latest research in Multimodal LLM (MLLM) safety, covering attack methods, defense mechanisms, and evaluation benchmarks.

---

## 目录 | Table of Contents

- [概述](#概述)
- [攻击方法研究](#攻击方法研究)
- [防御机制研究](#防御机制研究)
- [评估基准与数据集](#评估基准与数据集)
- [综述与框架](#综述与框架)
- [引用统计](#引用统计)

---

## 概述

### 数据统计

| 类别 | 数量 | 占比 |
|------|------|------|
| 攻击方法 | 21 | 24% |
| 防御机制 | 7 | 8% |
| 评估基准 | 59 | 68% |
| **总计** | **87** | **100%** |

### 时间分布

- **2026年**：65篇（75%）
- **2025年**：22篇（25%）

### 核心会议/期刊分布

- arXiv预印本：87篇
- 主要涵盖：cs.CV, cs.CL, cs.CR, cs.LG, cs.AI

---

## 攻击方法研究

### 越狱攻击（Jailbreak Attacks）

#### 1. TreeTeaming: 视觉语言模型的自主红队测试
- **作者**: Chunxiao Li, Lijun Li, Jing Shao
- **发表时间**: 2026-03
- **论文链接**: [arXiv:2603.22882](https://arxiv.org/pdf/2603.22882v1)
- **核心贡献**: 提出层次化策略探索框架，动态构建策略树进行自动化漏洞发现
- **实验结果**: 在12个主流VLM上达到SOTA攻击成功率，GPT-4o上达87.60%
- **关键词**: 自动化红队测试、策略树、视觉语言模型

#### 2. Structured Visual Narratives Undermine Safety Alignment
- **作者**: Rui Yang Tan, Yujia Hu, Roy Ka-Wei Lee
- **发表时间**: 2026-03
- **论文链接**: [arXiv:2603.21697](https://arxiv.org/pdf/2603.21697v1)
- **核心贡献**: 发现漫画模板越狱攻击，将有害目标嵌入三格视觉叙事
- **实验结果**: 在15个SOTA MLLM上，集成成功率超过90%
- **关键词**: 视觉叙事、漫画越狱、安全对齐

#### 3. Unsafe by Reciprocity: 统一多模态模型中的生成-理解耦合
- **作者**: Kaishen Wang, Heng Huang
- **发表时间**: 2026-03
- **论文链接**: [arXiv:2603.27332](https://arxiv.org/pdf/2603.27332v1)
- **核心贡献**: 提出RICE攻击范式，利用理解与生成之间的双向交互
- **实验结果**: 在G-U和U-G两个方向均实现高攻击成功率
- **关键词**: 统一多模态模型、跨功能利用、互惠交互

#### 4. MIDAS: 多图像分散与语义重构
- **作者**: Yilian Liu, Xiaojun Jia, et al.
- **发表时间**: 2026-02
- **论文链接**: [arXiv:2603.00565](https://arxiv.org/pdf/2603.00565v1)
- **核心贡献**: 将有害语义分解为风险子单元，分散到多个视觉线索
- **实验结果**: 4个闭源MLLM上平均攻击成功率81.46%
- **代码**: [GitHub](https://github.com/Winnie-Lian/MIDAS)
- **关键词**: 多图像攻击、语义重构、跨图像推理

#### 5. JAMA: 口语模型的联合音频-文本多模态攻击
- **作者**: Aravind Krishnan, Karolina Stańczak, Dietrich Klakow
- **发表时间**: 2026-03
- **论文链接**: [arXiv:2603.19127](https://arxiv.org/pdf/2603.19127v1)
- **核心贡献**: 结合GCG文本攻击与PGD音频攻击的联合优化框架
- **实验结果**: 比单模态越狱率提升1.5-10倍
- **代码**: [GitLab](https://repos.lsv.uni-saarland.de/akrishnan/multimodal-jailbreak-slm)
- **关键词**: 口语模型、音频攻击、联合优化

#### 6. Text is All You Need for VLM Jailbreaking
- **作者**: Yihang Chen, Zhao Xu, et al.
- **发表时间**: 2026-01
- **论文链接**: [arXiv:2602.00420](https://arxiv.org/pdf/2602.00420v1)
- **核心贡献**: 利用OCR能力，通过文本图像网格绕过安全机制
- **关键词**: OCR攻击、文本图像、分散查询

#### 7. GAMBIT: 游戏化多模态越狱框架
- **作者**: Xiangdong Hu, Yangyang Jiang, et al.
- **发表时间**: 2026-01
- **论文链接**: [arXiv:2601.03416](https://arxiv.org/pdf/2601.03416v1)
- **核心贡献**: 构建游戏化场景驱动模型主动完成越狱
- **实验结果**: Gemini 2.5 Flash上92.13%，QvQ-MAX上91.20%
- **关键词**: 游戏化攻击、角色沉浸、侦探叙事

### 对抗攻击与提示注入

#### 8. AgentTypo: 自适应排版提示注入攻击
- **作者**: Yanjie Li, Yiming Cao, et al.
- **发表时间**: 2025-10
- **论文链接**: [arXiv:2510.04257](https://arxiv.org/pdf/2510.04257v1)
- **核心贡献**: 黑盒优化排版文本嵌入网页图像
- **实验结果**: GPT-4o代理成功率从0.23提升至0.45
- **关键词**: 排版攻击、提示注入、多模态代理

#### 9. EVA: 通过进化式间接提示注入红队测试GUI代理
- **作者**: Yijie Lu, Tianjie Ju, et al.
- **发表时间**: 2025-05
- **论文链接**: [arXiv:2505.14289](https://arxiv.org/pdf/2505.14289v1)
- **核心贡献**: 持续监控代理注意力分布，动态更新对抗提示
- **关键词**: GUI代理、间接提示注入、注意力监控

---

## 防御机制研究

### 输入/输出过滤

#### 1. CASA: 基于条件解码的鲁棒多模态安全
- **作者**: Anurag Kumar, Raghuveer Peri, et al.
- **发表时间**: 2026-03
- **论文链接**: [arXiv:2604.00310](https://arxiv.org/pdf/2604.00310v1)
- **核心贡献**: 利用MLLM内部表示预测安全token，无需外部分类器
- **实验结果**: 在MM-SafetyBench等基准上攻击成功率降低97%以上
- **关键词**: 条件解码、安全注意力、内部表示

#### 2. NullSteer: 基于零空间投影的越狱防御
- **作者**: Xingyu Zhu, Beier Zhu, et al.
- **发表时间**: 2026-03
- **论文链接**: [arXiv:2603.22094](https://arxiv.org/pdf/2603.22094v2)
- **核心贡献**: 在良性子空间保持零扰动，在有害方向动态诱导拒绝
- **实验结果**: MiniGPT-4上平均ASR降低超过15%
- **关键词**: 零空间投影、激活防御、安全-效用平衡

#### 3. JRS-Rem: 基于越狱相关表示移位的防御
- **作者**: Zhihua Wei, Qiang Li, et al.
- **发表时间**: 2026-03
- **论文链接**: [arXiv:2603.17372](https://arxiv.org/pdf/2603.17372v1)
- **核心贡献**: 量化图像引起的表示移位，识别越狱方向
- **关键词**: 表示移位、越狱方向、推理时防御

#### 4. EchoSafe: 推理时自反思记忆
- **作者**: Ce Zhang, Jinxi He, et al.
- **发表时间**: 2026-03
- **论文链接**: [arXiv:2603.15800](https://arxiv.org/pdf/2603.15800v1)
- **核心贡献**: 维护自反思记忆库，积累安全洞察
- **关键词**: 上下文安全、记忆库、推理时学习

### 安全对齐与训练

#### 5. SafeNeuron: 神经元级安全对齐
- **作者**: Zhaoxin Wang, Jiaming Liang, et al.
- **发表时间**: 2026-02
- **论文链接**: [arXiv:2602.12158](https://arxiv.org/pdf/2602.12158v1)
- **核心贡献**: 识别安全相关神经元，偏好优化时冻结这些神经元
- **实验结果**: 显著提升对神经元剪枝攻击的鲁棒性
- **关键词**: 神经元级对齐、安全表示、参数高效

#### 6. Safe RLHF-V: 多模态人类反馈的安全强化学习
- **作者**: Jiaming Ji, Xinyu Chen, et al.
- **发表时间**: 2025-03
- **论文链接**: [arXiv:2503.17682](https://arxiv.org/pdf/2503.17682v2)
- **核心贡献**: 首个多模态安全对齐框架，含BeaverTails-V数据集
- **实验结果**: 安全性提升34.2%，有用性提升34.3%
- **关键词**: RLHF、安全约束、多级别护栏

---

## 评估基准与数据集

### 综合评估平台

#### 1. MUSE: 多模态统一安全评估平台
- **作者**: Zhongxi Wang, Yueqian Lin, et al.
- **发表时间**: 2026-03
- **论文链接**: [arXiv:2603.02482](https://arxiv.org/pdf/2603.02482v1)
- **核心贡献**: 集成跨模态payload生成、多轮攻击算法、LLM评判
- **创新点**: 引入ITMS（轮间模态切换）测试跨模态对齐
- **实验结果**: 多轮策略可达90-100% ASR
- **关键词**: 统一评估、多轮攻击、跨模态测试

#### 2. Uni-SafeBench: 统一多模态大模型安全基准
- **作者**: Zixiang Peng, Yongxiu Xu, et al.
- **发表时间**: 2026-04
- **论文链接**: [arXiv:2604.00547](https://arxiv.org/pdf/2604.00547v1)
- **核心贡献**: 6大安全类别×7种任务类型的综合评估
- **创新点**: Uni-Judger框架解耦上下文安全与内在安全
- **发现**: 统一化过程显著降低底层LLM的内在安全性
- **关键词**: 统一模型、安全基准、上下文安全

#### 3. MMDT: 多模态基础模型可信度解码
- **作者**: Chejian Xu, Jiawei Zhang, et al.
- **发表时间**: 2025-03
- **论文链接**: [arXiv:2503.14827](https://arxiv.org/pdf/2503.14827v1)
- **核心贡献**: 首个统一平台，评估安全、幻觉、公平、隐私、对抗鲁棒性、OOD泛化
- **平台**: [mmdecodingtrust.github.io](https://mmdecodingtrust.github.io/)
- **关键词**: 综合评估、可信度、多维度

### 专项基准

#### 4. JailbreakV-28K: 视觉越狱基准
- **相关论文**: Multiple papers reference this benchmark
- **内容**: 28K多模态越狱攻击样本
- **用途**: 评估VLM对视觉攻击的鲁棒性

#### 5. MM-SafetyBench: 多模态安全基准
- **覆盖**: 多模态输入的安全评估
- **用途**: 跨模态安全对齐测试

#### 6. SACRED-Bench: 语音-音频组合攻击基准
- **作者**: Yudong Yang, Xuezhen Zhang, et al.
- **发表时间**: 2025-11
- **论文链接**: [arXiv:2511.10222](https://arxiv.org/pdf/2511.10222v3)
- **核心贡献**: 评估LLM在复杂音频攻击下的鲁棒性
- **创新点**: 语音-音频组合机制（重叠、混合、多说话人对话）
- **实验结果**: Gemini 2.5 Pro攻击成功率66%
- **代码**: [HuggingFace](https://huggingface.co/datasets/tsinghua-ee/SACRED-Bench)
- **关键词**: 音频攻击、语音组合、黑盒攻击

#### 7. Lingua-SafetyBench: 多语言VLM安全基准
- **作者**: Enyi Shi, Pengyang Shao, et al.
- **发表时间**: 2026-01
- **论文链接**: [arXiv:2601.22737](https://arxiv.org/pdf/2601.22737v1)
- **规模**: 100,440有害图像-文本对，覆盖10种语言
- **发现**: 高资源语言图像主导风险ASR更高，非高资源语言文本主导风险更严重
- **关键词**: 多语言、跨文化、资源不均衡

#### 8. FENCE: 金融多模态越狱检测数据集
- **作者**: Mirae Kim, Seonghun Jeong, Youngjun Kwak
- **发表时间**: 2026-02
- **论文链接**: [arXiv:2602.18154](https://arxiv.org/pdf/2602.18154v1)
- **特点**: 双语（韩语-英语）金融领域数据集
- **实验结果**: 基线检测器达到99%分布内准确率
- **关键词**: 金融安全、多语言、越狱检测

---

## 综述与框架

### 1. Jailbreaking LLMs & VLMs: 机制、评估与统一防御
- **作者**: Zejian Chen, Chaozhuo Li, et al.
- **发表时间**: 2026-01
- **论文链接**: [arXiv:2601.03594](https://arxiv.org/pdf/2601.03594v1)
- **核心贡献**: 三维调研框架（攻击-防御-评估），提出统一防御原则
- **覆盖**: 从纯文本到多模态的全谱分析
- **关键词**: 统一框架、防御原则、标准化评估

### 2. AI Security in the Foundation Model Era: 综合综述
- **作者**: Zhenyi Wang, Siyu Luan
- **发表时间**: 2026-03
- **论文链接**: [arXiv:2603.24857](https://arxiv.org/pdf/2603.24857v1)
- **核心贡献**: 统一闭环威胁分类法，四轴模型-数据交互
- **分类**: D→D, D→M, M→D, M→M四类威胁
- **关键词**: 基础模型、威胁分类、闭环分析

### 3. Cisco Integrated AI Security and Safety Framework
- **作者**: Amy Chang, Tiffany Saade, et al.
- **发表时间**: 2025-12
- **论文链接**: [arXiv:2512.12921](https://arxiv.org/pdf/2512.12921v1)
- **核心贡献**: 统一的生命周期感知分类法和操作框架
- **覆盖**: 多模态、代理、管道、生态系统
- **关键词**: 企业框架、生命周期、AI治理

### 4. OpenRT: 多模态LLM开源红队框架
- **作者**: Xin Wang, Yunhao Chen, et al.
- **发表时间**: 2026-01
- **论文链接**: [arXiv:2601.01592](https://arxiv.org/pdf/2601.01592v2)
- **核心贡献**: 统一模块化高吞吐量红队框架
- **集成**: 37种攻击方法，20个先进模型评估
- **发现**: 前沿模型平均ASR高达49.14%
- **关键词**: 开源框架、红队自动化、大规模评估

### 5. DeepSight: 一体化LM安全工具包
- **作者**: Bo Zhang, Jiaxuan Guo, et al.
- **发表时间**: 2026-02
- **论文链接**: [arXiv:2602.12092](https://arxiv.org/pdf/2602.12092v1)
- **核心贡献**: 评估-诊断集成范式，DeepSafe+DeepScan双工具包
- **特点**: 首个支持前沿AI风险评估的开源工具包
- **关键词**: 安全评估、诊断工具、白盒洞察

---

## 引用统计

### 高影响力论文（按主题）

| 排名 | 论文 | 主题 | 影响力指标 |
|------|------|------|------------|
| 1 | TreeTeaming | 红队测试 | GPT-4o 87.6% ASR |
| 2 | MUSE | 评估平台 | 90-100% ASR揭示 |
| 3 | CASA | 防御机制 | 97% ASR降低 |
| 4 | OpenRT | 开源框架 | 37攻击×20模型 |
| 5 | MMDT | 综合评估 | 6维度评估 |

### 研究热点关键词

```
Jailbreak (28) | Safety Alignment (24) | Multimodal (22) | Red Teaming (18)
Vision-Language (16) | Guardrails (12) | Attack (15) | Defense (11)
Evaluation (14) | Benchmark (13) | Cross-modal (9)
```

---

## 贡献指南

欢迎提交新的论文！请按以下格式添加：

```markdown
### 论文标题
- **作者**: 作者列表
- **发表时间**: YYYY-MM
- **会议/期刊**: 发表venue
- **论文链接**: [arXiv:ID](url)
- **代码**: [GitHub](url) (如有)
- **核心贡献**: 一句话概括
- **关键词**: 3-5个关键词
```

---

## 许可证

本文档遵循 [MIT License](../../LICENSE)，论文引用归原作者所有。
