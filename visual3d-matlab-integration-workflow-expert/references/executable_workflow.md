# Executable workflow

## Architecture

Visual3D export MAT -> call compiled MATLAB EXE -> EXE writes output MAT -> Visual3D import.

## Preconditions

- MATLAB Compiler available at build time.
- Entry M-file/function explicitly identified.
- Input/output MAT schema explicitly documented.
- Runtime dependencies and EXE path reproducible.

## Operational risks

- Compiler restrictions vary across MATLAB releases.
- Path quoting and spaces in Windows paths can break launches.
- Silent schema drift between EXE output and import mapping causes downstream errors.

## Verification gates

1. EXE exits with success code.
2. Output MAT exists and passes schema checks.
3. Imported signal names/types/folders match declared mapping.
4. Downstream RECALC or report template behavior remains stable.
