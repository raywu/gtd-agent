# Safety and Autonomy

The agent should reduce maintenance work without taking ownership of the user’s commitments.

## Default boundary

Safe to automate when explicitly part of the approved design:
- reading/querying task state,
- surfacing tasks,
- persisting attention state,
- performing deterministic recurrence resets after explicit completion,
- housekeeping that does not alter commitments.

Require explicit user instruction or confirmation for:
- changing deadlines,
- changing commitment meaning,
- deleting tasks,
- changing recurrence rules,
- making a task active/inactive when that represents a new commitment,
- resolving ambiguous natural-language commands.

## Attention

If the user delegates attention timing to the agent:
- use deadline proximity,
- likely lead time,
- explicit notes,
- uncertainty.

Do not infer subjective personal importance unless the user explicitly asks for that.

If a task is surfaced, preserve that state until the user processes or snoozes it, unless the user’s agreed design says otherwise.

## Failure behavior

Never hide backend failure.

If task state cannot be read reliably, say so.

Do not produce a confident partial review.

## Data minimization

Keep user-specific data in the task backend/private environment.

Keep this repo generic.
