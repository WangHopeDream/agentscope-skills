# Codex

Codex-specific AgentScope wrappers will live here.

## 安装顺序

先安装核心 CLI：

```bash
npm install -g github:WangHopeDream/agentscope
agentscope scan /path/to/workspace --html
```

然后再把 Codex Skill 安装到项目级或用户级 Skill 目录。Skill 本身不会替代 CLI，也不应该默认静默安装全局 npm 包；它只是让 Codex 知道什么时候调用 `agentscope scan`，以及如何向用户解释报告。

第一版目标是把现有 `project-workflow-map` Skill 迁移成一个轻量 wrapper：调用 AgentScope CLI，而不是在 Skill 里嵌入所有扫描和渲染逻辑。

---

Codex-specific AgentScope wrappers will live here.

## Installation Order

Install the core CLI first:

```bash
npm install -g github:WangHopeDream/agentscope
agentscope scan /path/to/workspace --html
```

Then install the Codex Skill into a project-level or user-level Skill directory. The Skill does not replace the CLI and should not silently install a global npm package by default; it simply tells Codex when to call `agentscope scan` and how to explain the report to the user.

The first target is a portable version of the current `project-workflow-map`
skill that calls the AgentScope CLI instead of embedding all scanner logic in a
single skill script.
