# GTD Agent

A setup guide for building an agent-operated GTD system around your own workflow.

This repo does **not** give you a prebuilt Notion database or prescribe one GTD setup. Instead, it gives your agent a safe process for:

1. interviewing you about how you use GTD,
2. designing a task system around that,
3. testing its MCP/backend access with disposable data,
4. building the real system only after the test passes,
5. verifying that the result can be recovered and operated without relying on old chat history.

## Reference setup

The setup used to validate this guide is:

**Human ↔ ChatGPT ↔ Notion MCP ↔ Notion**

ChatGPT + Notion MCP is the recommended reference path because it has been tested end-to-end for read/write/query/attachment workflows.

You do not have to use either. Your agent should first determine what it can actually access and modify.

## Start here

For humans:
- Read this file.
- Connect your preferred agent to your preferred task backend.
- Ask your agent to read `AGENTS.md` and begin setup.

For agents:
- Start with `AGENTS.md`.
- Do not build the production system until the disposable integration test passes.

## What this repo is not

- a GTD tutorial
- a Notion template
- a productivity app
- a replacement for your preferred GTD method

If you want a concise GTD refresher, see Erlend Hamberg’s guide:
https://hamberg.no/gtd/

## Core design idea

The backend stores task state.

The agent becomes both:
- the interface for capture and task updates,
- the thing that decides when tasks deserve the user’s attention.

The agent should reduce database maintenance, not take over the user’s commitments.

## Safety principle

> The agent may manage attention mechanics. The user owns commitments.

The setup process should make that boundary explicit.

## Files

- `AGENTS.md` — agent entry point
- `setup/SETUP.md` — interview and design workflow
- `setup/INTEGRATION_TEST.md` — disposable capability test
- `setup/PRODUCTION_BUILD.md` — production build checklist
- `setup/RECOVERY_TEST.md` — cold-start/recovery validation
- `principles/SAFETY.md` — autonomy and failure rules
- `tests/scenarios.yaml` — adversarial acceptance tests

## Quick start

Tell your agent:

> Read AGENTS.md in this repo and help me set up an agent-operated GTD system. Interview me first. Do not create the production system until the integration test passes.

That is intentionally the shortest supported path.
