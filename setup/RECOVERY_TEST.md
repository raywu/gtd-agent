# Recovery Test

The system should survive loss of conversational context.

## Test

Use a fresh session or fresh agent context with:
- access to this repo,
- authorized access to the production backend,
- no prior conversation history.

Ask it to operate or inspect the GTD system.

## Expected behavior

The agent should:
1. discover that an existing GTD system may already exist,
2. locate the canonical backend,
3. avoid creating a duplicate,
4. read the user-specific operating rules from the appropriate private configuration,
5. correctly identify task state from the backend.

## Failure

Setup is incomplete if the new session:
- cannot locate the system,
- invents a second production database,
- relies on remembered chat state,
- cannot distinguish test and production stores.

The recovery path does not need to be automatic for every agent. It must be documented and workable.
