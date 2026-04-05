# Contributing to Multimodal LLM Safety Guardrails

首先，感谢您考虑为本项目做出贡献！正是像您这样的贡献者让这个项目变得更好。

## 如何贡献

### 报告问题

如果您发现内容错误、链接失效或信息过时，请通过以下方式报告：

1. **GitHub Issues**: 提交Issue描述问题
2. **Pull Request**: 直接提交修复

### 添加新论文

要将新的研究论文添加到资料库，请确保包含以下信息：

```markdown
### 论文标题
- **作者**: 作者列表
- **会议/期刊**: 发表 venue
- **年份**: 发表年份
- **链接**: [arXiv/Paper](url)
- **代码**: [GitHub](url) (如有)
- **核心贡献**: 一句话概括主要贡献
- **关键词**: 3-5个关键词
- **摘要**: 简要摘要
```

### 更新产品信息

更新护栏产品信息时，请确保：

1. 信息来自官方文档或可靠来源
2. 包含数据更新时间
3. 提供参考链接

### 提交对比数据

添加新的对比维度或更新现有数据时：

1. 说明数据来源（官方基准/论文实验/自测）
2. 保持格式与其他条目一致
3. 更新相关可视化图表

## 内容标准

### 信息来源优先级

1. **高优先级**: 官方文档、顶会论文（NeurIPS/ICML/ICLR/CVPR/ACL等）
2. **中优先级**: arXiv预印本、技术博客、官方发布
3. **低优先级**: 第三方评测、社区反馈

### 时效性要求

- 论文：优先2023-2025年
- 产品信息：优先6个月内更新
- 趋势分析：基于近2年数据

### 格式规范

- 使用中英文双语（关键术语）
- 引用格式统一
- 表格使用Markdown格式
- 链接确保可访问

## Pull Request 流程

1. Fork 本仓库
2. 创建您的特性分支 (`git checkout -b feature/AmazingFeature`)
3. 提交您的更改 (`git commit -m 'Add some AmazingFeature'`)
4. 推送到分支 (`git push origin feature/AmazingFeature`)
5. 打开一个 Pull Request

### PR 检查清单

- [ ] 内容准确且有来源
- [ ] 格式符合规范
- [ ] 链接已验证
- [ ] 无拼写错误
- [ ] 更新了相关目录（如有）

## 开发环境

如需本地预览文档：

```bash
# 安装 mkdocs
pip install mkdocs-material

# 本地预览
mkdocs serve
```

## 社区

- 讨论区: [GitHub Discussions](../../discussions)
- 即时交流: [Discord](https://discord.gg/multimodal-safety) (即将开通)

## 许可证

通过提交贡献，您同意您的贡献将在 MIT 许可证下发布。

---

再次感谢您的贡献！
