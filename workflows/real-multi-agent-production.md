# Real Multi-Agent Production Workflow

## Execution Modes

- `real_multi_agent`: actual subagents or independent model calls were used and each has a handoff record.
- `single_agent_with_reviews`: one assistant used multiple review perspectives without independent agent execution.
- `single_agent_direct`: one assistant produced the artifact directly.

## Minimum Real Multi-Agent Run

1. 总控制片人 creates `00-orchestrator-brief.md`.
2. 口播编剧 Agent receives the brief and returns script output.
3. 剪辑/平台优化 Agent receives the brief plus script and returns platform/editing output.
4. 审核 Agent reviews the merged output for IP fit, platform fit, compliance, and conversion path.
5. 总控制片人 creates `06-final-merge-report.md` and states the true execution mode.

## Required Evidence

Each real agent stage must include:

- Agent name
- Run/source id when available
- Input received
- Output produced
- Decisions made
- Risks
- Files created/changed

Without this evidence, do not claim `real_multi_agent`.
