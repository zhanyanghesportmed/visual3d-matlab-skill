# MATLAB launch patterns

Based on XML KB sections describing MATLAB-generated pipelines and Visual3D launch from MATLAB.

## Patterns

1. MATLAB writes `.v3s` script text.
2. MATLAB launches Visual3D with `/s <pipeline.v3s>`.
3. Visual3D executes pipeline and optionally exits via `Exit_Workspace`.

## Risks

- PATH dependency if `Visual3D.exe` is not discoverable.
- Windows path quoting errors with spaces.
- Silent failures if pipeline path is wrong or inaccessible.

## Required checks

- Use full executable path when possible.
- Validate pipeline file exists before launch.
- Capture and inspect launch return code/log where available.
