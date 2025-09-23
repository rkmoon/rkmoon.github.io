# UI / HUD

## Widget(s)
| Widget | Purpose |
|--------|---------|
| WBP_QBHUD | Core in-game HUD (scores / stamina / possession) |

## Planned Elements
- Ball possession indicator
- Stamina bar
- Ability cooldown indicators

## Guidelines
- Keep logic in underlying data / ability system; UI observes state.
- Use gameplay tags to drive icon states where possible.

## Future
- Touch controls overlay (reuse assets under `Input/Touch/`)
