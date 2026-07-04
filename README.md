# AgentScope Skills

想安装 AgentScope Skill？把这个链接发给你的 Agent，并告诉它“请按 README 安装 AgentScope Skill”：`https://github.com/WangHopeDream/agentscope-skills`。

AgentScope Skills 是 AgentScope CLI 的 agent-specific 包装仓库。

核心扫描器属于 `agentscope` 仓库。本仓库只描述不同 agent 应该在什么场景调用 AgentScope、如何调用 CLI、以及如何解释输出结果。

普通用户不需要安装这个仓库也能使用 AgentScope。先安装核心 CLI：

```bash
npm install -g github:WangHopeDream/agentscope
agentscope scan /path/to/workspace --html
```

只有在你需要 Codex Skill、Claude Code command、Cursor rule 或其他 agent-specific wrapper 时，才需要这个仓库。

当前已经包含 Codex、Claude Code、Cursor 三类 wrapper：

```text
codex/agentscope-scan/
  SKILL.md
  agents/openai.yaml
claude-code/agentscope-scan/
  SKILL.md
claude-code/agentscope-scan.md
cursor/skills/agentscope-scan/
  SKILL.md
cursor/rules/agentscope.mdc
cursor/commands/agentscope-scan.md
```

把对应目录或文件复制到目标 agent 平台的推荐位置，即可让 agent 在需要时调用 `agentscope`。

## 发给 Agent 的安装提示

你可以直接把下面这段话发给你的 Agent：

```text
请安装 AgentScope Skill。

Skill 仓库：
https://github.com/WangHopeDream/agentscope-skills

请先安装核心 CLI：
npm install -g github:WangHopeDream/agentscope

然后根据当前 Agent 平台，把 Skill/wrapper 安装到正确位置：
- Codex 项目级：<project>/.agents/skills/agentscope-scan/
- Codex 用户级：~/.codex/skills/agentscope-scan/ 或 ~/.agents/skills/agentscope-scan/
- Claude Code 项目级：<project>/.claude/skills/agentscope-scan/，可选 <project>/.claude/commands/agentscope-scan.md
- Claude Code 用户级：~/.claude/skills/agentscope-scan/，可选 ~/.claude/commands/agentscope-scan.md
- Cursor 项目级：<project>/.cursor/skills/agentscope-scan/，可选 <project>/.cursor/rules/agentscope.mdc 和 <project>/.cursor/commands/agentscope-scan.md
- Cursor 用户级：~/.cursor/skills/agentscope-scan/

安装后，请运行：
agentscope scan <workspace-root> --html --lang zh
```

## 平台安装位置

| 平台 | 当前状态 | 推荐安装位置 |
| --- | --- | --- |
| Codex 项目级 | 已支持 | `<project>/.agents/skills/agentscope-scan/` |
| Codex 用户级 | 已支持 | `~/.codex/skills/agentscope-scan/` 或 `~/.agents/skills/agentscope-scan/` |
| Claude Code 项目级 | 已支持 | `<project>/.claude/skills/agentscope-scan/`，可选 `<project>/.claude/commands/agentscope-scan.md` |
| Claude Code 用户级 | 已支持 | `~/.claude/skills/agentscope-scan/`，可选 `~/.claude/commands/agentscope-scan.md` |
| Cursor 项目级 | 已支持 | `<project>/.cursor/skills/agentscope-scan/`，可选 `<project>/.cursor/rules/agentscope.mdc` |
| Cursor 用户级 | 已支持 | `~/.cursor/skills/agentscope-scan/` |

## 安装顺序

这个仓库里的 Skill/wrapper 不会自动静默安装全局命令。推荐使用顺序是：

1. 先安装核心 CLI。

```bash
npm install -g github:WangHopeDream/agentscope
```

2. 确认 CLI 可用。

```bash
agentscope scan /path/to/workspace --html
```

3. 再把本仓库里的 Skill/wrapper 安装到对应项目或 agent 环境里。

安装完成后，Skill/wrapper 只是负责告诉 agent 什么时候调用 `agentscope`、如何选择项目根目录、如何解释生成的 JSON/HTML 报告。真正的扫描和报告生成仍然由核心 CLI 完成。

## 更新核心 CLI

如果用户让 agent 更新 AgentScope CLI，推荐让 agent 执行：

```bash
npm install -g github:WangHopeDream/agentscope
agentscope --version
```

这会从 GitHub 重新安装最新版本。因为这是全局 npm 安装，agent 应该在执行前明确告诉用户会修改本机全局命令。

## 国际化

默认中文，英文说明附在本 README 下半部分。包装层后续也应该遵循同样规则：

- 默认中文。
- 同时提供英文说明。
- 调用核心 CLI 时可以传 `--lang zh` 或 `--lang en`。

## 计划目录

```text
codex/              Codex Skills 和项目级 Skill 模板。
claude-code/        Claude Code commands 和项目指导。
cursor/             Cursor rule 模板和使用说明。
examples/           小型公开示例。
```

## 与 AgentScope 的关系

```text
Agent-specific wrapper
  -> 调用 agentscope CLI
  -> 读取生成的 JSON/HTML
  -> 为用户总结发现
```

