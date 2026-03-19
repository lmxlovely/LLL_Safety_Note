---
type: concept
aliases: [Centrifugal Drift, 离心漂移]
---

# Centrifugal Drift (离心漂移)

## 定义

当恶意指令被嵌入多样化的语言外壳时，其内部表示不锚定在稳定的"恶意流形"上，而是被风格特征主导，向量被拉离安全对齐的决策边界的现象。

## 机制

由 [[Form-Intent Entanglement|形式-意图纠缠]] 引发：
1. 风格特征（如诗歌格式、角色扮演框架）主导语义编码
2. 表示向量偏离规范恶意锚点 $\mu_h^{\text{base}}$
3. 判别边界模糊，检测器失效

## 数学量化

在 [[HRF]] 框架中，漂移由 $B_t$ 量化：

$$
B_t = D_{\cos}(\mu_t, \mu_h^{\text{base}})
$$

其中 $\mu_t$ 是当前风格下的恶意质心，$\mu_h^{\text{base}}$ 是原始恶意锚点。

## 核心要点

1. **主导失效机制**: 实验显示漂移项 $B_t$ 与 ASR 的正相关最强（ρ = +0.82），是防御失效的主导因素
2. **风格敏感**: 语用框架（角色扮演）比形态句法变化（被动语态）引发更强漂移
3. **可预测性**: 简单合成变体上的漂移度可预测复杂 OOD 攻击的成功率
4. **可对抗**: [[Contrastive Suffix Tuning|CST]] 通过明确对抗漂移，将表示"拉回"安全区域

## 代表工作

- [[Separability Without Stability]]: 识别离心漂移为核心失效机制，提出 HRF 量化

## 相关概念

- [[Form-Intent Entanglement]]: 根本原因
- [[Semantic Drift]]: 更广义的术语
- [[HRF]]: 量化漂移的指标
- [[Contrastive Suffix Tuning]]: 缓解漂移的方法
