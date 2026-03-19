---
type: concept
aliases: [校准失败, 置信度失真]
---

# Miscalibration

## 定义

分类器预测置信度与实际准确率不匹配的现象，导致"不知道自己不知道"。

## 数学形式

完美校准要求：当模型以概率 $p$ 预测类别 $y$ 时，实际准确率应为 $p$。

校准失败表现为 $|\text{conf} - \text{acc}|$ 过大，通过[[Expected Calibration Error|ECE]]量化。

## 核心要点

1. **静默失效**: 高置信度但低准确率（如90%置信度只有56%准确率）
2. **漂移诱发**: 嵌入漂移破坏校准但不降低置信度幅度
3. **监控失效**: 平均置信度无法反映实际性能退化
4. **生产危害**: 基于置信度的决策（如阈值过滤）完全失效

## 代表工作

- [[Embedding Drift Safety Collapse]]: ECE从1.2%升至26.9%，置信度完全失去意义

## 相关概念

- [[Expected Calibration Error]]
- [[Silent Failure]]
- [[Model Calibration]]
