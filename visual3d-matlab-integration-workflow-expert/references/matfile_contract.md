# MAT-file contract for Visual3D round-trip

## Export/import contract

- Define explicit variable mapping between Visual3D signals and MATLAB variables.
- Preserve frame-rate metadata.
- Preserve source filename metadata when provided.
- Preserve cell-array structure when present; do not flatten by default.
- Preserve missing-point sentinel values used by source data.

## Save format constraints

- Prefer uncompressed MAT output for robust interoperability.
- Use old MAT format `-v6` when targeting maximal Visual3D compatibility.
- Emit warning if script saves output MAT without `-v6` for Visual3D import workflows.

## Validation checklist

1. All required variables exist.
2. Data dimensions match expected channel/component layout.
3. Cell/non-cell expectation matches declared contract.
4. Frame count consistency is preserved or intentionally transformed and documented.
