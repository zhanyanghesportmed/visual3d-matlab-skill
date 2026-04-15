# KB source map (visual3d_kb.xml)

Skill-local KB:
- `references/visual3d_kb.xml`

Original workspace source:
- `D:/Research work/Code/Biomechanics/visual3d_kb.xml`

Coverage summary used for this skill:
- Total page ids detected: 1061
- Pipeline/RECALC-related ids detected: 564
- MATLAB-related content matches detected: 101
- RECALC-related content matches detected: 404

## Skill rule -> KB topic mapping

1. Mode selection (`MAT`, `EXE`, `DLL`)
- KB sections mentioning Visual3D-MATLAB communication in three modes
- KB sections on integrating MATLAB executables
- KB sections on integrating MATLAB DLLs

2. DLL hard rule (`.dll` + same-name `.txt`)
- KB examples describing plugin DLL + text interface descriptor pair
- KB examples showing descriptor function signature and signal argument mapping

3. MAT contract and `-v6` safety
- KB MAT export/import workflow sections
- KB MATLAB load/fieldnames/getfield parsing sections
- KB workflow notes on preserving schema compatibility in round-trip data

4. RECALC safety and persistence
- KB RECALC pipeline warnings about persistence and duplicate definitions
- KB notes on active files behavior and Select_Active_File implications

5. Path and launch risks
- KB notes on Visual3D path resolution from MATLAB `dos()`
- KB notes on PATH dependency and full executable path alternatives

6. Version compatibility risk gate
- KB notes discussing MATLAB release-specific integration constraints (R12/R13/R14/R15 era guidance)

## Generated full-extraction artifacts

- `references/generated/kb_extraction_report.md`
- `references/generated/kb_index_matlab.md`
- `references/generated/kb_index_matfile.md`
- `references/generated/kb_index_dll.md`
- `references/generated/kb_index_exe.md`
- `references/generated/kb_index_recalc.md`
- `references/generated/kb_index_pipeline.md`
- `references/generated/kb_snippets_matlab.md`
- `references/generated/kb_snippets_matfile.md`
- `references/generated/kb_snippets_dll.md`
- `references/generated/kb_snippets_exe.md`
- `references/generated/kb_snippets_recalc.md`
- `references/generated/kb_snippets_pipeline.md`
- `references/generated/kb_pages_matlab_full.md`
- `references/generated/kb_pages_recalc_full.md`
