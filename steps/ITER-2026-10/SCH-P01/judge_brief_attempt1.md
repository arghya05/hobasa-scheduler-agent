# Evaluate step SCH-P01: Maintain calendar rules for ITER-2026-10

- Workbook action: Record iteration dates, release train dates, the PROD window (11 am–12 pm, day after system demo), timezone and holidays
- Workbook outcome: Approved calendar rules

## Outputs to evaluate
- `hobasa-agentic-sdlc/org/org.calendar_rules.md`

## Inputs the agent was given
- org.calendar_rules: `hobasa-scheduler-agent/inputs/ITER-2026-10/SCH-P01/org.calendar_rules.md`

## Trigger event
{"iteration": "ITER-2026-10", "calendar_date": "2026-10-25"}

Shared memory and conventions: `memory/MEMORY.md` and `CLAUDE.md` in the SDLC repository.

## The step brief the agent was given (a valid source, cited as record:brief)

# Step SCH-P01: Maintain calendar rules (attempt 1) for ITER-2026-10

- Workbook trigger: Start of each release train; change to holidays or the PROD window
- Workbook action: Record iteration dates, release train dates, the PROD window (11 am–12 pm, day after system demo), timezone and holidays
- Workbook outcome: Approved calendar rules

## Inputs (GitHub checkout; read them with Read, or context_get for a receipt)
- org.calendar_rules (Iterations, release train, PROD window, timezone, holidays): `hobasa-scheduler-agent/inputs/ITER-2026-10/SCH-P01/org.calendar_rules.md` (from hobasa-agentic-sdlc/org/org.calendar_rules.md at commit 9404ef3)

## Outputs (write each file in full; the spine commits and pushes after evaluation and approval)
- org.calendar_rules (Iterations, release train, PROD window, timezone, holidays): write `hobasa-agentic-sdlc/org/org.calendar_rules.md`


## How to work
Decide the best way to do this step from the inputs and the workbook action, plan it (TodoWrite for multi-part work), then do it. Helper subagents you can delegate to: explorer, verifier (use the verifier before you finish when the output makes many factual statements). Use the shared memory (memory_search) for decisions and lessons. Connectors approved for you: api:github (GitHub REST API for the Hobasa repositories: issues, pull requests, checks (GET /repos/<owner>/<repo>/...)). Use one only when your inputs do not hold what you need; request a missing one with capability_request.

## Trigger event (cite as record:intake)
{
  "iteration": "ITER-2026-10",
  "calendar_date": "2026-10-25"
}

Finish with the structured result: approach, tools_used, claims (each citing an input item name, a tool view, api:<name>, mcp:<server>, record:intake, record:owner_answer, record:memory or record:brief for this brief; a claim drawing on several sources lists them separated by ';'; every number must appear in what you cite), open questions (BLOCKING: only when you cannot finish), summary.