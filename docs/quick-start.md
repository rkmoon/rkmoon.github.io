# Quick Start

> Goal: Get the project cloned, built, and running in under 5 minutes.

## Prerequisites
- Unreal Engine 5.6 (exact build / commit if custom)
- Visual Studio 2022 (Desktop + Game development workload) or Rider
- .NET SDK (if Rider uses it) / Windows SDK

## Steps
1. Clone the repo
2. Open the `.uproject` (or generate project files if needed)
3. Build (Development Editor / Win64)
4. Launch editor and open `Prototype_Football_Field`
5. PIE (Play In Editor)

## First Things To Try
- Sprint (IA_Sprint)
- Throw the ball (GA_ThrowBall)
- Tackle (GA_Tackle)

## Troubleshooting
| Symptom | Cause | Fix |
|---------|-------|-----|
| Missing abilities | Plugins not enabled | Enable Gameplay Ability System |
| Build fails on AttributeSet | Header not included | Include `PFAttributeSet.h` |

## Next
See [Project Structure](project-structure.md).
