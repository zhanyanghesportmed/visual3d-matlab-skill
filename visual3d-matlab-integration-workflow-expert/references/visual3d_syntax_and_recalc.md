# Visual3D syntax and RECALC notes

## RECALC behavior

- RECALC acts on active files; default is effectively all files unless filtered.
- Avoid casual edits to RECALC pipeline because changes persist into report templates and can re-create removed signals.
- Deleting a signal from the data tree alone is insufficient if its definition still exists in RECALC.
- RECALC can contain duplicate definitions if users append commands repeatedly; detect and de-duplicate.

## Safe workflow for RECALC edits

1. Save baseline workspace/template before RECALC edits.
2. Edit RECALC definitions intentionally.
3. Re-run RECALC and verify expected signal regeneration.
4. Confirm no stale or duplicated model-based definitions remain.

## Pipeline syntax guardrails

- Use explicit command blocks and explicit parameter naming.
- Use internal segment abbreviations when required by command conventions.
- Keep file and signal selectors deterministic; avoid ambiguous wildcard mapping for final production scripts.
