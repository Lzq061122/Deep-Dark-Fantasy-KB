# knowledge-capture Skill

这是一个**指令型 Skill**：没有脚本、数据库或后台服务。它规定 Agent 如何响应用户随时提出的“记一下 / 存个心得 / 存个经验”请求，并通过宿主已授权的文件或 GitHub 工具完成写入。

核心文件：[SKILL.md](SKILL.md)

## 为什么放在 `.agents/skills/`？

OpenCode、Codex 和 DeepSeek Harness 的当前文档都支持从项目级的 `.agents/skills/<name>/SKILL.md` 发现 Skill。但发现范围是**当前 Agent 正在工作的项目路径**，不是 GitHub 上所有仓库。

也就是说：**Skill 在这个知识库仓库里，只有当 Agent 工作目录在本知识库里时才自动作为项目 Skill 可见**。如果你想在 CultureLens、CombatBrain 或日常其他目录里也能随手触发，应额外把整个 `knowledge-capture` 文件夹安装进该工具支持的用户级 Skills 目录。不要误以为 GitHub 更新等于你电脑里的 Skill 已自动更新。

## Windows 全局安装（本地 Agent 执行一次）

建议让本地 Agent 在你授权后按以下原则操作：

1. 克隆或更新 `Lzq061122/Deep-Dark-Fantasy-KB` 到本机可访问目录。
2. 将 `.agents/skills/knowledge-capture/` 复制到当前 Harness 支持的**用户级** Skill 目录，确保目标目录直接包含 `SKILL.md`。
3. 重新加载 Skill 列表，并通过 `knowledge-capture` 的名称及描述核对发现结果。
4. 使用一句“记一下：这是一条测试笔记”，验证能够在授权范围内真正追加文件并返回位置；若测试笔记提交到公开仓库，要明确知道它将公开。
5. 如果使用多个 Harness，逐个确认其用户级目录及发现结果；同名 Skill 避免重复安装多个有差异的副本。

### 常见位置（需以各 Harness 的当前配置为准）

| Harness | 典型用户级路径 |
| --- | --- |
| Codex | `%USERPROFILE%\.agents\skills\knowledge-capture\SKILL.md` |
| OpenCode | `%USERPROFILE%\.agents\skills\knowledge-capture\SKILL.md`（也支持 OpenCode 专用目录） |
| DeepSeek Harness | `<agentsHome>\skills\knowledge-capture\SKILL.md` 或 `<dshHome>\skills\knowledge-capture\SKILL.md`，取决于实际配置 |

需要**文件/GitHub 写入权限**才能保存。Skill 只提供工作流程，不会自行获得授权。

## 公开与私人数据

此 GitHub 仓库是 Public。记录“随时发生”不等于“私人内容可随时公开”。如果一条心得不适宜公开，优先保存在用户指定的本地私有草稿目录；等确定可以共享，再提炼后写入公共知识区。

## 与之前长提示词的关系

[本地 Agent 指令](../../../AdenineLeo/projects/Agent-Experience-Lab/LOCAL-AGENT-TASK.md) 仍作为人类可读说明。日常实际使用优先装 Skill，然后只需说“记一下……”。

## 参考

- [OpenCode 官方 Skills 文档](https://opencode.ai/docs/skills)
- [Codex Skills 指南](https://learn.chatgpt.com/docs/build-skills)
- [DeepSeek Harness 技能系统](https://deepseekdocs.com/docs/features/skills)
