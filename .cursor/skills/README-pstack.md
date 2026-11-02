# pstack（仓库内副本）

更新日期：2026-11-02

Marketplace 插件在 Cloud Agent 里经常加载不到。官方做法是把技能提交到 `.cursor/skills/<name>/SKILL.md`，让代理从本次 checkout 读取。

本目录是 [Lauren Tan 的 pstack](https://github.com/cursor/plugins/tree/main/pstack) 技能的完整副本（MIT）。来源提交 `ae5650febf4320793844c12c4adaa937f417f8da`（`cursor/plugins` `main`，2026-10-31），插件版本 `0.15.36`。许可全文见同目录 `pstack-LICENSE`。

- **入口技能是 `poteto-mode`。** Cloud Agent 应从本仓库技能调用 `/poteto-mode`，不要依赖 Marketplace 插件是否已挂载。同目录下的 `how`、`why`、`architect`、`arena`、`interrogate`、`tdd`、`unslop`、`setup-pstack`、`poteto-help` 以及全部 `principle-*` 技能会随 playbook 被引用；相对路径是 `../<name>/SKILL.md`。
- **本地 Cursor 仍使用 Marketplace 插件**（`/add-plugin pstack`）。桌面端以插件为准，避免和这份副本抢同名技能。
- **Cloud Agent 从本仓库技能调用 `/poteto-mode`。** 需要选模型时再跑 `/setup-pstack`（它写入用户级 `~/.cursor/rules/pstack-models.mdc`，不在本仓库里）。

## 子代理

`pstack/agents/` 里的 `poteto-agent` 和 `comment-sicko` 放在 `.cursor/agents/`。这是 Cursor 项目级自定义子代理的目录（Markdown，带 `name` / `description` frontmatter），Cloud Agent 可以从 checkout 加载这两个 `subagent_type`。本地 Marketplace 插件仍提供同名子代理。

## 技能（58）

`architect`、`arena`、`automate-me`、`benchmark-checklist`、`blast-radius`、`bro`、`correct`、`create-formal-verification-skill`、`create-verification-skill`、`figure-it-out`、`how`、`in-your-own-words`、`interrogate`、`ketchup`、`ketchup-video`、`maintain-formal-verification-skill`、`maintain-verification-skill`、`make-bot-ui`、`no-comments`、`poteto-help`、`poteto-mode`、`recall`、`reflect`、`setup-pstack`、`sharpen`、`show-me-your-work`、`statechart`、`swarm`、`tdd`、`teach`、`technical-writing`、`typescript-best-practices`、`unslop`、`why`，以及 24 个 `principle-*` 技能。

每个技能目录都含 `SKILL.md`，playbook、references、scripts 一并保留。更新时只覆盖已经是同一 pstack 技能的目录，不删除 Spec Kit 或其他无关文件。
