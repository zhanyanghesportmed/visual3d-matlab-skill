# KB Rule-to-Page Mapping

- Source: `D:/Research work/Code/Biomechanics/visual3d_kb.xml`
- Purpose: hard mapping from skill rules to concrete KB page ids

| Rule | Matched page ids (up to 12) |
|---|---|
| Mode selection: MAT vs EXE vs DLL | `visual3d:documentation:cmo_viewer:free_cmo_viewer` |
| DLL mode must include .dll and same-name .txt descriptor | `visual3d:documentation:cmo_viewer:free_cmo_viewer`<br>`visual3d:getting_started:visual3d_release_notes` |
| DLL interface must define entry function and parameters | `visual3d:documentation:cmo_viewer:free_cmo_viewer` |
| MAT round-trip via export/import MAT-file | `visual3d:documentation:cmo_viewer:free_cmo_viewer` |
| MATLAB load/field parsing expectations | `visual3d:documentation:cmo_viewer:free_cmo_viewer` |
| Visual3D launch from MATLAB with /s pipeline | `visual3d:documentation:cmo_viewer:free_cmo_viewer`<br>`visual3d:documentation:pipeline:pipeline_overview` |
| PATH and absolute-path launch risk | `visual3d:documentation:cmo_viewer:free_cmo_viewer` |
| Recalc active files and Select_Active_File risk | `visual3d:documentation:pipeline:general_information:recalc_pipeline`<br>`visual3d:documentation:definitions:active_files` |
| Recalc persistence and duplicate-definition risk | `visual3d:documentation:pipeline:general_information:recalc_pipeline` |
| Pipeline expression/syntax guardrails | `visual3d:documentation:pipeline:expressions:expressions_overview`<br>`visual3d:documentation:pipeline:pipeline_overview` |
| Version compatibility gate (R12/R13/R14/R15) | `visual3d:documentation:cmo_viewer:free_cmo_viewer` |
| DLL runtime library resolution risk | `visual3d:documentation:cmo_viewer:free_cmo_viewer` |

## Notes

- Match method is regex over page id + stripped page content from the XML.
- Use `references/generated/` artifacts for broad-page verification.
