---
title: Attributes
description: Core gameplay attributes defined in PFAttributeSet and their current usage status.
---

# Attributes

Core numerical state values backed by the Unreal Gameplay Ability System (GAS) via `PFAttributeSet`. These replicate to clients (each has an `OnRep_` handler) and are modified by Gameplay Effects (`GE_*`) or read by Abilities (`GA_*`).

## What Are Attributes?
Attributes in GAS are normalized data points (health, stamina, movement modifiers, etc.) wrapped in `FGameplayAttributeData`. They:
- Replicate efficiently (server authoritative)
- Can be modified by additive, multiplicative, or override Gameplay Effects
- Trigger `OnAttributeChange` delegates for responsive UI / logic

### Design Guidelines
- Keep base movement values separate from temporary multipliers (e.g., `Speed` vs `SprintSpeedMultiplier`).
- Avoid adding an attribute until a system needs runtime tuning or effect-driven modification.
- Use Gameplay Effects for all runtime changes instead of directly setting raw values except during initialization.
- The Default values can be changed in `AbilitySystem/Effects/Character/GE_InitValues`
    - This is set with an initial gameplay effect on the Character

## Attribute Table
"Used" reflects current implementation in gameplay logic (update as systems come online).

| Attribute | Category | Default | Used | Description | Primary Usage / Planned Effects |
|-----------|----------|---------|:----:|-------------|----------------------------------|
| Stamina | Vital | 100.0 | Yes | Current stamina resource | Drained by Sprint / Tackle / Throw cost effects |
| MaxStamina | Vital | 100.0 | Yes | Cap for Stamina | Scaling reference for regen / UI percentage |
| Speed | Vital | 600.0 | Yes | Base ground movement speed (cm/s) | Modified by sprint / tackle / hold-ball logic |
| SprintSpeedMultiplier | Movement | 1.4 | Yes | Multiplies Speed while sprinting | Applied during `GA_Sprint` active state |
| DashSpeedMultiplier | Movement | 1.8 | No | Burst / dash acceleration multiplier | Reserved for future dash ability |
| ChargeThrowSpeedMultiplier | QB | 1.0 | No | Scales throw charge rate / animation | Future charged throw mechanic |
| ThrowPowerMax | QB | 2500.0 | Yes | Maximum initial projectile velocity | Determines football launch speed cap |
| JumpHeight | Vital | 500.0 | Yes | Jump impulse scalar | Read by jump ability / movement component |
| FumbleChance | Vital | 1.0 | No | Base probability modifier for fumble events | For future tackle vs possession resolution |
| ThrowAccuracy | QB | 100.0 | No | Accuracy rating (spread / deviation control) | Future pass dispersion + difficulty tuning |

### Pending / Future Attributes
Consider adding later only when needed:
- `CatchReliability`
- `RecoverySpeed` (stamina regen rate)
- `BallHandling`

## Modification Flow Example (Sprint)
1. Player activates `GA_Sprint`.
2. Ability applies a periodic stamina drain Gameplay Effect (e.g., `GE_PeriodicStaminaCost`).
3. Sprint tag active → movement system multiplies base `Speed * SprintSpeedMultiplier`.
4. On stamina low threshold: ability auto-ends or speed reduces.

## Adding a New Attribute (Checklist)
1. Declare in `PFAttributeSet` (default value) + `ATTRIBUTE_ACCESSORS` macro.
2. Add replication notifier `OnRep_NewAttribute`.
3. Update UI binding / listeners (e.g., stamina bar, debug panel).
4. Create Gameplay Effects to modify it (avoid manual writes elsewhere).
5. Add to this table with initial Used = No.

## Cross References
- Abilities using attributes: [Abilities](abilities.md)
- Effects that modify attributes: [Gameplay Effects](effects.md)
- Tags that gate attribute usage (e.g., stamina costs): [Gameplay Tags](gameplay-tags.md)

---
Last updated: 2025-09-23
