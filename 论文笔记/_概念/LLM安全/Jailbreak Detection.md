---
type: concept
aliases: [越狱检测, Adversarial Prompt Detection]
---

# Jailbreak Detection

## 定义

识别试图绕过AI安全机制、诱导模型生成有害内容的对抗性输入（jailbreak prompts）。

## 核心要点

1. **攻击类型**: 角色扮演、编码绕过、虚拟场景、语言转换
2. **检测方法**: 基于嵌入的分类器、模式匹配、意图分析
3. **与漂移关系**: 同样依赖冻结嵌入，面临相同脆弱性
4. **对抗进化**: 攻击方法持续演进，检测器需不断更新

## 代表工作

- [[Embedding Drift Safety Collapse]]: 揭示jailbreak检测器对漂移的潜在脆弱性

## 相关概念

- [[Safety Classifier]]
- [[Toxicity Detection]]
- [[Embedding Drift]]
