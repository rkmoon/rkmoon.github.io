# Standards (Light)

Minimal initial standards to keep project consistent.

## C++
- Use `PF` prefix for new engine-facing classes.
- Keep includes minimal; forward declare where possible.
- One class per file.

## Blueprints
- Prefix: `BP_`, `GA_`, `GE_`, `DA_`, `BPI_`, `BPL_`, `WBP_`.
- Keep event graph small; move logic to functions.
- Use categories for exposed variables.

## Folders
- Use subfolders inside AbilitySystem for clarity.

## Gameplay Tags
- Add only if used or scheduled soon.
- Remove dead tags quickly.
