---
type: concept
aliases: [逻辑回归, Logit Classifier, 对数几率回归]
---

# Logistic Regression

## 定义

线性分类器，通过Sigmoid函数将线性决策函数映射到概率，常用于二分类任务，是生产环境安全分类器的常见选择。

## 数学形式

**决策函数**:
$$
f(z) = w^\top z + b
$$

**概率预测**:
$$
p(y=1|z) = \sigma(f(z)) = \frac{1}{1 + e^{-f(z)}}
$$

**L2正则化目标**:
$$
\min_{w,b} \frac{1}{N} \sum_{i=1}^N \ell(y_i, w^\top z_i + b) + \lambda \|w\|_2^2
$$

其中 $\ell(y, s) = -y \log \sigma(s) - (1-y) \log(1-\sigma(s))$ 是二元交叉熵。

## 核心要点

1. **计算高效**: 训练/推理快速，适合生产环境实时判断
2. **可解释性**: 权重向量 $w$ 直接反映特征重要性
3. **生产偏好**: 成本约束下优于深度网络（更快、更稳定）
4. **线性局限**: 对嵌入漂移敏感，无法学习非线性鲁棒模式

## 代表工作

- [[Embedding Drift Safety Collapse]]: 使用L2正则逻辑回归（λ=1.0）测试漂移脆弱性

## 相关概念

- [[L2 Regularization]]
- [[Safety Classifier]]
- [[Signal-to-Noise Ratio]]
- [[Embedding]]
