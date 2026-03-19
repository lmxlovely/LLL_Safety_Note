---
type: concept
aliases: [Reinforcement Learning from Human Feedback, 人类反馈强化学习]
---

# RLHF

## 定义

通过人类标注的偏好数据训练奖励模型，再用强化学习（如PPO）优化语言模型，使其输出更符合人类价值观和期望的对齐技术。

## 典型流程

1. **监督微调（SFT）**: 在高质量演示数据上微调基础模型
2. **奖励建模（RM）**: 训练奖励模型预测人类偏好 $r_\phi(x, y)$
3. **强化学习优化**: 最大化期望奖励
$$
\max_\theta \mathbb{E}_{x \sim D, y \sim \pi_\theta} [r_\phi(x, y)] - \beta \text{KL}(\pi_\theta || \pi_{\text{ref}})
$$

其中 $\beta$ 控制与参考模型的KL散度，防止过度优化。

## 核心要点

1. **对齐目标**: 改善模型行为（有用性、无害性、诚实性）
2. **意外副作用**: 降低嵌入空间的类可分性（Silhouette Score -19%，Fisher Ratio -26%）
3. **边界模糊**: 倾向用中间嵌入表示边界案例，降低安全分类器margin
4. **权衡**: 行为改进 vs 分类器鲁棒性

## 代表工作

- [[InstructGPT]]: 首次大规模应用RLHF于语言模型对齐
- [[Embedding Drift Safety Collapse]]: 发现RLHF降低下游安全分类器可分性

## 相关概念

- [[Alignment]]
- [[Instruction Tuning]]
- [[Safety Classifier]]
- [[Constitutional AI]]
