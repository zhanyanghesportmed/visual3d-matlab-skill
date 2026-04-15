# MATLAB integration modes

Visual3D supports three practical MATLAB integration patterns.

## Mode A: MAT-file exchange (default)

Flow: Visual3D export MAT -> MATLAB processing -> MATLAB save MAT -> Visual3D import.

Why default:

- Most version-independent path.
- Easiest to validate and reproduce.
- Lowest dependency on compiler/runtime internals.

## Mode B: Compiled executable integration

Flow: Visual3D exports MAT and calls EXE -> EXE processes and writes MAT -> Visual3D imports.

Risks and checks:

- MATLAB Compiler availability required.
- Entry function and MAT I/O contract must be explicit.
- Runtime path and executable dependency chain must be reproducible.

## Mode C: DLL plugin integration

Flow: Visual3D plugin command invokes DLL using descriptor-defined interface.

Hard rule:

- Always provide BOTH DLL and matching TXT descriptor with the same base name.

Risks and checks:

- MATLAB release/compiler coupling can break compatibility.
- Plugin path and loader dependencies must be explicit.
- Interface signature must match Visual3D expectations exactly.
