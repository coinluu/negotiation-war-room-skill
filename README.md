# negotiation-war-room-skill

中文名：**动态谈判作战参谋 Skill**

## 一句话介绍

一个面向 ChatGPT、Claude、Cursor、Codex 等 Agent 的中文谈判决策 Skill，帮助用户把复杂谈判背景转化为结构化策略、可选方案、沟通话术、风险审查和复盘动作。

## 项目定位

`negotiation-war-room-skill` 不是普通话术库。

它是一个**动态谈判决策系统**：先判断谈判类型和信息缺口，再评估双方权力结构、BATNA / ZOPA、筹码地图和风险边界，最后生成多套方案、评分、话术、谈后确认和下一轮复盘建议。

项目目标不是承诺“保证谈判成功”，而是帮助用户提高谈判准备质量，增加达成更优且可执行协议的概率。

## 核心卖点

- **场景识别**：判断是客户压价、尾款结算、薪资谈判、合同协商、熟人合作还是家庭沟通。
- **权力指数评分**：从替代方案、时间压力、信息优势、资源控制、证据强度和关系依赖评估双方筹码。
- **BATNA / ZOPA 分析**：明确谈不成怎么办，以及可能成交区间在哪里。
- **筹码地图**：不只看价格，还分析时间、范围、付款、风险、资源、关系、信息和选择权。
- **让步交换规则**：避免免费让步，每次让步都换回确定条件。
- **MESO 多方案生成**：生成 2-3 套用户都能接受、对方偏好不同的方案。
- **方案评分**：按利益最大化、成交概率、风险可控、关系保留、执行清晰度评分。
- **话术生成**：输出适合微信、电话、面谈、邮件、会议的自然话术。
- **模拟演练**：让 Agent 扮演对方，帮助用户预演反应。
- **风险审查**：发送前检查底线暴露、情绪化、法律风险、无条件让步和留痕问题。
- **谈后确认**：生成可复制的会议纪要、微信确认、邮件确认文本。
- **复盘优化**：根据对方新反馈更新策略，而不是一轮话术用到底。

## 适用场景

| 场景 | 典型问题 |
|---|---|
| 商业合作 | 合作模式、交付边界、付款节点、资源互换 |
| 客户压价 | 客户嫌贵、竞品更便宜、续约要求降价 |
| 尾款结算 | 已交付但对方拖款、不验收、想取消后续服务 |
| 薪资谈判 | Offer 低于预期、涨薪、奖金、职级、调薪节点 |
| 合同协商 | 付款、验收、违约、责任上限、交付范围 |
| 采购销售 | 单价、账期、起订量、质量、供货稳定性 |
| 合伙人谈判 | 股权、分工、投入、决策权、退出机制 |
| 纠纷协商 | 退款、赔偿、责任、投诉、和解 |
| 熟人合作 | 朋友项目、亲戚借钱、免费帮忙、面子压力 |
| 家庭沟通 | 经济边界、家庭分工、亲密关系冲突 |

## 不适用场景

本项目不用于，也不支持生成以下内容：

- 威胁恐吓
- 敲诈勒索
- 伪造证据
- 恶意操控
- 违法施压
- 冒充律师
- 冒充监管机构、HR、客户、供应商或其他第三方
- 泄露隐私、羞辱、报复或骚扰
- 承诺“保证成功”“一定追回”“一定胜诉”

涉及合同、劳动仲裁、诉讼、赔偿、家庭财产或人身安全风险时，本 Skill 只提供沟通策略、证据整理和风险提示，不替代律师或其他专业人士。

## 快速开始

你可以把本仓库作为 Agent 的谈判 Skill 使用。

最简单的方式：

```text
请使用 negotiation-war-room-skill。
先读取 skill.md，再根据我的谈判场景按需读取 frameworks、playbooks、templates。

我的谈判背景是：
[粘贴你的背景]

请输出：局势判断、信息缺口、权力指数、BATNA/ZOPA、三套方案、方案评分、第一轮话术、风险审查和谈后确认文本。
```

如果你的工具支持系统提示词，可以复制：

- [skill.md](skill.md)：完整 Skill 核心协议
- [prompts/system-prompt.md](prompts/system-prompt.md)：适合放入 Agent 的系统提示词

适用工具包括但不限于：ChatGPT、Claude、Cursor、Codex、OpenAI Agent、自建 Agent 工作流。

## 使用方式

### 方式一：直接复制 `skill.md` 给 Agent

适合完整调用 Skill。

