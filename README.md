# technical-writing

中文内部技术写作的 agent skill。约束设计文档、评审稿、postmortem、分享稿等场景的语气、句法、结构，让产出贴近技术汇报，避开营销稿和散文气质。

## 适用场景

- 写内部技术方案、设计说明、评审文档、分享稿
- 改一篇文风过满、结论过快、证据不足的技术文章
- 把聊天记录、讨论结论整理成可传播的技术文档
- 解释代码、模块边界、架构演进、可观测性、评测方法

不适用：UI 文案、产品营销稿、面向外部用户的帮助文档、机械 API reference。

## 安装

### Claude Code

```bash
git clone https://github.com/luoling8192/technical-writing.git ~/repos/technical-writing
mkdir -p ~/.claude/skills
ln -s ~/repos/technical-writing ~/.claude/skills/technical-writing
```

或者通过 `~/.agents/skills/` 注册（推荐，可被其他 agent runtime 共享）：

```bash
mkdir -p ~/.agents/skills ~/.claude/skills
ln -s ~/repos/technical-writing ~/.agents/skills/technical-writing
ln -s ../../.agents/skills/technical-writing ~/.claude/skills/technical-writing
```

启动 Claude Code 后用 Skill 工具调用 `technical-writing`，或在 CLAUDE.md 里把它列为常用 skill。

### OpenAI Codex

`agents/openai.yaml` 是 Codex agent 配置，按 Codex 文档注册到本地即可。

## 核心约束

- 先观察，再归纳，再判断，不抢结论
- 中文里不用破折号 `—` 和英文连字符 `-` 做分句
- 中文引号统一用 `「」`
- 不要黑话连篇（完整词表见 SKILL.md 的 Buzzword Blocklist）
- 不写抢结论的词、空评价词、对立句法、过场句、英文翻译腔
- 结构信息直接用 list，论证顺序用 `1. 2. 3. 4.`
- 长文主线：背景 → 拆解现状 → 提出猜想 → 分节解答 → 回指前文 → 影响面 → 可观测性 / eval → 收束

完整规则、改写示例、Few-Shot 修正案例见 [`SKILL.md`](./SKILL.md)。

## Credits

灵感和反馈来自 [@nekomeowww](https://github.com/nekomeowww)。

## License

MIT
