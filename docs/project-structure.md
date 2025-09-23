# Project Structure

Overview of major runtime and content folders mapped to in-engine assets.

## Content Folders
```
AbilitySystem/
  Abilities/ (GA_*)
  Effects/ (GE_*)
  Attributes/
  Tags/ (DT_GameplayTags)
Actors/
  Football/ (BP_Football, SM_Football)
Art/
Blueprints/
  FunctionLibraries/ (BPL_*)
  Interfaces/ (BPI_*)
Game/
  Character/ (BP_FootballCharacter, BP_FootballPlayerController)
  GameModes/ (BP_FootballGameModeBase)
Input/
  Actions/ (IA_*)
Maps/ (Prototype_Football_Field.umap)
Materials/ (M_Football)
ThirdPerson/ (Lvl_Lobby, Lvl_ThirdPerson)
UI/ (WBP_QBHUD)
```

## Source Layout
```
Source/Project_Football/
  Public/
    AbilitySystem/
    Character/
  Private/
    AbilitySystem/
    Character/
```

## Naming Conventions
| Type | Prefix | Example |
|------|--------|---------|
| Blueprint Actor | BP_ | BP_Football |
| Gameplay Ability | GA_ | GA_ThrowBall |
| Gameplay Effect | GE_ | GE_ApplyHoldBall |
| Data Asset | DA_ | DA_AbilityCosts |
| Attribute Set | (Class) | PFAttributeSet |
| Widget Blueprint | WBP_ | WBP_QBHUD |
| Interface | BPI_ | BPI_Player |
| Function Library | BPL_ | BPL_GameplayEffectFunctions |
| Material | M_ | M_Football |
| Static Mesh | SM_ | SM_Football |
| Texture | T_ | T_Crosshair07 |

## Gameplay Ability System (GAS) Touchpoints
- Abilities: `GA_*`
- Effects: `GE_*` (grouped by domain: Ball, Character, Costs)
- Tags: `DT_GameplayTags`
- Attribute Set: `PFAttributeSet`
- Cost Data: `DA_AbilityCosts`

## Maps
- Prototype / Core Field: `Prototype_Football_Field`
- Third-person sandbox: `Lvl_ThirdPerson`
- Lobby / staging: `Lvl_Lobby`

## UI
- HUD: `WBP_QBHUD`
