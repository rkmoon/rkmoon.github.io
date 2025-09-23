# Gameplay Tags

Central tag table: `DT_GameplayTags`.

## Example Tag Categories (Propose & Refine)
| Category | Example | Purpose |
|----------|---------|---------|
| State | Player.State.HoldingBall | Marks current ball holder |
| State | Player.State.Tackled | Restrict movement / abilities |
| Ability | Player.Ability.Block | Gate activation / queries |
| Ability | Player.Ability.Throw | For UI prompts / filtering |
| Cost | Data.Stamina | Modify cost scaling |

## Guidelines
- Use dot hierarchy: `Domain.SubDomain.Detail`.
- Avoid mixing concerns (no `StateOrAbility.Mixed`).
- Add comments in the tag data asset for usage.

## Planned Additions
- State.Aiming
- Ability.Catch
