---
type: concept
aliases: [高斯漂移, Isotropic Drift, 各向同性漂移]
---

# Gaussian Drift

## 定义

向嵌入向量添加各向同性高斯噪声，模拟训练随机性、量化误差等导致的随机扰动。

## 数学形式

对于基线嵌入 $z_0$，在检查点 $c$ 添加噪声：
$$
z_c = \text{Normalize}(z_0 + \epsilon_c), \quad \epsilon_c \sim \mathcal{N}(0, \sigma_c^2 I_d)
$$

其中：
- $\sigma_c$: 漂移幅度（如0.02）
- $I_d$: d维单位矩阵
- Normalize: 重新投影到单位球面

## 核心要点

1. **各向同性**: 每个维度独立同分布，无偏向性
2. **噪声放大**: 在d=896维，权重向量内积 $w^\top \epsilon$ 的方差为 $\|w\|_2^2 \sigma^2 \approx d\sigma^2$
3. **SNR退化**: 小σ在高维空间产生大噪声，SNR ≈ 1/(dσ²)
4. **真实场景**: 对应优化随机性、量化误差、数值精度损失

## 代表工作

- [[Embedding Drift Safety Collapse]]: 测试三种漂移机制之一，σ=0.02导致崩溃

## 相关概念

- [[Embedding Drift]]
- [[Directional Drift]]
- [[Subspace Drift]]
- [[Signal-to-Noise Ratio]]
