# Visual3D-MATLAB Skill Usage and Capabilities

This document explains what `visual3d-matlab-integration-workflow-expert` does, how to use it, what it can deliver, and where its boundaries are.

## 1. What this skill is for

This is a lab-grade Visual3D-MATLAB integration skill designed to make workflows:

- reproducible
- auditable
- version-aware

It enforces architecture-first planning, modular output, and explicit risk gates for versions, paths, MAT schemas, and DLL interfaces.

## 2. What it can do

### 2.1 Three official integration modes

1. `Mode A`: MAT-file exchange (recommended default)
- Visual3D export `.mat` -> MATLAB process -> save `.mat` -> Visual3D import

2. `Mode B`: Compiled MATLAB executable (EXE)
- Visual3D export MAT -> run EXE -> EXE writes MAT -> Visual3D import

3. `Mode C`: DLL plugin mode
- Visual3D calls a plugin DLL command
- Hard requirement: both `.dll` and same-name `.txt` interface descriptor

### 2.2 Workflow capabilities

- architecture design output before code
- module-by-module generation: export pipeline, MATLAB parser, signal processor, save logic, import pipeline, EXE wrapper, DLL descriptor, auto-launch workflow
- version-risk guidance (MATLAB release, compiler, plugin compatibility)
- path/runtime-risk guidance (PATH, absolute path, Windows spacing/quoting)
- MAT schema contract checks (fields, dimensions, cell layout, frame-rate metadata)
- RECALC persistence and duplicate-definition safety checks

### 2.3 Traceability capabilities

- rule-to-page mapping: `references/kb_rule_to_page_map.md`
- source and coverage map: `references/kb_source_map.md`
- extraction summary: `references/generated/kb_extraction_report.md`

## 3. How to use it

### 3.1 Trigger

Invoke explicitly in chat:

`$visual3d-matlab-integration-workflow-expert`

### 3.2 Standard operating flow

1. Choose mode first: `A` / `B` / `C`
2. Provide all 13 mandatory fields
3. Ask for architecture only first (no runnable code)
4. Confirm architecture
5. Generate one module at a time

### 3.3 The 13 mandatory fields

1. MATLAB version
2. Visual3D version
3. integration mode (`A/B/C`)
4. compiler availability
5. Visual3D and MATLAB installation paths
6. plugin path (`C` required, commonly needed for `B`)
7. MAT-file structure requirements
8. input signal names
9. signal folder
10. signal type
11. output variable names
12. whether cell arrays are expected
13. whether old MAT format (`-v6`) is required

### 3.4 Recommended prompt template

`Use $visual3d-matlab-integration-workflow-expert. Mode=A. MATLAB=R2023b. Visual3D=6.x. I will provide 13 required fields, then you return architecture only.`

## 4. Hard rules

- DLL mode must produce both `.dll` and same-name `.txt`
- Do not assume MATLAB version, compiler availability, paths, or MAT fields
- For MAT round-trip workflows, explicitly handle `save(...,'-v6')` compatibility intent
- Use explicit signal mapping (no implicit mapping)
- Preserve frame-rate, source metadata, and missing-value semantics
- Architecture first, code second, one module per response

## 5. Typical use cases

- standardizing lab batch-processing workflows
- reliable bidirectional Visual3D-MATLAB data exchange
- building audit-ready biomechanical processing pipelines
- reducing workflow drift in team environments

## 6. Non-ideal or high-risk situations

- delivering DLL/EXE pipelines without confirmed MATLAB/compiler environment
- requesting end-to-end code before MAT schema is defined
- editing RECALC as temporary scratch space without persistence-impact checks

## 7. Related files in this repository

- skill definition: `SKILL.md`
- UI metadata: `agents/openai.yaml`
- icons: `assets/`
- references: `references/`
- generated extraction outputs: `references/generated/`

## 8. Quick start

1. Start with `Mode A`
2. Provide your 13 parameters
3. confirm architecture
4. implement from `export pipeline` module first
