# Copilot SDK Harness Engineering Example

This example recreates the *behavior pattern* of a harnessed coding agent using the GitHub Copilot SDK:

- one **orchestrator** session
- specialized **sub-agents**
- **MCP** tool wiring
- a structured **journal** for every step
- a hard **verification loop** before completion

It is designed as a minimal starting point for reproducing the kind of workflow often shown in agent-harness demos:

1. clarify the goal
2. inspect the workspace
3. delegate planning
4. implement narrowly
5. run validation
6. review against intent
7. return evidence, not vibes

## What this includes

```text
copilot_sdk_harness/
├── README.md
├── package.json
├── tsconfig.json
└── src/
    ├── index.ts
    ├── agents.ts
    └── journal.ts
```

## Requirements

- Node.js 20+
- a Copilot SDK-compatible environment
- optional local MCP servers for filesystem, repo tools, or browser automation

## Install

```bash
cd tutorials/copilot_sdk_harness
npm install
```

## Run

```bash
npm run dev -- "Implement a small feature and prove it works"
```

## How the harness works

The example uses four roles:

- `planner` for decomposition and validation planning
- `coder` for small code changes
- `tester` for narrow validation first, broad validation second
- `reviewer` for completeness and regression checks

The orchestrator forces this order:

1. plan
2. code
3. test
4. review
5. summarize with evidence

That is the real harness move. Not mystical chain-of-thought theater. Just disciplined process, scoped tools, and visible checkpoints.

## Next steps

Useful upgrades:

- add a `browser` MCP server backed by Playwright
- persist journal entries as JSONL
- add a `fixBug` and `reviewPR` workflow
- route to different sub-agents by task type
- block completion when tests or review fail
