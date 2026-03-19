---
type: concept
aliases: [Harmful Representation Fidelity, 有害表示保真度]
---

# HRF (Harmful Representation Fidelity)

## 定义

基于 Fisher 判别分析的几何度量，量化 LLM 表示空间中有害意图的稳定性，表示为总表示变化中有效意图信号所占的比例。

## 数学形式

$$
\text{HRF}_t = \frac{S_t}{S_t + \lambda(B_t + V_t) + \epsilon}
$$

其中：
- $S_t$: 信号项（风格归一化的判别边界）
- $B_t$: 语义漂移项
- $V_t$: 类内离散度
- $\lambda$: 正则化系数（默认为 1）

## 核心要点

1. **有界性**: 取值范围 [0, 1)，跨模型架构可比
2. **物理意义**: 表示空间的信噪比（SNR），量化意图稳定性
3. **计算效率**: 仅需前向传播，比 ASR 快 180×
4. **预测能力**: 与 ASR 强负相关（ρ ≈ -0.90），ID 上的 HRF 可预测 OOD 攻击成功率

## 代表工作

- [[Separability Without Stability]]: 提出 HRF 指标，揭示离心漂移机制

## 相关概念

- [[Fisher Linear Discriminant Analysis]]: 理论基础
- [[Centrifugal Drift]]: HRF 量化的核心现象
- [[Signal-to-Noise Ratio]]: 物理解释
- [[Attack Success Rate]]: 传统评估指标对比
