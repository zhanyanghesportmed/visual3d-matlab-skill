# Compatibility matrix notes

Grounded in legacy compatibility statements from XML KB.

## Historical constraints noted

- MATLAB release-specific integration differences exist and are non-trivial.
- DLL and compiler architecture assumptions vary by release.
- Some compiler/release combinations are explicitly incompatible.

## Current skill policy derived

- Never assume release/compiler compatibility.
- Collect MATLAB release and compiler details before generating DLL/EXE modules.
- Treat cross-version portability as unsupported unless user confirms tested pairing.
