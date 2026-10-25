# SCH-P01 Maintain calendar rules (Scheduler agent)

**Item:** ITER-2026-10 · **status:** done
**Trigger:** Start of each release train; change to holidays or the PROD window  
**Action:** Record iteration dates, release train dates, the PROD window (11 am–12 pm, day after system demo), timezone and holidays  
**Outcome expected:** Approved calendar rules

## Inputs (what the agent was given)

| Item | Prepared input (this repository) | Read from (producer in GitHub) | Commit | Produced by |
|---|---|---|---|---|
| org.calendar_rules | hobasa-scheduler-agent/inputs/ITER-2026-10/SCH-P01/org.calendar_rules.md | hobasa-agentic-sdlc/org/org.calendar_rules.md | 9404ef3 | source |

Full brief per attempt: `brief_attempt<N>.md` (trigger event, owner answers, tool view, refusal reasons).

## Outputs (what the agent produced)

| Item | GitHub file |
|---|---|
| org.calendar_rules | hobasa-agentic-sdlc/org/org.calendar_rules.md |

## How the agent worked

- Approach: The only input is a one-paragraph calendar rules file. I restated its facts in a structured layout and did not invent the iteration or release train dates it lacks. This attempt removes the reference to a named role as the owner of the open items, because no input names one. The gaps are non-blocking open questions with no addressee. I didn't use connectors or the verifier, because the output is a few facts taken straight from the input.
- Tools used: Read, Skill, Write
- Helper subagents: none
- Connector calls: none

## Attempts (checks before any person saw the output)

| Attempt | Session | Checks failed | Judge unsupported | Judge scores |
|---|---|---|---|---|
| 1 | new | 1 | 1 | {'correct': 5, 'complete': 3, 'grounded': 4, 'useful': 4} |
| 2 | resumed | 0 | 0 | {'correct': 5, 'complete': 3, 'grounded': 5, 'useful': 3} |

Details: `result_attempt<N>.json` (claims with sources), `checks_attempt<N>.json`, `judge_attempt<N>.json`.

## Human evaluation

| Role | By | Decision | Scores | Comment or reason |
|---|---|---|---|---|
| RTE | sim.rte | approve | — | automated checks and the independent judge passed |
