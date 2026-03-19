---
type: concept
aliases: [AdvBench数据集, Adversarial Bench]
---

# AdvBench

## 定义

一个广泛使用的对抗性安全基准数据集，包含多样化的有害指令（harmful instructions），用于评估 LLM 的安全对齐鲁棒性。

## 核心要点

1. **规模**: 包含数百个精心设计的有害意图种子
2. **多样性**: 覆盖多种有害类别（暴力、欺诈、隐私侵犯等）
3. **应用**: 常作为合成攻击生成的基础（如风格变化实验）
4. **ID 基准**: 在 [[Separability Without Stability]] 中，300 个 AdvBench 种子被扩展为 12 种风格变体，构成 ID 评估集

## 代表工作

- [[Separability Without Stability]]: 使用 AdvBench 构建 ID 合成变体基准

## 相关概念

- [[HarmBench]]: 另一个标准化攻击评估框架（OOD）
- [[WildGuard]]: 真实世界 OOD 基准
- [[Attack Success Rate]]: 评估指标
