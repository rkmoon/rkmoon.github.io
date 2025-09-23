# Input System

Enhanced Input assets + mapping contexts.

## Assets
| Type | Asset | Purpose |
|------|-------|---------|
| Mapping Context | IMC_Default | Core gameplay bindings |
| Mapping Context | IMC_MouseLook | Mouse-look specific |
| Action | IA_Move | Movement vector |
| Action | IA_Look | Gamepad / stick look |
| Action | IA_MouseLook | Mouse delta |
| Action | IA_Sprint | Sprint toggle/hold |
| Action | IA_Jump | Jump |
| Action | IA_Block | Defensive action |
| Action | IA_Tackle | Tackle initiation |
| Action | IA_Throw | Throw football |

## Flow
1. PlayerController adds `IMC_Default` (and situational contexts).
2. Actions fire → bound functions / abilities.
3. Ability system activates abilities (e.g., Sprint).

## Guidelines
- Keep one primary context for base gameplay.
- Use additional contexts (e.g., Menu, Spectator) later for clarity.
- Avoid logic in input events; delegate to ability / character functions.
