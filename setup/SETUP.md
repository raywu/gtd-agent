# Setup

Goal: work with the user to design their GTD system before touching production data.

## 1. Understand the user’s GTD practice

Interview one question at a time.

Cover only what is needed.

### Commitments and dates
- What does a due date mean?
- Are due dates hard deadlines, reminder dates, or both?
- Should active tasks always have due dates?
- How should overdue tasks behave?

### Status model
- Which statuses are actually useful?
- What does Next Action mean?
- How are Waiting For items handled?
- Is there a future/incubating state?
- How is Someday/Maybe used?

### Recurrence
- Which tasks recur?
- Is the next date based on the scheduled date or completion date?
- Should recurring completion create history?

### Attention
- Should the agent decide when a task needs attention?
- What signals may it use?
- What must it never infer?
- Should surfaced tasks remain surfaced until explicitly processed?
- How does the user want to correct bad timing judgments?

### Capture
- How should a new task be added?
- What should the agent infer?
- What requires confirmation?
- Are notes free-form?
- Are attachments important?

### Reviews
- What belongs in daily review?
- What belongs in weekly review?
- What is intentionally excluded?
- What happens when reviews are missed?

### Autonomy
Define what the agent may do automatically versus what requires explicit instruction.

## 2. Propose the smallest workable model

Do not add fields just because a database supports them.

Prefer the minimum state necessary to support the user’s workflow.

Typical categories may include:
- task title
- status
- due date
- notes
- recurrence
- attachment reference
- completion state
- system-managed attention state

These are examples, not requirements.

## 3. Present tradeoffs

Explain any important consequences before building.

Examples:
- a fuzzy attention model reduces data entry but may occasionally surface something too early/late;
- recurrence needs a clear basis to avoid date drift;
- storing attention state prevents tasks from disappearing between model runs;
- one canonical backend avoids sync bugs.

## 4. Get user approval

Before the integration test, summarize:
- proposed statuses,
- field meanings,
- due-date semantics,
- recurrence behavior,
- attention behavior,
- agent autonomy.

Then proceed to `INTEGRATION_TEST.md`.
