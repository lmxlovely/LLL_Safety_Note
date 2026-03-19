---
type: concept
aliases: [最后token池化, Final Token Pooling, EOS Pooling]
---

# Last Token Pooling

## 定义

对于解码器架构（causal attention），使用序列最后一个token的隐藏状态作为整个序列的固定长度表示。

## 数学形式

给定token序列 $x = (x_1, \ldots, x_T)$，语言模型产生隐藏状态 $H = [h_1, \ldots, h_T]^\top \in \mathbb{R}^{T \times d}$：
$$
z = h_T
$$

其中 $h_T \in \mathbb{R}^d$ 是最后token的隐藏状态。

## 核心要点

1. **因果建模**: 在自回归解码器中，$h_T$ 通过注意力机制聚合了所有前文信息
2. **架构依赖**: 仅适用于解码器架构（GPT系列、LLaMA、Qwen），编码器需用其他策略
3. **vs 平均池化**: 解码器中最后token自然聚合全局，无需平均
4. **生产常用**: 简单高效，是GPT风格模型的标准嵌入提取方式

## 代表工作

- [[Embedding Drift Safety Collapse]]: 对Qwen-0.6B/4B-Instruct使用Last Token Pooling提取嵌入

## 相关概念

- [[Embedding Extraction]]
- [[Embedding]]
- [[Mean Pooling]]
- [[Causal Attention]]
