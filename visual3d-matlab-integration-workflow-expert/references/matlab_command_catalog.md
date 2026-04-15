# MATLAB command catalog in Visual3D workflows

Cataloged from Visual3D documentation content in the provided XML KB.

## Common MATLAB bridge commands

- `Call_MFile`
- `Export_Data_To_Matlab`
- `Import_Data_From_Matlab`
- `Export_data_from_matfile`
- `Import_data_from_matfile`
- `Get_from_matlab`
- `Put_To_Matlab`
- `Eval_In_Matlab`

## Usage guardrails

- Do not select a command path before choosing integration mode.
- For `EXE` workflows, enforce explicit MAT input/output schema.
- For plugin workflows, use DLL command only with validated descriptor contract.
- Do not mix command families in one module unless user requests a hybrid architecture.
