---
name: agentscope-scan
description: Use when the user asks Claude Code to inspect an agent workspace with AgentScope, generate an HTML or JSON report, refresh an existing AgentScope report, or explain visible rules, skills, commands, tools, scripts, configs, risks, and inferred workflows.
---

# AgentScope Scan

Use the AgentScope CLI as the scanner. This skill is a wrapper; it should not reimplement scanning logic.

## Prerequisite

Confirm the CLI is available:

```bash
agentscope --version
```

If it is missing or the user asks to update it, install the latest GitHub version:

```bash
npm install -g github:WangHopeDream/agentscope
agentscope --version
```

Tell the user before changing a global npm command.

## Workflow

1. Identify the workspace root. Prefer the current project root unless the user gives a path.
2. For a human-readable report, run `agentscope scan <workspace-root> --html --lang zh`.
3. For automation or comparison, run `agentscope scan <workspace-root> --json --output agentscope-scan.json --lang zh`.
4. If the user asks to refresh an existing report, reuse the report's copied refresh command when available.
5. Share the generated file path and summarize key counts: adapters, rules, skills, commands, configs, diagnostics, and child repositories.

## Output

Return concise Chinese by default unless the user asks for English. Include the HTML path when an HTML report is generated.

## Guardrails

- Do not include private local reports or user-specific files in public examples.
- Do not silently upload generated reports.
- Use `--project-only` when the user wants to avoid scanning user-level agent settings.