## 当前状态

早期 bootstrap。当前已提供 Codex Skill、Claude Code Skill/command、Cursor Skill/rule/command，全部调用核心 AgentScope CLI，不内置扫描逻辑。

---

# AgentScope Skills

Want to install the AgentScope Skill? Send this link to your agent and say: "Please install the AgentScope Skill according to the README": `https://github.com/WangHopeDream/agentscope-skills`.

AgentScope Skills contains agent-specific wrappers, skills, commands, and usage templates for the AgentScope CLI.

The core scanner belongs in the `agentscope` repository. This repository should only describe when and how different agents call AgentScope, and how they should interpret its outputs.

Users do not need this repository to run AgentScope. Install the core CLI first:

```bash
npm install -g github:WangHopeDream/agentscope
agentscope scan /path/to/workspace --html
```

Use this repository only when adding a Codex Skill, Claude Code command, Cursor rule, or other agent-specific wrapper around the CLI.

This repository currently includes wrappers for Codex, Claude Code, and Cursor:

```text
codex/agentscope-scan/
  SKILL.md
  agents/openai.yaml
claude-code/agentscope-scan/
  SKILL.md
claude-code/agentscope-scan.md
cursor/skills/agentscope-scan/
  SKILL.md
cursor/rules/agentscope.mdc
cursor/commands/agentscope-scan.md
```

Copy the relevant directory or file into the target agent platform's recommended location so the agent can call `agentscope` when needed.

## Prompt To Send To Your Agent

You can send this directly to your agent:

```text
Please install the AgentScope Skill.

Skill repository:
https://github.com/WangHopeDream/agentscope-skills

First install the core CLI:
npm install -g github:WangHopeDream/agentscope

Then install the Skill/wrapper for the current agent platform:
- Codex project-level: <project>/.agents/skills/agentscope-scan/
- Codex user-level: ~/.codex/skills/agentscope-scan/ or ~/.agents/skills/agentscope-scan/
- Claude Code project-level: <project>/.claude/skills/agentscope-scan/, optional <project>/.claude/commands/agentscope-scan.md
- Claude Code user-level: ~/.claude/skills/agentscope-scan/, optional ~/.claude/commands/agentscope-scan.md
- Cursor project-level: <project>/.cursor/skills/agentscope-scan/, optional <project>/.cursor/rules/agentscope.mdc and <project>/.cursor/commands/agentscope-scan.md
- Cursor user-level: ~/.cursor/skills/agentscope-scan/

After installation, run:
agentscope scan <workspace-root> --html --lang zh
```

## Platform Install Locations

| Platform | Current status | Recommended location |
| --- | --- | --- |
| Codex project-level | Supported | `<project>/.agents/skills/agentscope-scan/` |
| Codex user-level | Supported | `~/.codex/skills/agentscope-scan/` or `~/.agents/skills/agentscope-scan/` |
| Claude Code project-level | Supported | `<project>/.claude/skills/agentscope-scan/`, optional `<project>/.claude/commands/agentscope-scan.md` |
| Claude Code user-level | Supported | `~/.claude/skills/agentscope-scan/`, optional `~/.claude/commands/agentscope-scan.md` |
| Cursor project-level | Supported | `<project>/.cursor/skills/agentscope-scan/`, optional `<project>/.cursor/rules/agentscope.mdc` |
| Cursor user-level | Supported | `~/.cursor/skills/agentscope-scan/` |

## Installation Order

The skills and wrappers in this repository do not silently install a global command. Recommended setup:

1. Install the core CLI first.

```bash
npm install -g github:WangHopeDream/agentscope
```

2. Confirm the CLI works.

```bash
agentscope scan /path/to/workspace --html
```

3. Then install the Skill/wrapper from this repository into the target project or agent environment.

After installation, the Skill/wrapper tells the agent when to call `agentscope`, how to choose the workspace root, and how to interpret the generated JSON/HTML report. The core CLI still performs the actual scan and report generation.

## Updating The Core CLI

If the user asks the agent to update AgentScope CLI, the recommended command is:

```bash
npm install -g github:WangHopeDream/agentscope
agentscope --version
```

This reinstalls the latest version from GitHub. Because this changes a global npm command, the agent should clearly tell the user before running it.

## Internationalization

Chinese is the default language, with English documentation included in the second half of this README. Wrappers should follow the same rule:

- Chinese by default.
- English documentation included.
- Pass `--lang zh` or `--lang en` when calling the core CLI.

## Planned Layout

```text
codex/              Codex skills and project-local skill templates.
claude-code/        Claude Code commands and project guidance.
cursor/             Cursor rule templates and usage notes.
examples/           Small public examples.
```

## Relationship to AgentScope

```text
Agent-specific wrapper
  -> calls agentscope CLI
  -> reads generated JSON/HTML
  -> summarizes findings for the user
```

## Status

Early bootstrap. The repository now includes a Codex Skill, Claude Code Skill/command, and Cursor Skill/rule/command. All wrappers call the core AgentScope CLI instead of embedding scanner logic.
