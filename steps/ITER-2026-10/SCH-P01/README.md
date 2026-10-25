# SCH-P01 Maintain calendar rules (Scheduler agent)

**Item:** ITER-2026-10 · **status:** done
**Trigger:** Start of each release train; change to holidays or the PROD window  
**Action:** Record iteration dates, release train dates, the PROD window (11 am–12 pm, day after system demo), timezone and holidays  
**Outcome expected:** Approved calendar rules

## Inputs (what the agent was given)

| Item | Prepared input (this repository) | Read from (producer in GitHub) | Commit | Produced by |
|---|---|---|---|---|
| org.calendar_rules | hobasa-scheduler-agent/inputs/ITER-2026-10/SCH-P01/org.calendar_rules.md | hobasa-agentic-sdlc/org/org.calendar_rules.md | 2038404 | source |

Full brief per attempt: `brief_attempt<N>.md` (trigger event, owner answers, tool view, refusal reasons).

## Outputs (what the agent produced)

| Item | GitHub file |
|---|---|
| org.calendar_rules | hobasa-agentic-sdlc/org/org.calendar_rules.md |

## How the agent worked

- Approach: Read the single input and the scheduler-steps skill. The input already held the system demo, PROD window, timezone and holidays, so I kept those unchanged. I searched the repository for iteration and release train dates and found none, so those sections stay "not recorded" and are not guessed. I used no connector. A shell command was blocked by the G9 hook for this step, so I did not diff the input against the existing output file.
- Tools used: Skill, Read, Grep, Write
- Helper subagents: none
- Connector calls: none

## Attempts (checks before any person saw the output)

| Attempt | Session | Checks failed | Judge unsupported | Judge scores |
|---|---|---|---|---|
| 1 | new | 0 | 0 | {'correct': 5, 'complete': 3, 'grounded': 5, 'useful': 3} |

Details: `result_attempt<N>.json` (claims with sources), `checks_attempt<N>.json`, `judge_attempt<N>.json`.

## Human evaluation

| Role | By | Decision | Scores | Comment or reason |
|---|---|---|---|---|
| RTE | sim.rte | approve | — | automated checks and the independent judge passed |