```text
请读取以下 Skill 协议，并按其中工作流执行：
[复制 skill.md 内容]

我的谈判背景是：
[粘贴背景]
```

### 方式二：复制 `prompts/system-prompt.md` 作为系统提示词

适合你在自定义 GPT、Claude Project、Cursor Rules、Agent System Prompt 中长期使用。

```text
系统提示词：
[复制 prompts/system-prompt.md 内容]

用户输入：
[按 input-template.md 填写谈判背景]
```

### 方式三：根据 `playbooks/` 选择具体场景模板

适合只处理某一类谈判。

示例：

- 客户压价：读取 [playbooks/client-discount.md](playbooks/client-discount.md)
- 尾款结算：读取 [playbooks/business-payment.md](playbooks/business-payment.md)
- 薪资谈判：读取 [playbooks/salary-negotiation.md](playbooks/salary-negotiation.md)
- 合同协商：读取 [playbooks/contract-negotiation.md](playbooks/contract-negotiation.md)
- 家庭沟通：读取 [playbooks/relationship-communication.md](playbooks/relationship-communication.md)

## 标准输入模板

建议用户按以下格式描述谈判情况：

```text
【谈判类型】
商业合作 / 客户压价 / 尾款结算 / 薪资 / 合同 / 采购销售 / 合伙 / 纠纷 / 熟人合作 / 家庭关系 / 其他

【当前背景】
发生了什么？目前谈到哪一步？

【我的身份与权限】
我是决策人、执行人、乙方、甲方、员工、候选人、合伙人，还是其他角色？

【对方身份与权限】
对方是谁？是否有最终决策权？

【我的目标】
最想达成什么结果？

【我的底线】
最低能接受什么？

【我的 BATNA】
如果这次谈不成，我还有什么替代方案？

【对方可能诉求】
对方可能最在意什么？

【我的筹码】
我有什么价值、证据、资源、替代方案、时间优势？

【我的弱点】
我最担心什么？哪里比较被动？

【已有证据】
聊天记录、合同、付款记录、交付成果、会议纪要等。

【沟通渠道】
微信 / 电话 / 面谈 / 邮件 / 会议 / 其他

【希望风格】
温和 / 稳健 / 强边界 / 正式 / 高情商 / 不撕破脸 / 快速成交

【是否需要】
策略分析 / 话术生成 / 模拟演练 / 消息润色 / 风险审查 / 谈后确认文本
```

完整模板见 [prompts/input-template.md](prompts/input-template.md)。

## 示例调用 Prompt

### 1. 尾款结算

```text
请使用 negotiation-war-room-skill。

我和甲方口头约定 3 万合作，对方已付 6000。我已经完成账号诊断、选题方案和 2 次陪跑。现在对方说后续不需要服务了，可能不想付剩余款。没有正式合同，但有微信记录、转账记录和交付文档。

请帮我输出：局势判断、信息缺口、权力指数、BATNA/ZOPA、三套结算方案、微信话术、风险审查和谈后确认文本。
```

### 2. 客户压价

```text
请使用 negotiation-war-room-skill。

我给客户报 10 万年度服务，客户说别人 6 万就能做，希望我降价 40%。我最多只能降 10%，低于 9 万就必须缩小服务范围。客户是老客户，认可服务效果，但今年预算紧。

请帮我维护价值、设计不同报价方案，并生成微信回复。
```

### 3. 薪资谈判

```text
请使用 negotiation-war-room-skill。

我拿到一家 AI SaaS 公司的产品经理 Offer，薪资是 32k x 14。我预期是 38k x 14，手上还有一个 35k x 14 的 Offer。岗位职责包括商业化和增长，我有相关项目成果。

请分析我的筹码、市场价值、BATNA/ZOPA，并生成给 HR 的邮件和可能反应的应对话术。
```

### 4. 合伙谈判

```text
请使用 negotiation-war-room-skill。

我和朋友准备做一个本地生活账号。他说他出商家资源，我负责内容、拍摄、剪辑和运营。他希望五五分，但股权、分工、投入、账号归属和退出机制都没谈清楚。

请帮我设计面谈策略、三套合作方案、第一轮话术和谈后确认文本。
```

### 5. 合同条款

```text
请使用 negotiation-war-room-skill。

客户合同里写“甲方满意后付款”，但没有具体验收标准；同时违约责任比较重，没有责任上限。我担心后续尾款和责任风险。

请帮我分析条款风险，给出修改谈判策略，并生成正式邮件。
```

更多示例见 [docs/prompt-examples.md](docs/prompt-examples.md) 和 [examples/](examples/)。

