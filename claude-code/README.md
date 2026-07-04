# Claude Code

AgentScope 的 Claude Code 包装层。

推荐安装为 Claude Code Skill：

```text
<project>/.claude/skills/agentscope-scan/SKILL.md
```

把 `claude-code/agentscope-scan/` 复制到该位置即可。用户级安装位置：

```text
~/.claude/skills/agentscope-scan/
```

仓库里也提供兼容 command 的文件：

```text
claude-code/agentscope-scan.md
```

如需旧 command 形态，把它复制到 `.claude/commands/agentscope-scan.md` 或 `~/.claude/commands/agentscope-scan.md`。

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

# Claude Code

Claude Code wrapper for AgentScope.

Recommended install is a Claude Code Skill:

```text
<project>/.claude/skills/agentscope-scan/SKILL.md
```

Copy `claude-code/agentscope-scan/` to that location. For user-level install, copy it to:

```text
~/.claude/skills/agentscope-scan/
```

The repository also includes a command-compatible file:

```text
claude-code/agentscope-scan.md
```

Copy it to `.claude/commands/agentscope-scan.md` or `~/.claude/commands/agentscope-scan.md` when you want the legacy command layout.

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
