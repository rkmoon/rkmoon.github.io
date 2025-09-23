# Abilities

List + purpose of each `GA_` asset.

| Ability | Purpose | Key Effects | Costs | Notes |
|---------|---------|-------------|-------|-------|
| GA_Sprint | Temporary speed increase | (Add speed tag / effect) | Stamina drain (periodic) | Cancel on stop input |
| GA_Jump | Standard jump action | None or impulse | None | Could gate if low stamina |
| GA_Tackle | Apply tackle state / impact | `GE_ApplyTackled` | Instant stamina cost | Stops ball holder |
| GA_Block | Defensive posture | (Future) | Periodic stamina | Could reduce incoming effects |
| GA_ThrowBall | Launch football | `GE_ApplyJustThrewBall`, remove hold | Stamina + maybe cooldown | Spawns / detaches ball |

## Data Source
Costs: `DA_AbilityCosts` (tunable table or data asset)

## Ability Guidelines
- Use tags to: gate activation, mark transient states, filter effects.
- Prefer effects for attribute changes instead of manual modifications.

## Future Additions
- Pass vs Long Throw specialization
- Interception / Catch ability
- Fake / Dodge move
