# E-05｜动作执行成功不代表目标状态真正生效

**领域**：Agent / Harness / 配置加载 / 工作流部署  
**来源项目**：CultureLens · Ade  
**核查状态**：部分公开代码与历史审查文档已核对；未独立启动 Harness 或真实平台。

## 可复用结论

“写入成功”“点击保存”“返回 HTTP 200”等回执，只能说明**某一层**完成了动作；消费者是否真正加载规则、读取配置、采用版本和接受业务数据，必须在目标状态所在的一层独立确认。

## 触发场景

- Agent Skill 文件已存在但模型没有使用。
- `.env` 文件已经配置，但实际进程仍使用 Mock 或默认值。
- 工作流草稿保存成功，但线上仍运行旧版本。
- 上游服务表示成功，但下游业务验证失败。

## 操作原则

- 对每个配置或发布动作定义消费者侧的可观察信号。
- Skill 优先检查实际 Harness 的发现和加载记录，不能只凭文件路径或模型答对一个问题断言加载成功。
- 服务配置应检查运行中的诊断状态，避免输出机密信息。
- 平台发布应检查正式生效版本，再从正式入口执行最小调用。
- 业务成功还需检查数据解析、校验、必要的落库和回读。

## 代表案例

CultureLens 的审查记录中，Dify Skill 曾放在当前 Harness 默认未扫描的目录；项目根的 `.env` 也曾没有被启动入口实际读取，导致服务仍以 Mock 运行。后续修改了 Skill 位置与配置加载路径，并留下范围受限的验收记录。

## 边界

不同 Harness 的默认扫描目录可能不同；此条不意味着所有工具都采用 `.dsh/skills`。允许显式降级为 Mock 的程序可以这样做，但应如实显示真实运行模式。历史 Skill 会话加载与内部平台发布步骤**未在本次独立复核**。

## 证据

- [集成审查中 R4 与 Skill 发现](https://github.com/Lzq061122/CultureLens/blob/c7e0804b84a7b6045d6a4d2e38be75f65149f891/docs/CODEX_INTEGRATION_REVIEW.md)
- [配置加载代码](https://github.com/Lzq061122/CultureLens/blob/c7e0804b84a7b6045d6a4d2e38be75f65149f891/backend/app.py)
- [当前 Skill 入口](https://github.com/Lzq061122/CultureLens/blob/c7e0804b84a7b6045d6a4d2e38be75f65149f891/.dsh/skills/dify-operator/SKILL.md)
- [协作与发布约定](https://github.com/Lzq061122/CultureLens/blob/c7e0804b84a7b6045d6a4d2e38be75f65149f891/docs/TEAM_AND_COORDINATION.md)

**证据等级**：公开代码与文档已核；实际 Harness 加载、平台发布没有独立重跑。
