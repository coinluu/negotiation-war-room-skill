# Agent Integration / Agent 集成指南

`negotiation-war-room-skill` 本质是 **Skill / Prompt / Playbook 文档库**，不依赖特定平台。只要你的 Agent 支持读取文档、粘贴系统提示词或添加自定义规则，就可以使用。

返回首页：[README.md](../README.md)

## 核心文件

- [skill.md](../skill.md)：完整 Skill 协议，适合完整集成。
- [prompts/system-prompt.md](../prompts/system-prompt.md)：适合作为系统提示词。
- [prompts/input-template.md](../prompts/input-template.md)：用户输入模板。
- [prompts/output-template.md](../prompts/output-template.md)：标准输出结构。
- [playbooks/](../playbooks/)：按场景加载的打法。
- [templates/](../templates/)：微信、邮件、电话、会议等可复制模板。

## ChatGPT

适合方式：

1. 在自定义 GPT 的 Instructions 中粘贴 `prompts/system-prompt.md`。
2. 将 `skill.md` 和相关目录作为知识文件上传。
3. 使用 `prompts/input-template.md` 作为用户输入格式。

推荐调用：

```text
请使用 negotiation-war-room-skill 的工作流。
我的谈判背景如下：
[按 input-template 填写]
```

## Claude

适合方式：

1. 在 Claude Project 中添加 `skill.md`、`prompts/`、`frameworks/`、`playbooks/`。
2. 在 Project Instructions 中粘贴 `prompts/system-prompt.md`。
3. 每次对话按场景要求 Claude 读取对应 Playbook。

推荐调用：

```text
请先读取 skill.md，再读取 playbooks/client-discount.md，帮我处理以下客户压价谈判。
```

## Cursor

适合方式：

1. 将仓库放入工作区。
2. 在 Cursor Rules 或项目说明中引用 `skill.md`。
3. 让 Cursor 根据任务读取对应文件。

推荐调用：

```text
Use negotiation-war-room-skill. Read skill.md first, then use frameworks and playbooks based on my negotiation scenario.
```

## Codex

适合方式：

1. 将仓库作为 Codex 工作区。
2. 直接要求 Codex 读取 `skill.md`。
3. 针对具体场景读取 `playbooks/`、`frameworks/` 和 `templates/`。

推荐调用：

```text
请使用本仓库的 negotiation-war-room-skill。
先读取 skill.md，然后基于我的场景读取对应 playbook，输出完整谈判策略。
```

## OpenAI Agent

适合方式：

1. 将 `prompts/system-prompt.md` 作为 system instructions。
2. 将 `skill.md`、`frameworks/`、`playbooks/`、`templates/` 放入可检索知识库或文件上下文。
3. 在工具编排中让 Agent 先做场景分流，再加载对应 Playbook。

建议流程：

```text
system: [prompts/system-prompt.md]
retrieval/context: skill.md + frameworks + playbooks + templates
user: [input-template]
assistant: [output-template]
```

## 其他支持自定义提示词的 Agent

只要支持以下任一能力即可使用：

- 可粘贴系统提示词。
- 可上传或读取 Markdown 文档。
- 可设置项目规则。
- 可检索本地文件。
- 可用 Prompt 模板驱动输出。

最低集成方式：

```text
系统提示词：复制 prompts/system-prompt.md
用户输入：复制 prompts/input-template.md 并填写
输出格式：参考 prompts/output-template.md
```

## 平台无关原则

这个项目不绑定任何模型或平台。Agent 的关键任务是：

1. 先诊断，不直接写话术。
2. 先识别信息缺口，不编造事实。
3. 先分析权力、BATNA/ZOPA 和筹码，再出方案。
4. 输出多方案和评分。
5. 做风险审查和谈后确认。
6. 遵守安全边界。
