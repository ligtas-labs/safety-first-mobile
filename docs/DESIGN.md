# Safety First Mobile technical design

## Implemented foundation and feature layout

The repository currently contains the Godot project settings, project icon and import metadata, and placeholder directories for scenes, scripts, assets and audio.

## Planned simulation layout

Group each instructional case as a self-contained scene with its own script and case-specific resources. The same Godot scene conventions work for an educational simulation. Apply GDQuest's separation of case content from reusable behavior where it helps cases share assessment and attempt handling. Add each directory when its first implementation lands.

```text
project.godot
scenes/
  app/                              # application entry and session navigation
  cases/
    tutorial/                       # basic inspection and emergency reporting
    work_at_height/                 # work at height and pre-work checks
    temporary_works/                # temporary works and safe sequencing
  shared/                           # reusable touch controls and UI scenes
scripts/
  assessment/                       # reviewed criteria and local result calculation
  attempts/                         # attempt lifecycle, SQLite saves and recovery
  sync/                             # authenticated upload and server acknowledgment
assets/, audio/                     # resources used by multiple scenes
```

Keep a case's scene, script and exclusive resources together. Case scenes and UI call the shared modules through their public methods. Shared assessment and persistence depend on versioned case data supplied by callers. Keep scoring, save writes and network retries out of UI handlers.

See [Godot project organization](https://docs.godotengine.org/en/stable/tutorials/best_practices/project_organization.html) and [GDQuest modular architecture](https://www.gdquest.com/library/modular_game_architecture/).

## Files and identifiers to protect

| Path or identifier | Handling |
| --- | --- |
| `project.godot`, `icon.svg`, `icon.svg.import`, `export_presets.cfg` once present | Keep paths and settings intact during folder cleanup. Change settings or export configuration only for a task that requires it. |
| `.tscn`, `.tres`, `.uid`, `.import`, `res://` references | Do not hand-edit UIDs or generated import metadata for a move. Use the Godot editor to move referenced resources with their sidecars, then check scene references and headless import. |
| `.godot/`, generated `android/` | Leave generated output out of version control. |
| `user://` saves, attempt IDs, scenario and rubric IDs and versions | Preserve across folder moves. Validate backward compatibility before making a schema change. Never commit device saves or signing credentials. |

## Planned integration

Use versioned reviewed content separate from save state. Verify a Godot-compatible Android SQLite extension before committing to its binding. Save evidence and pending state durably, retry with a stable ID and acknowledge only confirmed API results. Keep Android export presets independent of VPS deployments.

See the [PRD](PRD.md) for stable requirement IDs, the proposed cross-app workflow and unresolved contracts. Add planned folders with their first implementation.

## Verification

Move Godot resources with their metadata; verify affected references and headless import. For gameplay changes record scene/APK, device, engine, network state, save/restart and retry results. See the [README](../README.md) for current commands and the [PRD](PRD.md) for acceptance checks.
