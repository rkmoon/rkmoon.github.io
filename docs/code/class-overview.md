# Class Overview

Key C++ classes and responsibilities.

| Class | Responsibility | Notes |
|-------|----------------|-------|
| PFGameplayAbilityBase | Common ability helpers | Derive all abilities |
| PFAttributeSet | Attribute definitions (e.g., Stamina) | Expand later |
| PFAbilityCostDataAsset | Data for ability costs | Possibly merge into table |
| PFCharacterMovementComponent | Custom movement logic | Sprint, tackle reactions |

## Extension Points
- Add a PlayerState subclass for replicated stats.
- Create a custom GameState for match timing.

## TODO
- Document initialization order
- Add diagram once additional systems added
