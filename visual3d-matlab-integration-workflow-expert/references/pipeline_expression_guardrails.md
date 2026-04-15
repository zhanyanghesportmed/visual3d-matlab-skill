# Pipeline expression guardrails

Consolidated from expression and pipeline sections in the XML KB.

## Practical constraints

- Prefer explicit parameter names and deterministic selectors.
- Use bracket/function syntax consistent with Visual3D expression grammar.
- Keep signal math operations traceable (avoid hidden intermediate remapping).

## Reproducibility rules

- Use explicit `TYPE:FOLDER:NAME` style signal targets where required.
- Keep wildcard use limited to discovery stages; lock concrete names in production modules.
- Preserve signal dimensionality assumptions when exporting to MATLAB and re-importing.
