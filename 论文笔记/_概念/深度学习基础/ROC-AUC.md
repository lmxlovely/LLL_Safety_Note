---
type: concept
aliases: [AUROC, Area Under ROC Curve, ROC曲线下面积]
---

# ROC-AUC

## 定义

Receiver Operating Characteristic曲线下的面积，衡量二分类器在所有可能阈值下的判别能力，独立于具体阈值选择。

## 数学形式

$$
\text{AUC} = \frac{1}{|P| \cdot |N|} \sum_{i \in P} \sum_{j \in N} \mathbb{I}[\hat{p}_i > \hat{p}_j]
$$

其中：
- $P = \{i : y_i = 1\}$: 正类样本集
- $N = \{i : y_i = 0\}$: 负类样本集
- $\hat{p}_i$: 样本i的预测概率
- $\mathbb{I}[\cdot]$: 指示函数

## 核心要点

1. **取值范围**: [0.5, 1.0]，0.5表示随机猜测，1.0表示完美分离
2. **阈值无关**: 评估所有可能阈值下的性能，避免阈值选择偏差
3. **排序质量**: 本质上衡量正类样本概率高于负类样本的比例
4. **不平衡鲁棒**: 相比准确率，对类别不平衡更鲁棒

## 代表工作

- [[Embedding Drift Safety Collapse]]: 用ROC-AUC衡量漂移下分类器崩溃（85% → 50%）

## 相关概念

- [[Expected Calibration Error]]
- [[Precision-Recall Curve]]
- [[F1 Score]]
