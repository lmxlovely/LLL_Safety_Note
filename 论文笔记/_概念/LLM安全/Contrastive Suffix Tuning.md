---
type: concept
aliases: [Contrastive Suffix Tuning, CST, 对比后缀调优]
---

# Contrastive Suffix Tuning (CST)

## 定义

一种轻量级防御策略，通过优化短可学习后缀（长度约 16 tokens），使用双目标对比损失明确对抗 [[Centrifugal Drift|离心漂移]]，将伪装的恶意输入"拉回"可检测安全区域。

## 数学形式

$$
\mathcal{L}_{\text{total}} = \mathcal{L}_{\text{supcon}}(h) + \lambda \mathcal{L}_{\text{bce}}(f_{\text{cls}}(h), y)
$$

其中：
- $\mathcal{L}_{\text{supcon}}$: [[Supervised Contrastive Loss|监督对比损失]]，拉近相同意图（不同风格）的表示
- $\mathcal{L}_{\text{bce}}$: 二元交叉熵，确保有害/良性线性可分
- $h$: 隐藏状态（通常在中后层，如 Layer 19）

## 核心要点

1. **数据高效**: 仅需 500 个有害种子（扩展到 ~12k 样本）即可训练
2. **OOD 泛化强**: 在 WildGuard (+31.1%) 和 XSTest (+30.0%) 上显著提升检测精度
3. **轻量级**: 仅优化后缀 + 投影器 + 分类器，LLM 主体冻结
4. **对抗漂移**: 对比损失明确将不同风格的相同意图对齐，抵消风格噪声

## 训练流程

1. 数据增强：将 500 种子应用 12 种风格变化，平衡良性/恶意
2. 每批次平衡采样（一半良性，一半恶意）
3. 联合优化后缀、投影器、分类器
4. 在选定层（如 Layer 19）提取隐藏状态

## 代表工作

- [[Separability Without Stability]]: 提出 CST 方法，验证其 OOD 有效性

## 相关概念

- [[Centrifugal Drift]]: CST 对抗的核心现象
- [[Supervised Contrastive Loss]]: 核心损失函数
- [[HRF]]: 评估 CST 效果的指标
- [[Representation Engineering]]: 更广义的表示操控框架
