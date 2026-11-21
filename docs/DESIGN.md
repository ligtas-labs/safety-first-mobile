# Safety First Mobile technical design

## Implemented foundation and feature layout

Keep `project.godot` and current resource metadata at the root. When a playable slice lands, group each case scene and its own GDScript under `scenes/<case>/`; put reusable touch/UI scenes under `scenes/shared/` and cross-case services under `scripts/` by responsibility. Keep art and audio in their existing roots. Preserve `res://` paths, UIDs and `.import`/`.uid` metadata when moving resources. Keep saved attempt IDs and versions readable across upgrades and verify migrations before changing an existing save format.

## Planned integration

Use versioned reviewed content separate from save state. Verify a Godot-compatible Android SQLite extension before committing to its binding. Save evidence and pending state durably, retry with a stable ID and acknowledge only confirmed API results. Keep Android export presets independent of VPS deployments.

See the [PRD](PRD.md) for stable requirement IDs, the proposed cross-app workflow and unresolved contracts. Add planned folders with their first implementation.

## Verification

Move Godot resources with their metadata; verify affected references and headless import. For gameplay changes record scene/APK, device, engine, network state, save/restart and retry results. See the [README](../README.md) for current commands and the [PRD](PRD.md) for acceptance checks.