## 示例输出结构

默认输出包括：

```text
【一、当前局势判断】
【二、双方权力指数】
【三、信息缺口】
【四、目标三层模型】
【五、BATNA / ZOPA 分析】
【六、筹码地图】
【七、对方画像】
【八、策略建议】
【九、三套谈判方案】
【十、方案评分】
【十一、第一轮话术】
【十二、对方可能反应与应对】
【十三、发送前风险审查】
【十四、谈后确认文本】
【十五、下一轮行动】
```

完整输出模板见 [prompts/output-template.md](prompts/output-template.md)。

## 文档导航

- [快速开始](docs/quick-start.md)：5 分钟内完成克隆、复制提示词、填写输入和验证输出。
- [适用场景](docs/use-cases.md)：尾款、压价、薪资、合同、合伙、纠纷、熟人和家庭沟通。
- [Agent 集成指南](docs/agent-integration.md)：ChatGPT、Claude、Cursor、Codex、OpenAI Agent 等平台使用方式。
- [示例 Prompt](docs/prompt-examples.md)：20 个高质量调用 Prompt。
- [安全边界](docs/safety-boundaries.md)：禁止用途、高风险请求和专业风险提示。
- [谈判方法论](docs/negotiation-methodology.md)：BATNA、ZOPA、权力指数、MESO、让步交换等。
- [FAQ](docs/faq.md)：常见问题和贡献方式。
- [Roadmap](docs/roadmap.md)：后续计划。

## 项目结构说明

```text
negotiation-war-room-skill/
├── skill.md                 # Skill 核心协议，Agent 调用入口
├── prompts/                 # 系统提示词、输入输出模板、模拟和复盘 Prompt
├── frameworks/              # 谈判框架：BATNA、ZOPA、权力指数、让步、MESO、风险
├── playbooks/               # 各类谈判场景的实战打法
├── templates/               # 微信、邮件、电话、会议、确认和跟进模板
├── examples/                # 完整案例，展示从输入到输出的全过程
├── tests/                   # 测试 Prompt、边界案例、验收清单
├── docs/                    # 使用文档、场景指南、Roadmap、示例 Prompt
├── CONTRIBUTING.md          # 贡献指南
├── SECURITY.md              # 安全边界
├── CHANGELOG.md             # 版本记录
└── LICENSE
```

## 安装 / 使用说明

这不是传统软件包，不需要编译或安装依赖。你可以把它当作 Agent Skill 文档库使用。

### 1. 克隆仓库

```bash
git clone https://github.com/your-name/negotiation-war-room-skill.git
cd negotiation-war-room-skill
```

### 2. 查看核心协议

```bash
cat skill.md
```

### 3. 复制系统提示词

```bash
cat prompts/system-prompt.md
```

将其复制到 ChatGPT、Claude、Cursor、Codex 或你的自建 Agent 的 System Prompt / Rules / Instructions 中。

### 4. 使用测试 Prompt 验证

打开 [tests/test-prompts.md](tests/test-prompts.md)，任选一个 Prompt 交给 Agent，检查输出是否包含：

- 谈判类型判断
- 信息缺口
- 权力指数
- BATNA / ZOPA
- 三套方案
- 方案评分
- 第一轮话术
- 风险审查
- 谈后确认文本

## Roadmap

- [ ] 增加更多行业场景：设计外包、咨询服务、电商代运营、企业软件采购、装修工程。
- [ ] 增加更多中文话术模板：不同强度、不同关系、不同渠道。
- [ ] 增加谈判案例库：成功案例、失败案例、复盘案例。
- [ ] 增加多轮复盘模板：记录每轮对方反馈、策略变化和下一步动作。
- [ ] 增加英文版本：提供 English README、system prompt 和核心模板。

更完整计划见 [docs/roadmap.md](docs/roadmap.md)。

## 贡献方式

欢迎贡献：

- 谈判场景
- 话术模板
- 失败案例
- 成功案例
- 行业 Playbook
- 测试 Prompt
- 安全边界补充

贡献前请阅读 [CONTRIBUTING.md](CONTRIBUTING.md)。请务必脱敏，不要提交真实姓名、手机号、地址、合同编号、公司机密或未经授权的聊天记录。

## Star 支持

如果这个项目帮你提升谈判准备质量，或者帮助你构建更可靠的谈判 Agent，欢迎 Star 支持。

这会帮助更多中文用户发现一个更结构化、可复制、可安全使用的谈判 Skill。

## License

MIT License。详见 [LICENSE](LICENSE)。
