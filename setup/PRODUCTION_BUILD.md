# Production Build

Run only after:
- user design approval,
- integration test PASS.

## 1. Create or adapt exactly one canonical task store

If an existing production backend already exists, prefer adapting it over creating a duplicate.

Name the canonical store clearly.

## 2. Create only approved fields

Do not smuggle in fields from an example implementation.

## 3. Add a manual fallback view

The user should have a simple way to inspect tasks directly in the backend if needed.

Useful views may include:
- active by due date,
- attention now,
- calendar,
- someday/maybe.

Only create views that fit the user’s system.

## 4. Seed data

If migrating from another system:
- preserve the original until verification,
- migrate in a reversible way,
- preserve notes and attachments where possible,
- record failures explicitly,
- do not silently drop fields or files.

## 5. Dry-run attention logic

Before persisting attention/activation decisions:
- show what the agent would surface,
- explain non-obvious decisions,
- get user approval.

Then persist only the approved behavior.

## 6. Configure reviews

If scheduling is supported:
- configure the user-approved cadence,
- confirm the scheduled run can access the backend,
- confirm notifications actually reach the user.

Do not assume a scheduled run has the same permissions as an interactive session.

## 7. Preserve rollback

Keep the previous system intact until the new system has survived a reliability period.

Avoid bidirectional sync unless there is a compelling reason.

## 8. Record the private configuration

The user’s private environment should contain enough information to recover the system later:
- canonical backend name,
- operating rules,
- recurrence rules,
- autonomy boundaries,
- scheduling behavior.

Do not put private identifiers into this public repo.
