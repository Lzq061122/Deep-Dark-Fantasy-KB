# Shared · 通用经验库

这里收录 Ade、Ethan 和本地 Agent 从真实实践中提炼出的**有代表性、可跨项目复用的经验**。

不要求写成文章，不限定技术深度、受众基础或阅读时长。一个条目只要能够告诉下次遇到类似问题的人“应该怎么判断、怎么做、边界在哪里”，就有积累价值。

## 经验索引

| ID | 经验 | 领域 | 来源 |
| --- | --- | --- | --- |
| [E-01](E-01-verification-scope.md) | 验收结论必须明确适用范围 | 工程验收 / Agent 交接 | Ade · CultureLens |
| [E-02](E-02-untrusted-model-output.md) | 把模型输出视为不可信的外部输入 | LLM / 数据一致性 | Ade · CultureLens |
| [E-03](E-03-empty-is-intent.md) | 空值不一定代表用户没有处理过 | AI 编辑器 / 状态机 | Ade · CultureLens |
| [E-04](E-04-hash-final-bytes.md) | 校验文件哈希必须对应最终字节 | 文件处理 / 测试 | Ade · CultureLens |
| [E-05](E-05-observe-effective-state.md) | 动作成功不等于目标状态真正生效 | Agent / 配置 / 部署 | Ade · CultureLens |

首批五条（2026-10-26）依据 CultureLens **已公开**的工程文档和代码整理；不是独立重新执行全部测试。每条记录自己的证据状态。

## 随时保存，不等任务结束

有值得复用的判断时，可以直接告诉 Agent“存个经验：……”。它只需核对是否已有类似条目、保留适用边界、确认内容适合进入当前 Public 仓库，然后补充或新增；不需要专门启动一次项目审查。随手的个人想法先放在 [Ade 的笔记区](../../AdenineLeo/notes/README.md)，不必强行提炼成通用原则。

推荐安装 [knowledge-capture Skill](../../.agents/skills/knowledge-capture/SKILL.md)，然后直接说“记一下……”或“存个经验……”。不支持 Skill 的 Agent 可以使用 [长提示词兼容版](../../AdenineLeo/projects/Agent-Experience-Lab/LOCAL-AGENT-TASK.md)。

## 今后怎么增补？

```text
本地 Agent 在用户授权的项目中发现经验
    ↓
判断可复用性、代表性与证据
    ↓
查找本目录是否有同类条目
    ↓
新增，或给已有条目补充案例 / 反例
    ↓
完成必要的隐私与授权检查
    ↓
直接存入 Shared/experiences/
```

**不需要先写教程、撰写长篇复盘、凑够固定数量，也不必把“初学者能否立刻学会”当作收录门槛。**

一条经验通常包含：结论、触发条件、机制和做法、代表案例、证据状态、边界及反例。不能独立验证的部分保留“来源记录 / 待核实”，不得编造测试结果。

## 这里是公开仓库的一部分

虽然目的是两个人共享经验，而不是对外写文章，**本 GitHub 仓库当前是 Public，任何人都能看到已提交内容**。

- 不复制私人 Agent 会话、私人记忆、密钥、账号、内部服务地址、未获授权的材料。
- 对来自私有来源且无法安全公开的细节，应只保存经过处理的通用结论；必要时把证据保留在私有审查材料里。
- 本地 Agent 只有在得到明确的目标仓库写入授权后才可推送；安全边界不清楚时留在本地等待处理。
- 来源是一个可核对的工程例子时，可以链接相应公开提交，不必复制原始文档全文。

## 放在这里还是个人空间？

- **Shared/experiences/**：可复用的通用判断、方法和反例。
- **AdenineLeo/** 或 **Ethan/**：个人项目故事、日常日志、主观使用心得。

两者可以交叉引用，不需要同一份经验写两篇。

[返回 Shared 首页](../README.md) · [Ade 的 Agent 经验提炼项目](../../AdenineLeo/projects/Agent-Experience-Lab/README.md)
