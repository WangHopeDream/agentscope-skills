---
name: agentscope-scan
description: Use when the user wants to install, update, or run AgentScope to inspect an agent-native workspace, generate an AgentScope HTML/JSON report, map Codex/Claude Code/Cursor rules and skills, or understand a project's agent operating layer.
---

# AgentScope Scan

## Purpose

Use the AgentScope CLI to inspect an agent-native workspace and generate a self-contained report.

Default language is Chinese. Use `--lang en` only when the user asks for English output.

## Workflow

1. Identify the target workspace root.
   - Default to the current working directory.
   - If the user names a path, use that path.
   - Do not promote automatically to a Git repository root; AgentScope workspaces may contain multiple child repositories.

2. Ensure the AgentScope CLI is installed.
   - Check:

```bash
command -v agentscope
```

   - If missing, tell the user that AgentScope CLI needs to be installed as a global npm command, then run:

```bash
npm install -g github:WangHopeDream/agentscope
```

   - Confirm:

```bash
agentscope --version
```

3. For update requests, reinstall the CLI from GitHub.

```bash
npm install -g github:WangHopeDream/agentscope
agentscope --version
```

4. Generate the report.
   - Chinese default:

```bash
agentscope scan <workspace-root> --html --lang zh
```

   - English output:

```bash
agentscope scan <workspace-root> --html --lang en
```

   - JSON plus HTML when the user asks for machine-readable output:

```bash
agentscope scan <workspace-root> --json --output agentscope-scan.json --html --html-output agentscope-report.html --lang zh
```

5. Verify the result.
   - Confirm the command exits successfully.
   - Confirm the generated HTML file exists.
   - Default HTML path is `<workspace-root>/agentscope-report.html` unless `--html-output` is provided.

6. Report the output path and key counts.
   - Keep the final response short.
   - Mention whether the report used Chinese or English.

## Guardrails

- Do not upload generated reports anywhere.
- Do not commit generated reports, scan JSON, local `.env`, local agent state, or private project data.
- Before installing or updating the global npm CLI, clearly tell the user this changes a global command on their machine.
- If npm is unavailable, explain that AgentScope currently requires Node.js/npm and stop.
- Treat generated reports as local artifacts that may contain private workspace structure.

---

# English Notes

This Skill is a thin wrapper. The actual scanner and renderer live in the `agentscope` CLI.

Installation:

```bash
npm install -g github:WangHopeDream/agentscope
```

Run:

```bash
agentscope scan <workspace-root> --html --lang en
```

Update:

```bash
npm install -g github:WangHopeDream/agentscope
agentscope --version
```
