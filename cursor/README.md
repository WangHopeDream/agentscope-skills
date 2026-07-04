# Cursor

AgentScope 的 Cursor 包装层。

推荐安装为 Cursor Agent Skill：

```text
<project>/.cursor/skills/agentscope-scan/SKILL.md
```

把 `cursor/skills/agentscope-scan/` 复制到该位置即可。用户级 Skill 安装位置：

```text
~/.cursor/skills/agentscope-scan/
```

如果你想让 Cursor 在项目规则里知道什么时候使用 AgentScope，也可以安装规则文件：

```text
<project>/.cursor/rules/agentscope.mdc
```

对应源文件是：

```text
cursor/rules/agentscope.mdc
```

仓库里还提供可选 command 文件：

```text
cursor/commands/agentscope-scan.md
```

先安装或更新核心 CLI：

```bash
npm install -g github:WangHopeDream/agentscope
agentscope --version
```

默认扫描：

```bash
agentscope scan <workspace-root> --html --lang zh
```

如果用户只想扫描项目内文件，使用 `--project-only`。

---

# Cursor

Cursor wrapper for AgentScope.

Recommended install is a Cursor Agent Skill:

```text
<project>/.cursor/skills/agentscope-scan/SKILL.md
```

Copy `cursor/skills/agentscope-scan/` to that location. For user-level skill install, copy it to:

```text
~/.cursor/skills/agentscope-scan/
```

To teach Cursor project rules when to use AgentScope, also install:

```text
<project>/.cursor/rules/agentscope.mdc
```

Source file:

```text
cursor/rules/agentscope.mdc
```

An optional command file is also included:

```text
cursor/commands/agentscope-scan.md
```

Install or update the core CLI first:

```bash
npm install -g github:WangHopeDream/agentscope
agentscope --version
```

Default scan:

```bash
agentscope scan <workspace-root> --html --lang zh
```

Use `--project-only` when the user wants to avoid user-level agent settings.
