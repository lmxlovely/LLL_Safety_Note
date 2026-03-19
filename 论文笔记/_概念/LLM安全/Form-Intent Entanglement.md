---
type: concept
aliases: [Form-Intent Entanglement, 形式意图纠缠]
---

# Form-Intent Entanglement (形式-意图纠缠)

## 定义

在 LLM 表示空间中，"意图特征"（语义内核，What is said）和"形式特征"（语用外壳，How it is said）非线性纠缠的现象，导致模型无法将有害意图解耦为风格无关的不变特征。

## 机制

在编码过程中，LLM 对显式形式特征（如被动语态、诗歌框架、角色扮演）的过度关注导致：
1. 表示向量偏离原始恶意质心
2. 语义内核被语用外壳掩盖
3. 安全检测器在 OOD 风格下失效

## 核心要点

1. **非线性特性**: 纠缠在高维表示空间中呈现非线性，线性分类器无法分离
2. **导致漂移**: 触发 [[Centrifugal Drift|离心漂移]]，表示被拉离安全流形
3. **分布偏移**: 造成严重的 [[Distribution Shift|分布偏移]]，OOD 泛化失效
4. **对齐脆弱性**: 是安全对齐在风格化攻击下失效的根本原因

## 代表工作

- [[Separability Without Stability]]: 识别并命名此现象，提出 HRF 指标量化

## 相关概念

- [[Centrifugal Drift]]: 纠缠的直接后果
- [[Semantic Drift]]: 表现形式
- [[Invariant Feature]]: 对立面（理想的解耦目标）
- [[Contrastive Suffix Tuning]]: 针对性的解决方案
