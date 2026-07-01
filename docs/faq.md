# FAQ / 常见问题

返回首页：[README.md](../README.md)

## 这个项目是软件吗？

不是传统软件包。它不需要安装依赖，也不需要运行服务。

它是一个面向 Agent 的 **Skill / Prompt / Playbook 文档库**。你可以把 `skill.md`、`prompts/system-prompt.md` 和相关 Playbook 复制到 ChatGPT、Claude、Cursor、Codex 或自建 Agent 中使用。

## 可以直接用于 ChatGPT 吗？

可以。

最简单的方式是复制 [prompts/system-prompt.md](../prompts/system-prompt.md) 到自定义 GPT 的 Instructions 中，再把 [skill.md](../skill.md) 和相关目录作为知识文件上传。

如果不使用自定义 GPT，也可以直接在对话中输入：

```text
请使用 negotiation-war-room-skill 的工作流。
我的谈判背景如下：
[粘贴背景]
```

## 能保证谈判成功吗？

不能。

谈判结果取决于事实、证据、权力结构、替代方案、对方意愿和执行条件。本项目只能帮助用户提高准备质量、减少低级错误、增加方案空间、降低沟通风险。

## 能用于法律纠纷吗？

可以用于法律纠纷前的沟通准备、事实整理、证据清单、风险提示和话术审查。

但它不能替代律师，不能给确定法律结论，也不能预测诉讼或仲裁结果。涉及合同违约、劳动仲裁、赔偿、诉讼等正式权利义务判断时，建议咨询律师。

## 能用于薪资谈判吗？

可以。

项目包含 [playbooks/salary-negotiation.md](../playbooks/salary-negotiation.md)，可用于 Offer、涨薪、奖金、职级、签字费、期权和调薪节点谈判。

它会帮助用户分析：

- 能力证明。
- 市场价值。
- 替代 Offer。
- BATNA / ZOPA。
- base、bonus、sign-on、equity、title 等可交换变量。

## 能用于家庭关系沟通吗？

可以，但不能使用商业强压话术。

家庭和亲密关系沟通应优先考虑：

- 情绪安全。
- 边界表达。
- 共识建立。
- 人身安全。
- 长期关系。

项目包含 [playbooks/relationship-communication.md](../playbooks/relationship-communication.md)，专门处理熟人合作、家庭关系和亲密关系沟通。

## 如何贡献自己的谈判案例？

欢迎贡献，但必须脱敏。

请删除：

- 姓名。
- 手机号。
- 地址。
- 公司机密。
- 合同编号。
- 未授权聊天记录。
- 任何可识别个人或组织的信息。

建议先阅读 [CONTRIBUTING.md](../CONTRIBUTING.md)，按案例结构提交：

1. 用户输入。
2. 当前局势判断。
3. 信息缺口。
4. 权力指数。
5. BATNA / ZOPA。
6. 三套方案。
7. 方案评分。
8. 话术。
9. 风险审查。
10. 谈后确认。

## 如何判断 Agent 输出是否合格？

参考 [tests/acceptance-checklist.md](../tests/acceptance-checklist.md)。

简要标准：

- 能正确判断谈判类型。
- 能识别信息缺口。
- 能分析权力指数。
- 能建立目标三层模型。
- 能分析 BATNA/ZOPA。
- 能生成多方案和评分。
- 能生成可用话术。
- 能做风险审查。
- 能生成谈后确认文本。
- 不违反安全边界。
