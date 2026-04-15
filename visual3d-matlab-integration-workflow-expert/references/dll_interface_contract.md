# DLL interface contract

## Required artifacts

For DLL mode, generate both:

- `<name>.dll`
- `<name>.txt` descriptor

Base name must match exactly.

## Descriptor expectations

- First line is entry function name.
- Each argument is declared explicitly (input/output direction and type).
- Signal arguments use explicit `TYPE:FOLDER:NAME` style mapping when applicable.

## Compatibility cautions

- MATLAB release and compiler versions are tightly coupled.
- Cross-release compatibility cannot be assumed.
- Loader behavior depends on plugin directory and PATH resolution.

## Deployment checks

1. DLL and TXT are co-located in Visual3D plugin directory.
2. Entry function name matches compiled symbol and descriptor.
3. Visual3D command signature matches descriptor parameter order.
