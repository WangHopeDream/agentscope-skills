---
description: Run AgentScope to inspect the current agent workspace and generate a report.
argument-hint: "[workspace-root]"
---

# AgentScope Scan

Use this command when the user asks to inspect, map, refresh, or explain an agent workspace.

First confirm the CLI:

```bash
agentscope --version
```

If it is missing, install it after telling the user:

```bash
npm install -g github:WangHopeDream/agentscope
```

Run the scan:

```bash
agentscope scan . --html --lang zh
```

Use a user-provided workspace path instead of `.` when provided. Use `--project-only` when the user wants project-local files only.

Return the generated HTML path and summarize adapters, rules, skills, commands, configs, diagnostics, and child repositories.
