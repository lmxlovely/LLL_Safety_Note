---
type: concept
aliases: [安全分类器, Content Moderation Classifier, 内容审核分类器]
---

# Safety Classifier

## 定义

在生产环境中部署于语言模型下游，基于冻结嵌入判断生成内容是否有害（毒性、偏见、暴力等）的监督学习分类器。

## 典型架构

$$
\hat{y} = g_\phi(f_\theta(x))
$$

其中：
- $f_\theta(x)$: 冻结的语言模型嵌入提取器
- $g_\phi(\cdot)$: 可训练的分类器（常用逻辑回归、浅层MLP）
- $\hat{y} \in \{0, 1\}$: 安全/有害预测

## 核心要点

1. **冻结嵌入假设**: 隐式假设模型更新不改变嵌入空间分布
2. **计算约束**: 生产环境偏好简单分类器（逻辑回归），而非深度网络
3. **脆弱性**: 对嵌入漂移极度敏感，σ=0.02即可导致崩溃
4. **静默失效**: 校准失败时置信度不反映实际性能

## 代表工作

- [[Constitutional Classifiers++]]: SOTA安全分类器（Anthropic/OpenAI）
- [[Embedding Drift Safety Collapse]]: 系统揭示安全分类器的漂移脆弱性

## 相关概念

- [[Toxicity Detection]]
- [[Embedding]]
- [[Embedding Drift]]
- [[Silent Failure]]
- [[Jailbreak Detection]]
