# AgentScope Skills

AgentScope Skills 是 AgentScope CLI 的 agent-specific 包装仓库。

核心扫描器属于 `agentscope` 仓库。本仓库只描述不同 agent 应该在什么场景调用 AgentScope、如何调用 CLI、以及如何解释输出结果。

普通用户不需要安装这个仓库也能使用 AgentScope。先安装核心 CLI：

```bash
npm install -g github:WangHopeDream/agentscope
agentscope scan /path/to/workspace --html
```

只有在你需要 Codex Skill、Claude Code command、Cursor rule 或其他 agent-specific wrapper 时，才需要这个仓库。

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

早期 bootstrap。第一个 wrapper 会在核心 CLI 边界稳定后，从现有 `project-workflow-map` Codex Skill 中抽取。

---

# AgentScope Skills

AgentScope Skills contains agent-specific wrappers, skills, commands, and usage templates for the AgentScope CLI.

The core scanner belongs in the `agentscope` repository. This repository should only describe when and how different agents call AgentScope, and how they should interpret its outputs.

Users do not need this repository to run AgentScope. Install the core CLI first:

```bash
npm install -g github:WangHopeDream/agentscope
agentscope scan /path/to/workspace --html
```

Use this repository only when adding a Codex Skill, Claude Code command, Cursor rule, or other agent-specific wrapper around the CLI.

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

Early bootstrap. The first wrapper will be extracted from the existing `project-workflow-map` Codex skill after the CLI boundary is defined.
