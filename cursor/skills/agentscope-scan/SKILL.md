---
name: agentscope-scan
description: Use when Cursor should inspect an agent-native workspace with AgentScope, generate or refresh an HTML/JSON report, or explain visible rules, skills, commands, tools, scripts, configs, risks, and inferred workflows.
---

# AgentScope Scan

Use the AgentScope CLI for the scan. This skill only decides when and how to call the CLI.

## Prerequisite

Check the CLI:

```bash
agentscope --version
```

If it is not installed, tell the user and install from GitHub:

```bash
npm install -g github:WangHopeDream/agentscope
agentscope --version
```

## Workflow

1. Identify the workspace root from the user's request or the current project.
2. Generate HTML for review: `agentscope scan <workspace-root> --html --lang zh`.
3. Generate JSON for automation: `agentscope scan <workspace-root> --json --output agentscope-scan.json --lang zh`.
4. Use `--project-only` when the user wants to avoid user-level agent settings.
5. Report the output path and summarize adapters, rules, skills, commands, configs, diagnostics, and child repositories.

## Guardrails

- Do not upload generated reports unless the user explicitly asks.
- Keep public examples synthetic.
- Let the CLI perform scanning instead of duplicating scanner logic in Cursor prompts.
