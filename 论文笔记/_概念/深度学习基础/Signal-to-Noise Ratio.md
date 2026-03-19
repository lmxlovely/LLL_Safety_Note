---
type: concept
aliases: [信噪比, SNR, 信号噪声比]
---

# Signal-to-Noise Ratio

## 定义

信号强度与噪声强度的比率，用于量化有用信息相对于干扰的程度，在分类器鲁棒性分析中衡量决策函数的可靠性。

## 数学形式

对于线性分类器 $f(z) = w^\top z + b$，在高斯漂移 $\epsilon \sim \mathcal{N}(0, \sigma^2 I)$ 下：
$$
f(z + \epsilon) = \underbrace{w^\top z + b}_{\text{signal}} + \underbrace{w^\top \epsilon}_{\text{noise}}
$$

噪声项方差 $\text{Var}(w^\top \epsilon) = \|w\|_2^2 \sigma^2$，因此：
$$
\text{SNR} = \frac{|f(z)|^2}{\|w\|_2^2 \sigma^2} \approx \frac{1}{d\sigma^2}
$$

其中 $d$ 为嵌入维度（假设 $\|w\|_2 \approx \sqrt{d}$）。

## 核心要点

1. **失效阈值**: SNR ≈ 3是经验可靠性阈值，低于此值分类退化至随机
2. **维度诅咒**: 高维空间（d=896）放大噪声，使小扰动（σ=0.02）即可达到失效点
3. **量化预测**: 在d=896、σ=0.02时，SNR≈2.79，恰好在崩溃边界
4. **不可避免**: 这是高维线性分类的基本几何属性，非特定算法问题

## 代表工作

- [[Embedding Drift Safety Collapse]]: 用SNR分析解释1-2%漂移导致崩溃的理论原因

## 相关概念

- [[Embedding Drift]]
- [[Gaussian Drift]]
- [[Logistic Regression]]
- [[High-Dimensional Classification]]
