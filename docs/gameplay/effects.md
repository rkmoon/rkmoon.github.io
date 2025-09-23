# Gameplay Effects

Gameplay Effects (`GE_`) apply attribute or state changes.

## Organization
```
Effects/
  Ball/
    GE_ApplyHoldBall
    GE_ApplyJustThrewBall
    GE_RemoveHoldBall
  Character/
    GE_ApplyTackled
    Costs/
      GE_InstantStaminaCost
      GE_PeriodicSaminaCost (typo? -> GE_PeriodicStaminaCost)
```

## Common Patterns
| Type | Example | Purpose |
|------|---------|---------|
| State Apply | GE_ApplyHoldBall | Marks player as holder |
| State Remove | GE_RemoveHoldBall | Clears holding state |
| Status / Debuff | GE_ApplyTackled | Movement / ability lock |
| Cost - Instant | GE_InstantStaminaCost | One-time stamina reduction |
| Cost - Periodic | GE_PeriodicStaminaCost | Drains over time |

## Naming + Conventions
- Verb first (Apply / Remove) for stateful effects.
- Keep cost-related effects in `Costs/` subfolder.
- Fix typos early (consistency aids search & refactor).

## Stacking Rules (Fill In)
- Are tackle states mutually exclusive?
- Can multiple stamina drains stack?

## Pending
- Duration vs infinite effects doc
- Removal triggers (on death, end play, ability end)

See also: [Ability System Overview](ability-system.md) and [Abilities](abilities.md).
