# Disposable Integration Test

This test is mandatory before production setup.

Use fictional data only.

## Purpose

Verify that the chosen agent + backend + MCP/tool connection can actually support the proposed GTD workflow.

Do not infer capability from documentation alone.

## Test sequence

Create a disposable test store, such as `GTD Integration Test`.

Then verify, in order:

1. **Create structure**
   - create the minimum proposed task schema.

2. **Create task**
   - create a fictional task with a due date.

3. **Read**
   - fetch the task back and confirm all important fields.

4. **Update**
   - change status and due date.
   - fetch again and verify persistence.

5. **Query**
   - query incomplete tasks.
   - query by status.
   - query upcoming due dates.
   - sort by due date.

6. **Attention state**
   - persist whatever internal state is needed to keep surfaced tasks sticky.
   - verify it survives a fresh read.

7. **Attachments**
   - create or upload a disposable file.
   - associate it with the test task.
   - fetch the task and retrieve/read the attachment if the backend supports it.

8. **Views / fallback UI**
   - if relevant, verify the backend offers a usable manual fallback view.

9. **Scheduled execution**
   - if the chosen agent supports scheduling, run a one-time scheduled read.
   - verify that the scheduled run can access current backend state.
   - do not assume interactive access implies scheduled access.

10. **Direct backend edit**
   - change one test value directly in the backend UI.
   - query again from the agent and confirm it sees the change.

## Pass criteria

PASS only if every capability required by the user’s agreed design works.

A partial pass is not a pass.

If a nonessential feature fails:
- revise the design,
- explain the compromise,
- rerun the test.

If a core feature fails:
- stop.
- do not create the production system.

## Cleanup

The disposable test store may be deleted or archived after validation.

Do not let the test store remain ambiguous with the production store.
