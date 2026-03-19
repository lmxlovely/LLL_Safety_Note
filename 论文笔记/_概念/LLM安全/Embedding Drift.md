---
type: concept
aliases: [嵌入漂移, Representation Drift, 表示漂移]
---

# Embedding Drift

## 定义

模型更新（版本升级、微调、架构变更）导致的输入文本嵌入向量在向量空间中的系统性或随机性偏移，破坏下游分类器的假设。

## 数学形式

对于模型版本 t 和 t+1，原假设：
$$
f_{\theta_t}(x) \approx f_{\theta_{t+1}}(x)
$$

实际漂移建模（加性扰动）：
$$
z_{t+1} = \text{Normalize}(z_t + \epsilon), \quad \epsilon \sim \mathcal{N}(0, \sigma^2 I)
$$

其中 $\sigma$ 为漂移幅度，归一化保持单位球面。

## 核心要点

1. **脆弱性阈值**: 仅 σ=0.02（约1°角度漂移）即可导致安全分类器从85% ROC-AUC崩溃至50%
2. **三种机制**: 高斯漂移（随机）、方向漂移（系统性）、子空间漂移（几何变换）
3. **生产场景**: 模型更新（安全改进/性能优化）常见但漂移影响被低估
4. **检测困难**: 平均置信度仅下降14%，难以通过标准监控发现

## 代表工作

- [[Embedding Drift Safety Collapse]]: 首次系统量化漂移对安全分类器的灾难性影响

## 相关概念

- [[Embedding]]
- [[Safety Classifier]]
- [[Silent Failure]]
- [[Representation Stability]]
- [[Model Calibration]]
