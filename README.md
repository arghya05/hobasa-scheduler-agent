# Hobasa Scheduler agent

Scheduler Agent in the Hobasa agentic SDLC. Owner: RTE and SM (definition in Phase 2).. It runs on Claude Code: every step is one Claude Code session started by the Hobasa spine, with this agent's prompt and step skill (`.claude/`), helper subagents, guardrail hooks and the shared context server.

**Reads from GitHub:** each step's inputs are prepared in `inputs/<trace>/<STEP>/` with the repository, path and commit they came from (other agents' `outputs/`, the requirements and organisation sources in `hobasa-agentic-sdlc`, code in the `*-sample` repositories).

**Writes back to GitHub:** approved outputs in `outputs/<trace>/`; every step run in `steps/<trace>/<STEP>/` (brief, attempts, claims, checks, independent judge, human decision). Code changes go to the `*-sample` repositories. Journey, evaluations and shared memory: `hobasa-agentic-sdlc`.

## Steps

| Step | Name | Reads | Writes | Gate |
|---|---|---|---|---|
| SCH-P01 | Maintain calendar rules (proposed) | org.calendar_rules | org.calendar_rules | RTE |
| SCH-P02 | Schedule ceremonies (proposed) | org.calendar_rules, org.capacity | iter.events | SM |
| SCH-P03 | Schedule releases and deployment windows (proposed) | feat.uat_signoff, org.calendar_rules | feat.release_slot | Release approver |
| SCH-P04 | Resolve conflicts and changes (proposed) | org.calendar_rules, org.capacity | iter.events | SM |
| SCH-P05 | Remind and escalate pending decisions (proposed) | org.trace_ledger | summary only | checks + sampled evaluation |
