# Character

Primary playable character & related components.

## Key Blueprints
| Asset | Purpose |
|-------|---------|
| BP_FootballCharacter | Player pawn / ability system owner |
| BP_FootballPlayerController | Input routing / possession |
| BP_FootballGameModeBase | Match / rules orchestration |
| BP_Football (Actor) | Ball actor (possession, physics) |

## C++ Components
| Class | File | Notes |
|-------|------|-------|
| PFCharacterMovementComponent | `Character/PFCharacterMovementComponent.*` | Custom movement tweaks |
| PFGameplayAbilityBase | `AbilitySystem/PFGameplayAbilityBase.*` | Shared ability helpers |
| PFAttributeSet | `AbilitySystem/PFAttributeSet.*` | Stamina + future attributes |


## Ability System Integration
- Character owns ASC.
- Grant abilities on spawn.

## Future
- Replicated cosmetic state (team colors)
- Camera behavior variations (quarterback vs receiver)
