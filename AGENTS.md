# Agent Instructions

You are helping a user establish or operate an agent-managed GTD system.

Do not assume their workflow should match any example implementation.

## First: discover before creating

Before creating a production task system:

1. Determine whether the user already has an existing GTD system.
2. Identify the canonical backend if one exists.
3. Never create a second production database merely because you cannot immediately locate the existing one.
4. Treat the backend as authoritative task state, not chat history.

If no production system exists, continue with setup.

## Setup sequence

Follow this order:

1. Read `setup/SETUP.md`.
2. Interview the user about their actual GTD workflow.
3. Propose a minimal operating model.
4. Identify the available agent/backend/MCP capabilities.
5. Run `setup/INTEGRATION_TEST.md` using disposable data.
6. Report PASS / FAIL and concrete limitations.
7. Only if the test passes and the user approves the design, follow `setup/PRODUCTION_BUILD.md`.
8. Run `setup/RECOVERY_TEST.md`.
9. Run the acceptance scenarios in `tests/scenarios.yaml`.

Do not skip the disposable test.

## Be agent-agnostic

Do not assume:
- ChatGPT,
- Notion,
- a specific status model,
- a specific review cadence,
- a specific recurrence model,
- one conversation versus multiple conversations.

ChatGPT + Notion MCP is a tested reference implementation, not a requirement.

## Interview before designing

Ask one question at a time.

Prefer concrete behavioral questions over abstract productivity questions.

Examples:
- What does a due date mean to you?
- Which GTD states do you actually use?
- How do Waiting For items return to your attention?
- How do recurring tasks work?
- Do you distinguish future committed work from Someday/Maybe?
- How often do you review the system?
- What should the agent be allowed to do automatically?
- How should attachments and notes work?
- What happens if you miss a review?

Do not force GTD orthodoxy. Explain tradeoffs when useful, but design around the user’s actual practice.

## Backend rule

The task backend is the source of truth.

If the backend is unavailable:
- fail visibly,
- do not reconstruct an operational task list from memory,
- do not pretend a partial result is complete.

## Ambiguity rule

If a natural-language instruction could mutate more than one task, clarify before writing.

Use stable backend identifiers internally whenever possible.

## Privacy

Do not copy private task data into this public repository.

Do not store:
- credentials,
- workspace IDs,
- database IDs,
- personal URLs,
- emails,
- task content,
- attachment references.

Generated user-specific configuration belongs in the user’s private environment, not here.
