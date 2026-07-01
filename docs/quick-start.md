# Quick Start / 快速开始

本页面向第一次使用 `negotiation-war-room-skill` 的用户。你可以在 5 分钟内完成：克隆仓库、读取核心协议、复制系统提示词、填写输入模板，并用测试 Prompt 验证 Agent 输出。

返回首页：[README.md](../README.md)

## 1. 克隆仓库

```bash
git clone https://github.com/your-name/negotiation-war-room-skill.git
cd negotiation-war-room-skill
```

如果你只是想体验，也可以直接在 GitHub 页面打开文件，无需本地安装。

## 2. 打开 `skill.md`

`skill.md` 是本项目的核心协议文件，定义了 Agent 的角色、工作流、输入输出结构、安全边界和调用建议。

```bash
cat skill.md
```

推荐先阅读：

- [skill.md](../skill.md)
- [prompts/system-prompt.md](../prompts/system-prompt.md)
- [prompts/input-template.md](../prompts/input-template.md)
- [prompts/output-template.md](../prompts/output-template.md)

## 3. 复制 system prompt

如果你的工具支持 System Prompt、Project Instructions、Rules 或自定义 Agent 指令，复制：

[prompts/system-prompt.md](../prompts/system-prompt.md)

使用方式示例：

```text
你现在使用 negotiation-war-room-skill。
请遵守以下系统提示词：
[粘贴 prompts/system-prompt.md 内容]
```

如果你的工具不支持系统提示词，也可以在对话开头粘贴：

```text
请读取并遵守 negotiation-war-room-skill 的 skill.md 工作流。
我的谈判背景如下：
[粘贴背景]
```

## 4. 填写 input template

打开 [prompts/input-template.md](../prompts/input-template.md)，按模板填写谈判背景。

最小输入示例：

```text
【谈判类型】
客户压价

【当前背景】
客户说别人报价便宜 40%，希望我降价。

【我的身份与权限】
我是乙方负责人，可以决定 10% 以内折扣。

【对方身份与权限】
对方是客户市场负责人，可能需要老板审批。

【我的目标】
维护报价，最多降 10%。

【我的底线】
低于这个折扣必须缩小服务范围。

【我的 BATNA】
把团队排期给另一个利润更高的客户。

【沟通渠道】
微信

【是否需要】
策略分析 / 三套方案 / 微信话术 / 风险审查
```

## 5. 使用 test prompts 验证

打开 [tests/test-prompts.md](../tests/test-prompts.md)，复制任意测试 Prompt 给 Agent。

建议先测试这 3 类：

```text
使用 negotiation-war-room-skill。客户说报价太高，要降 25%，否则找别人。我最多只能降 8%，但想保住合作。请输出策略、三套方案和微信回复。
```

```text
使用 negotiation-war-room-skill。客户拖欠 10 万尾款，说还没验收，但没有提出具体问题。我不想撕破脸，也不能继续免费改。请给我谈判方案和跟进消息。
```

```text
使用 negotiation-war-room-skill。我拿到 offer 但薪资低于预期，希望争取 15% 提升。请生成邮件，并审查风险。
```

## 6. 判断输出是否合格

合格输出通常包含：

- 谈判类型判断
- 信息缺口
- 权力指数
- 目标三层模型
- BATNA / ZOPA
- 筹码地图
- 三套方案
- 方案评分
- 第一轮话术
- 对方可能反应与应对
- 发送前风险审查
- 谈后确认文本
- 下一轮行动

完整验收标准见 [tests/acceptance-checklist.md](../tests/acceptance-checklist.md)。
