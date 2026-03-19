---
type: concept
aliases: [静默失效, 隐蔽故障, Silent Error]
---

# Silent Failure

## 定义

系统在实际性能已崩溃的情况下，输出指标（如置信度、粗粒度准确率）仍显示正常，导致故障无法被标准监控检测的危险模式。

## 数学形式

高置信度错误率（静默失效率）：
$$
\text{SFR} = \frac{|C \cap E|}{|E|} \times 100
$$

其中：
- $C = \{i : \max_y p(y|z_i) \geq \tau\}$：高置信度预测集（τ=0.8）
- $E = \{i : \hat{y}_i \neq y_i\}$：错误预测集

## 核心要点

1. **置信度-准确率解耦**: 准确率崩溃至50%但平均置信度仅降14%（从0.85到0.73）
2. **高比例**: 72%的错误预测以高置信度（>0.8）发生
3. **监控失效**: 标准生产监控（平均置信度、粗粒度准确率）无法检测
4. **运营风险**: 系统看似正常运行，实际已完全失效

## 代表工作

- [[Embedding Drift Safety Collapse]]: 证明嵌入漂移下的安全分类器存在大规模静默失效

## 相关概念

- [[Miscalibration]]
- [[Confidence Miscalibration]]
- [[Expected Calibration Error]]
- [[Safety Classifier]]
- [[Embedding Drift]]
