---
name: scheduler-steps
description: Procedures, inputs, outputs and gates for every Scheduler agent step in the Hobasa agentic SDLC. Use when running any SCH-P01, SCH-P02, SCH-P03, SCH-P04, SCH-P05 step.
---

# Scheduler agent steps

## SCH-P01 Maintain calendar rules (proposed)

- Trigger: Start of each release train; change to holidays or the PROD window
- Action: Record iteration dates, release train dates, the PROD window (11 am–12 pm, day after system demo), timezone and holidays
- Outcome: Approved calendar rules
- Reads: org.calendar_rules
- Writes: org.calendar_rules
- Gate: RTE

## SCH-P02 Schedule ceremonies (proposed)

- Trigger: Calendar rules approved; new iteration
- Action: Create events for iteration planning, daily coordination, review, retrospective, predemo and system demo; check attendee leave and capacity
- Outcome: Calendar events with attendees
- Reads: org.calendar_rules, org.capacity
- Writes: iter.events
- Gate: SM

## SCH-P03 Schedule releases and deployment windows (proposed)

- Trigger: UAT sign-off (REL-02)
- Action: Propose the next PROD slot inside the window; reserve approvers and on-call; hand the slot to Deployment Step 7
- Outcome: Scheduled PROD deployment slot
- Reads: feat.uat_signoff, org.calendar_rules
- Writes: feat.release_slot
- Gate: Release approver

## SCH-P04 Resolve conflicts and changes (proposed)

- Trigger: Holiday, leave, overlap or cancellation
- Action: Detect conflicts; propose a reschedule; apply only after approval; notify attendees
- Outcome: Rescheduled or cancelled events
- Reads: org.calendar_rules, org.capacity
- Writes: iter.events
- Gate: SM

## SCH-P05 Remind and escalate pending decisions (proposed)

- Trigger: Gate decision due within 1 working day; overdue gate
- Action: Send a reminder with work ID, gate, decision needed and link; escalate overdue items to the named substitute
- Outcome: Reminder or escalation logged
- Reads: org.trace_ledger
- Writes: none (summary only)
- Gate: automated checks; sampled human evaluation

