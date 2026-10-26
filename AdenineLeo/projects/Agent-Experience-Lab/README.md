# Agent Experience Lab｜让 Agent 的实践经验进入共享空间

> 维护：AdenineLeo（Ade）  
> 状态：首批五条经验已归入 [Shared 通用经验库](../../../Shared/experiences/README.md)。

## 项目最初的目的

我在项目开发和不同 Agent / Harness 的使用中，积累了提交记录、验收证据、失败案例和设计判断。它们如果只保留在本地 Agent 的上下文或私人项目里，很难和朋友交流、也很难在其他任务中复用。

因此，**Agent Experience Lab 是经验提炼工作流，而不是另一座独立的最终知识库**。它的产出应该汇入我们共同维护的 [Deep-Dark-Fantasy-KB / Shared / experiences](../../../Shared/experiences/README.md)。

这里收的是*结论与方法*，不是漂亮的长篇文章：有代表性、具有可复用价值、能追溯到真实来源，就值得保存。无需要求初学者立刻看懂或做完练习。

## 工作路径

```text
Ade / Ethan 的项目、Coding Agent 的实际工作成果
    ↓
在明确授权范围内提取真实经验
    ↓
评价代表性、可复用性、证据和适用边界
    ↓
查重或增补同类条目
    ↓
剔除不适合提交到公开仓库的私人内容
    ↓
Shared/experiences/（最终共享位置）
```

- **个人项目经历与过程**：分别留在 `AdenineLeo/`、`Ethan/`。
- **普遍适用的经验结论**：整理到 `Shared/experiences/`。
- **私有来源与审查材料**：若有需要，只作暂存和证据留底；它不是独立的长期知识库。
- **PAIPOS Lite**：负责改善 Agent 自己的工作方式、维护工作规则和偏好。经验提炼可以借鉴它，但不会自动修改它的 Core、候选或 Skills。

## 一条经验应包含什么？

1. 一句话**结论**与触发条件；
2. 问题背后的**机制和可操作方法**；
3. 一个真实的**代表案例**；
4. 证据位置，以及“来源记录 / 核对过 / 已独立复现 / 待核实”的状态；
5. **边界、反例和不能滥用的情况**。

没有规定条目字数或固定数量；已有类似规律时优先补充新例子，而不是重复生成新文件。尚未全部验证但有可靠来源的条目也可以保留待核实状态。

## V0 进展

2026-10-26，Agent 首先从 CultureLens 的工程资料中提取了五条经验候选。为核对来源和敏感信息，曾建立一个私有 GitHub 审查包。现在已依据可公开核查的 CultureLens 证据，把五条精简经验归入 Shared：

- [E-01 验收结论与范围](../../../Shared/experiences/E-01-verification-scope.md)
- [E-02 不可信模型输出](../../../Shared/experiences/E-02-untrusted-model-output.md)
- [E-03 空值与用户意图](../../../Shared/experiences/E-03-empty-is-intent.md)
- [E-04 最终字节的校验和](../../../Shared/experiences/E-04-hash-final-bytes.md)
- [E-05 操作和生效状态](../../../Shared/experiences/E-05-observe-effective-state.md)

这并不是本地 Agent 自动持续监测功能已经完成。当前已经有**真实经验条目、共同入口以及可交给本地 Agent 的工作指令**；持续自动化仍需单独实现和验证。

## 平时随时怎么记？

**直接说“记一下：……”即可**，不要求任务已经结束，也不需要指定某个工作区或提供证据。个人心得默认放入 `AdenineLeo/notes/YYYY-MM.md`；明确要求通用经验时，放入 `Shared/experiences/`，并在必要时对已有条目补充内容。

只有你提出“帮我从这个项目里提取经验”时，Agent 才需要进入项目扫描、证据核查和批量提炼流程。两种模式的完整指令见 [随时保存与经验提炼委托](LOCAL-AGENT-TASK.md)。

**注意**：共同仓库当前是 Public。“分享给 Ethan”实际也会让互联网用户可见。私人细节和无法确认公开权限的证据不要推送；可共享的通用结论与公开来源链接可以进入 Shared。

[通用经验索引](../../../Shared/experiences/README.md) · [Ade 的项目索引](../README.md)
