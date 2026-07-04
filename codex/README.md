# Codex

这里存放 Codex-specific AgentScope wrappers。

当前可用 Skill：

```text
agentscope-scan/
  SKILL.md
  agents/openai.yaml
```

安装方式：

```bash
mkdir -p /path/to/project/.agents/skills
cp -R codex/agentscope-scan /path/to/project/.agents/skills/agentscope-scan
```

然后在 Codex 里使用：

```text
Use $agentscope-scan to inspect this workspace.
```

## 安装顺序

先安装核心 CLI：

```bash
npm install -g github:WangHopeDream/agentscope
agentscope scan /path/to/workspace --html
```

然后再把 Codex Skill 安装到项目级或用户级 Skill 目录。Skill 本身不会替代 CLI，也不应该默认静默安装全局 npm 包；它只是让 Codex 知道什么时候调用 `agentscope scan`，以及如何向用户解释报告。

## 更新 CLI

当用户要求更新 AgentScope CLI 时，让 Codex 执行：

```bash
npm install -g github:WangHopeDream/agentscope
agentscope --version
```

执行前应该说明这是一次全局 npm 命令更新。

这个 Skill 是轻量 wrapper：调用 AgentScope CLI，而不是在 Skill 里嵌入所有扫描和渲染逻辑。

---

Codex-specific AgentScope wrappers live here.

Available Skill:

```text
agentscope-scan/
  SKILL.md
  agents/openai.yaml
```

Install it into a project:

```bash
mkdir -p /path/to/project/.agents/skills
cp -R codex/agentscope-scan /path/to/project/.agents/skills/agentscope-scan
```

Then ask Codex:

```text
Use $agentscope-scan to inspect this workspace.
```

## Installation Order

Install the core CLI first:

```bash
npm install -g github:WangHopeDream/agentscope
agentscope scan /path/to/workspace --html
```

Then install the Codex Skill into a project-level or user-level Skill directory. The Skill does not replace the CLI and should not silently install a global npm package by default; it simply tells Codex when to call `agentscope scan` and how to explain the report to the user.

## Updating The CLI

When the user asks to update AgentScope CLI, have Codex run:

```bash
npm install -g github:WangHopeDream/agentscope
agentscope --version
```

Before running it, Codex should explain that this updates a global npm command.

This Skill is a thin wrapper: it calls the AgentScope CLI instead of embedding all scanner and renderer logic inside the Skill.
