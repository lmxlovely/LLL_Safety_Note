---
type: concept
aliases: [Civil Comments数据集, Civil Comments Corpus]
---

# Civil Comments

## 定义

包含约1.8百万条英语新闻评论的毒性检测标准数据集，每条评论由众包工作者标注毒性分数，广泛用于公平性和毒性检测研究。

## 数据来源

- **规模**: 1,800,000条评论
- **来源**: 约50个英语新闻网站的公开评论区
- **标注**: 众包标注，每条评论的毒性分数（0-1）
- **许可**: [[Creative Commons License|CC0]]（公共领域）
- **隐私**: 原始数据已去标识化

## 核心要点

1. **二值化**: 通常在阈值0.5处二值化为{安全, 有毒}
2. **平衡采样**: 研究中常构造平衡子集（如10,000条）
3. **公平性研究**: 包含人口统计标签（性别、种族），用于偏见检测
4. **标准基准**: 毒性检测/内容审核领域的事实标准

## 代表工作

- [[Embedding Drift Safety Collapse]]: 使用10k平衡子集测试安全分类器鲁棒性
- [[Jigsaw Toxic Comment Classification]]: Kaggle竞赛推广该数据集

## 相关概念

- [[Toxicity Detection]]
- [[Safety Classifier]]
- [[Civil Comments Dataset]]
