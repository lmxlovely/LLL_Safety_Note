---
type: concept
aliases: [Fisher判别比, Fisher Ratio, 类间类内比]
---

# Fisher Discriminant Ratio

## 定义

衡量类间距离相对于类内方差的比率，用于评估二分类任务的可分性，源自Fisher线性判别分析（LDA）。

## 数学形式

$$
F = \frac{\|\mu_1 - \mu_0\|_2^2}{\text{mean}(\sigma_0^2) + \text{mean}(\sigma_1^2)}
$$

其中：
- $\mu_0, \mu_1$: 两类的中心点（均值向量）
- $\sigma_0^2, \sigma_1^2$: 类内方差（逐维度方差的均值）

## 核心要点

1. **物理意义**: 类中心距离越大、类内散布越小 → F越高 → 越易分类
2. **线性分类器性能**: 高F值预示线性分类器（如逻辑回归）易达高准确率
3. **RLHF退化**: 指令调优导致F从4.23降至3.12（-26%），类间距离缩小
4. **漂移敏感性**: 低F值的嵌入空间对扰动更脆弱

## 代表工作

- [[Linear Discriminant Analysis]]: Fisher判别分析原始工作
- [[Embedding Drift Safety Collapse]]: 用Fisher Ratio量化对齐对可分性的损害

## 相关概念

- [[Silhouette Score]]
- [[Class Separability]]
- [[RLHF]]
- [[Logistic Regression]]
