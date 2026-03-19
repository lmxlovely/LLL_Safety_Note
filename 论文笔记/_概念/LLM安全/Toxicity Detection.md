---
type: concept
aliases: [毒性检测, Harmful Content Detection, 有害内容检测]
---

# Toxicity Detection

## 定义

识别用户输入或模型生成内容中的有害信息（攻击性语言、仇恨言论、偏见、暴力威胁等）的分类任务。

## 典型方法

1. **基于嵌入的分类器**:
$$
\hat{y} = g_\phi(\text{LM}(x)), \quad \hat{y} \in \{\text{safe}, \text{toxic}\}
$$

2. **基于概率的检测**: 分析token概率分布中的异常模式

3. **多层防御**: 输入过滤 + 生成监控 + 输出分类

## 核心要点

1. **数据集**: [[Civil Comments]]（1.8M众包标注评论）、Jigsaw、Perspective API
2. **挑战**:
   - 嵌入漂移导致分类器失效
   - 对抗性输入（jailbreak）
   - 边界案例判断（讽刺、引用）
3. **生产部署**: 作为安全分类器防止有害内容输出
4. **脆弱性**: 对模型更新高度敏感（σ=0.02即崩溃）

## 代表工作

- [[Perspective API]]: Google的毒性检测API
- [[Civil Comments Dataset]]: 标准毒性检测基准
- [[Embedding Drift Safety Collapse]]: 揭示毒性检测器的漂移脆弱性

## 相关概念

- [[Safety Classifier]]
- [[Jailbreak Detection]]
- [[Civil Comments]]
- [[Embedding Drift]]
