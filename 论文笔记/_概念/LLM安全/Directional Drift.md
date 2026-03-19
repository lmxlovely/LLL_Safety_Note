---
type: concept
aliases: [方向漂移, Systematic Drift, 系统性漂移]
---

# Directional Drift

## 定义

沿固定方向向嵌入向量添加系统性偏移，模拟微调、领域适应等导致的一致性变化。

## 数学形式

对于基线嵌入 $z_0$，在检查点 $c$ 沿方向 $v$ 漂移：
$$
z_c = \text{Normalize}(z_0 + \sigma_c v)
$$

其中：
- $v \in \mathbb{R}^d$: 固定单位方向向量（$\|v\|_2 = 1$），采样一次后固定
- $\sigma_c$: 漂移幅度
- Normalize: 重新投影到单位球面

## 核心要点

1. **确定性**: 所有样本沿同一方向漂移，无随机性
2. **微调建模**: 对应在特定任务数据上微调导致的系统性表示偏移
3. **与高斯对比**: 高斯为各向同性随机，方向为单向确定性
4. **脆弱性一致**: 与高斯漂移产生相似的灾难性失效（ROC-AUC 46-52%）

## 代表工作

- [[Embedding Drift Safety Collapse]]: 测试三种漂移机制之一，表明失效与机制无关

## 相关概念

- [[Embedding Drift]]
- [[Gaussian Drift]]
- [[Subspace Drift]]
- [[Fine-tuning]]
