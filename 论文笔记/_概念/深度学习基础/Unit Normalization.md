---
type: concept
aliases: [单位归一化, L2 Normalization, 向量归一化]
---

# Unit Normalization

## 定义

将向量除以其L2范数投影到单位超球面，使所有向量长度为1，消除尺度差异。

## 数学形式

对于向量 $z \in \mathbb{R}^d$：
$$
\tilde{z} = \frac{z}{\|z\|_2}
$$

其中 $\|z\|_2 = \sqrt{\sum_{i=1}^d z_i^2}$ 是L2范数。

归一化后 $\tilde{z} \in \mathcal{S}^{d-1}$（d-1维单位球面），满足 $\|\tilde{z}\|_2 = 1$。

## 核心要点

1. **余弦相似度**: 归一化后内积等价于余弦相似度：
$$
\tilde{z}_1^\top \tilde{z}_2 = \cos(\theta)
$$
其中 $\theta$ 是两向量夹角

2. **尺度不变性**: 消除向量模长差异，聚焦方向信息
3. **漂移建模**: 漂移后重新归一化保持球面约束
4. **标准实践**: 嵌入向量几乎总是归一化后使用

## 代表工作

- [[Embedding Drift Safety Collapse]]: 漂移模拟中先扰动再归一化（angular drift）

## 相关概念

- [[Embedding]]
- [[Cosine Similarity]]
- [[Embedding Drift]]
- [[Gaussian Drift]]
