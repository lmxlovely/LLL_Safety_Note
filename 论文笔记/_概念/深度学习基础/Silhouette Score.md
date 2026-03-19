---
type: concept
aliases: [轮廓分数, Silhouette Coefficient, 轮廓系数]
---

# Silhouette Score

## 定义

衡量聚类或分类任务中样本与同类样本紧密度相对于异类样本分离度的无监督指标。

## 数学形式

对于样本 $i$：
$$
s_i = \frac{b_i - a_i}{\max(a_i, b_i)}
$$

其中：
- $a_i$: 样本 $i$ 到同类其他样本的平均距离
- $b_i$: 样本 $i$ 到最近异类样本的平均距离

整体分数：
$$
S = \frac{1}{N} \sum_{i=1}^N s_i \in [-1, 1]
$$

## 核心要点

1. **取值解释**:
   - $S \to +1$: 分离良好，样本远离异类、接近同类
   - $S \to 0$: 样本位于决策边界附近
   - $S \to -1$: 样本可能分配到错误类别
2. **类可分性**: 高Silhouette Score表明类间界限清晰
3. **RLHF退化**: 指令调优模型的Silhouette Score从0.245降至0.198（-19%）
4. **分类器脆弱性**: 低可分性导致对嵌入漂移更敏感

## 代表工作

- [[Embedding Drift Safety Collapse]]: 用Silhouette Score量化对齐对类可分性的负面影响

## 相关概念

- [[Fisher Discriminant Ratio]]
- [[Class Separability]]
- [[RLHF]]
- [[Embedding Drift]]
