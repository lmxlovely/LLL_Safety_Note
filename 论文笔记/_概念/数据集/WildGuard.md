---
type: concept
aliases: [WildGuard数据集, Wild安全基准]
---

# WildGuard

## 定义

一个真实世界的 OOD 安全评估基准，明确包含 **有害查询**（复杂分布下）和 **困难良性查询**（棘手但安全），用于准确测量 LLM 安全检测的精度，避免过度拒绝。

## 核心要点

1. **真实分布**: 来自野生（in-the-wild）场景，涵盖多样化的语用框架
2. **平衡性**: 包含有害和困难良性样本，测试检测器的判别能力
3. **OOD 特性**: 与合成攻击分布不同，测试泛化能力
4. **应用**: 在 [[Separability Without Stability]] 中，[[CST]] 在 WildGuard 上检测精度提升 31.1%（58.4% → 89.5%）

## 与其他基准对比

| 基准 | 类型 | 特点 |
|------|------|------|
| [[AdvBench]] | ID 种子 | 合成变体基础 |
| [[HarmBench]] | OOD 形态 | 标准化自动化攻击 |
| **WildGuard** | **OOD 语用** | **真实 + 平衡（有害+困难良性）** |
| [[XSTest]] | OOD 语用 | 另一个真实世界基准 |

## 代表工作

- [[Separability Without Stability]]: 使用 WildGuard 验证 [[CST]] 的 OOD 泛化能力

## 相关概念

- [[XSTest]]: 另一个 OOD 真实基准
- [[HarmBench]]: OOD 形态句法攻击基准
- [[Contrastive Suffix Tuning]]: 在此基准上大幅提升
