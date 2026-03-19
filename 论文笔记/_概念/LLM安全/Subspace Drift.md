---
type: concept
aliases: [子空间漂移, Rotation Drift, 旋转漂移]
---

# Subspace Drift

## 定义

通过旋转变换对嵌入空间施加几何变换，模拟架构变更、表示空间重组等导致的结构性偏移。

## 数学形式

对于基线嵌入 $z_0$，在检查点 $c$ 应用旋转：
$$
z_c = \text{Normalize}(R_c z_0)
$$

其中旋转矩阵插值：
$$
R_c = \cos(\theta_c) I_d + \sin(\theta_c) Q
$$

- $\theta_c = \sigma_c \cdot \pi/2$: 旋转角度（最大90°）
- $Q$: 随机正交矩阵（由随机矩阵的QR分解得到）
- $I_d$: 单位矩阵

## 核心要点

1. **几何变换**: 保持向量间相对关系但改变全局坐标系
2. **架构变更**: 对应层数/宽度变化、初始化差异等结构性改动
3. **最强扰动**: 在三种机制中产生略差性能（48.9% vs 42.7% AUC降幅）
4. **正交性**: 旋转保持向量模长，仅改变方向

## 代表工作

- [[Embedding Drift Safety Collapse]]: 测试三种漂移机制之一，最接近真实架构变更

## 相关概念

- [[Embedding Drift]]
- [[Gaussian Drift]]
- [[Directional Drift]]
- [[Orthogonal Transformation]]
