---
type: concept
aliases: [Instruction-Tuned LM, 指令微调模型, SFT Model]
---

# Instruction-Tuned Model

## 定义

在基础语言模型上通过监督微调（SFT）和/或强化学习（RLHF）训练，使其能够遵循自然语言指令、完成多样化任务的对齐模型。

## 训练流程

1. **监督微调（SFT）**: 在高质量指令-响应对上微调
$$
\min_\theta -\mathbb{E}_{(x, y) \sim D_{\text{instruct}}} [\log p_\theta(y | x)]
$$

2. **RLHF（可选）**: 用人类偏好数据进一步优化
$$
\max_\theta \mathbb{E}_{x, y} [r_\phi(x, y)] - \beta \text{KL}(\pi_\theta || \pi_{\text{ref}})
$$

## 核心要点

1. **vs 基础模型**: 基础模型仅做下一token预测，指令模型遵循用户意图
2. **对齐目标**: 有用性（helpfulness）、无害性（harmlessness）、诚实性（honesty）
3. **意外副作用**: 降低嵌入空间类可分性（Silhouette -19%，Fisher -26%）
4. **生产标准**: GPT-3.5/4、Claude、LLaMA-Chat等主流模型均为指令调优

## 代表工作

- [[InstructGPT]]: OpenAI首次大规模应用
- [[LLaMA-2-Chat]]: Meta的开源指令模型
- [[Embedding Drift Safety Collapse]]: 发现指令调优降低安全分类器鲁棒性

## 相关概念

- [[RLHF]]
- [[Instruction Tuning]]
- [[Alignment]]
- [[Safety Classifier]]
