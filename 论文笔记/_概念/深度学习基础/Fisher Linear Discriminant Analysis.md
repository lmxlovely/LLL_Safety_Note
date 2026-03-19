---
type: concept
aliases: [Fisher LDA, Fisher判别分析, 费舍判别]
---

# Fisher Linear Discriminant Analysis (Fisher 线性判别分析)

## 定义

一种经典的降维和分类方法，通过最大化类间散度与类内散度的比率（Fisher Ratio），找到最优投影方向以实现类别可分。

## 数学形式

Fisher Score (判别质量):

$$
J = \frac{\text{Signal}}{\text{Noise}} = \frac{\text{Inter-class Scatter}}{\text{Intra-class Scatter}}
$$

有界形式（用于 [[HRF]]）:

$$
\phi(J) = \frac{J}{1 + J} = \frac{\text{Signal}}{\text{Signal} + \text{Noise}}
$$

## 核心要点

1. **目标**: 最大化类间距离，最小化类内距离
2. **判别能力**: Fisher Ratio 越高，类别越可分
3. **有界化**: 原始 Fisher Ratio 无界，归一化后可跨架构比较
4. **几何解释**: 在最优方向上投影后，类别分布最分离

## 应用场景

- LLM 安全：[[HRF]] 使用 Fisher 框架量化意图稳定性
- 层选择：[[Fisher Discriminant Value|FDV]] 选择最具判别性的隐藏层
- 人脸识别：Fisherface 方法
- 降维：与 PCA 互补（PCA 最大化总方差，LDA 最大化判别性）

## 代表工作

- [[Separability Without Stability]]: 基于 Fisher 框架设计 HRF 指标

## 相关概念

- [[HRF]]: 基于 Fisher 的安全评估指标
- [[Fisher Discriminant Value]]: FDV 层选择标准
- [[Signal-to-Noise Ratio]]: 本质上是 SNR 的具体化
- [[PCA]]: 互补的降维方法
