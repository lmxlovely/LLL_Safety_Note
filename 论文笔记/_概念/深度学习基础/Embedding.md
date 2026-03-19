---
type: concept
aliases: [嵌入, 向量表示, Vector Representation]
---

# Embedding

## 定义

将离散的输入（文本、图像、节点）映射到连续的稠密向量空间的表示，捕获语义或结构信息。

## 数学形式

对于输入 $x$，嵌入函数 $f_\theta: \mathcal{X} \to \mathbb{R}^d$ 产生：
$$
z = f_\theta(x) \in \mathbb{R}^d
$$

常见提取方式：
- **最后token池化**: $z = h_T$（解码器）
- **平均池化**: $z = \frac{1}{T} \sum_{t=1}^T h_t$（编码器）
- **[CLS] token**: $z = h_{\text{[CLS]}}$（BERT风格）

## 核心要点

1. **单位归一化**: 归一化到单位球面 $\tilde{z} = z/\|z\|_2$ 使余弦相似度等价于内积
2. **语义捕获**: 语义相近的输入在嵌入空间中距离接近
3. **下游任务**: 冻结嵌入用于分类、检索、聚类
4. **稳定性假设**: 生产系统假设模型更新不改变嵌入分布（实际上脆弱）

## 代表工作

- [[Word2Vec]]: 经典词嵌入
- [[Sentence-BERT]]: 句子级嵌入
- [[Embedding Drift Safety Collapse]]: 揭示嵌入在模型更新下的不稳定性

## 相关概念

- [[Embedding Drift]]
- [[Last Token Pooling]]
- [[Unit Normalization]]
- [[Representation Stability]]
