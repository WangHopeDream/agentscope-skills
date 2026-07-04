# AgentScope Skills

AgentScope Skills contains agent-specific wrappers, skills, commands, and usage
templates for the AgentScope CLI.

The core scanner belongs in the `agentscope` repository. This repository should
only describe when and how different agents call AgentScope, and how they should
interpret its outputs.

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

Early bootstrap. The first wrapper will be extracted from the existing
`project-workflow-map` Codex skill after the CLI boundary is defined.
