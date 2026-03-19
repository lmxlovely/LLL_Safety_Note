---
type: concept
aliases: [对齐, AI Alignment, 价值对齐]
---

# Alignment

## 定义

使AI系统的行为符合人类价值观、意图和期望的过程，包括提升有用性、减少有害输出、提高事实准确性。

## 主要技术

1. **RLHF**: 人类反馈强化学习
2. **Constitutional AI**: 基于规则的自我批评与修正
3. **Red Teaming**: 对抗性测试发现漏洞
4. **Prompt Engineering**: 引导模型安全生成

## 核心要点

1. **三H原则**: Helpful（有用）、Harmless（无害）、Honest（诚实）
2. **意外权衡**: 改善行为的同时可能损害嵌入可分性、降低下游分类器鲁棒性
3. **多维目标**: 需平衡能力、安全性、可用性
4. **持续挑战**: 对齐税（capability tax）、jailbreak攻击、分布外泛化

## 代表工作

- [[InstructGPT]]: OpenAI的RLHF对齐实践
- [[Constitutional AI]]: Anthropic的规则驱动对齐
- [[Embedding Drift Safety Collapse]]: 揭示对齐对分类器的负面影响

## 相关概念

- [[RLHF]]
- [[Instruction Tuning]]
- [[Constitutional AI]]
- [[Safety Classifier]]
- [[Jailbreak Detection]]
