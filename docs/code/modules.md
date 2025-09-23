# Code Modules

Single primary module currently: `Project_Football`.

## Build File
`Project_Football.Build.cs` - Add dependencies here (GameplayAbilities, EnhancedInput, etc.).

## Potential Future Modules
| Module | Purpose |
|--------|---------|
| PFGameplay | Core gameplay layer separation |
| PFUI | UI specific logic |
| PFNetworking | Session / replication logic |

## Guidelines
- Keep module count low until clear boundaries emerge.
- Avoid circular dependencies (enforce direction).
