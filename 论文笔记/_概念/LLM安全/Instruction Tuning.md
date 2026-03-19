---
type: concept
aliases: [指令调优, SFT, Supervised Fine-Tuning]
---

# Instruction Tuning

## 定义

在多样化指令-响应对数据集上监督微调语言模型，使其能够理解并执行自然语言指令。

## 数学形式

$$
\min_\theta -\mathbb{E}_{(x, y) \sim D_{\text{instruct}}} [\log p_\theta(y | x)]
$$

其中 $x$ 为指令，$y$ 为期望响应。

## 核心要点

1. **数据构造**: 多样化任务（QA、摘要、推理、创作等）
2. **vs RLHF**: SFT仅用监督学习，RLHF进一步用人类偏好优化
3. **副作用**: 扩展表示空间以编码任务多样性，稀释特定特征（如毒性）
4. **标准流程**: 几乎所有生产LLM的必经步骤

## 代表工作

- [[FLAN]]: Google的指令调优基准
- [[Embedding Drift Safety Collapse]]: 发现指令调优降低类可分性

## 相关概念

- [[Instruction-Tuned Model]]
- [[RLHF]]
- [[Alignment]]
