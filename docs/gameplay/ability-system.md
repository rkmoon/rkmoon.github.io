# Ability System Overview

High-level description of how the Unreal Gameplay Ability System (GAS) is used.

## Goals
- Modular player actions (sprint, tackle, throw)
- Consistent cost + cooldown handling
- Clear separation between abilities, effects, and attributes

## Components
| Concept | Implementation | Notes |
|---------|----------------|-------|
| Attribute Set | `PFAttributeSet` | Holds stamina, etc. |
| Ability Base | `PFGameplayAbilityBase` | Common logic / helper functions |
| Cost Data | `DA_AbilityCosts` | Tunable cost values |
| Abilities | `GA_*.uasset` | One Blueprint per action |
| Gameplay Effects | `GE_*` | Apply attribute changes, states |
| Tags | `DT_GameplayTags` | State + gating tags |

## Flow (Typical Ability)
1. Input triggers (e.g., `IA_Jump`)
2. Ability system component grants / activates `GA_Jump`
3. Stamina costs determined by DA_AbilityCosts
4. Gameplay effect(s) applied (movement speed increase)
5. Ongoing / periodic costs if applicable
6. Ability ends -> cleanup / tag removal

## Tags
Examples:
```
Player.Attribute.Stamina
Player.Ability.ThrowBall
Data.Stamina
```

## Pending Documentation
- Activation prediction (if added)
- Cooldown stacking rules

See also: [Abilities](abilities.md), [Gameplay Effects](effects.md), [Gameplay Tags](gameplay-tags.md).
