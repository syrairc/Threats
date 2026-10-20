# Threats

EmberHUD plugin that draws what is about to hurt you in Torchlight: Infinite - cast telegraphs on rare and boss monsters, lines for their projectiles, ground hazards (pools, falling rocks, boss orbs, expanding rings) and an optional MOVE alert when you stand in danger. F9 toggles it.

## Files

- `Main.cs` - render loop, ties the pieces together
- `Telegraph.cs` - cast windup areas with a countdown
- `ProjectileLine.cs` - projectile paths, orbiting projectiles as a ring around their owner
- `GroundHazards.cs` - areas, damage circles and ring bands
- `Groups.cs` - merges overlapping shapes into one draw group
- `Settings.cs`, `SettingsUI.cs`, `defaults.json` - settings POCO, its page, shipped defaults
- `Tests/` - plugin self-tests, run by `Ember.exe --check`

## Use

Copy the folder into the EmberHUD `Plugins\Threats` folder. The host compiles it against `EmberHUD.Api.dll`, so it only builds inside an EmberHUD checkout or install. The game readers it relies on (casts, projectiles, ground hazards) live in the host, not here.

## Where the source of truth is

This repo is a history-preserving export of `src\Plugins\Threats` from the EmberHUD source repo, made 2026-10-20. The copy in `src` still builds and ships with EmberHUD, so changes land there first and get carried over here. Local only, no remote.
