# RECALC safety playbook

Derived from RECALC pipeline guidance in the XML KB.

## Critical behavior

- RECALC changes can persist in report-template behavior.
- Removing a signal from tree alone is insufficient if RECALC definition remains.
- Duplicate entries can appear when commands are appended repeatedly.
- Active file scope can be unintentionally modified via `Select_Active_File`.

## Safety protocol

1. Save baseline workspace/template.
2. Snapshot RECALC script before edits.
3. Apply minimal RECALC changes.
4. Re-run RECALC and compare regenerated signals.
5. Verify no duplicate or stale model-based definitions.

## Integration implication

Any MATLAB round-trip that feeds model-based/derived signals must include RECALC impact verification before finalizing the workflow.
