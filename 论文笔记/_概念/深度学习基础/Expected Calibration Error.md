---
type: concept
aliases: [ECE, 期望校准误差, Calibration Error]
---

# Expected Calibration Error

## 定义

衡量分类器预测置信度与实际准确率之间差异的度量，量化模型是否"知道自己不知道"。

## 数学形式

将置信度范围 [0,1] 划分为 M 个区间 $B_1, \ldots, B_M$：
$$
\text{ECE} = \sum_{m=1}^M \frac{|B_m|}{N} |\text{acc}(B_m) - \text{conf}(B_m)|
$$

其中：
$$
\text{acc}(B_m) = \frac{1}{|B_m|} \sum_{i \in B_m} \mathbb{I}[\hat{y}_i = y_i]
$$
$$
\text{conf}(B_m) = \frac{1}{|B_m|} \sum_{i \in B_m} \max_y p(y|z_i)
$$

## 核心要点

1. **完美校准**: ECE=0 意味着"90%置信度的预测实际准确率为90%"
2. **危险信号**: ECE从1.2%升至26.9%表明置信度完全失去意义
3. **静默失效关联**: 高ECE导致高置信度错误（Silent Failure）
4. **生产重要性**: 置信度阈值决策依赖良好校准

## 代表工作

- [[Embedding Drift Safety Collapse]]: 展示漂移如何破坏校准（ECE 1.2% → 26.9%）

## 相关概念

- [[Model Calibration]]
- [[Miscalibration]]
- [[Confidence Miscalibration]]
- [[Silent Failure]]
- [[ROC-AUC]]
