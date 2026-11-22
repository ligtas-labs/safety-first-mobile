<div align="center">

# Safety First Mobile

[![Godot 4.7](https://img.shields.io/badge/Godot-4.7-478CBF?style=for-the-badge&logo=godotengine&logoColor=white)](https://godotengine.org/)
[![Android target](https://img.shields.io/badge/Android-target-3DDC84?style=for-the-badge&logo=android&logoColor=white)](https://developer.android.com/)
[![pnpm 10.25](https://img.shields.io/badge/pnpm-10.25-F69220?style=for-the-badge&logo=pnpm&logoColor=white)](https://pnpm.io/)

</div>

[About](#about) · [Local development](#local-development) · [Configuration](#configuration) · [Testing](#testing) · [Repository layout](#repository-layout) · [Deployment](#deployment) · [Contributing](#contributing)

## About

Safety First Mobile is the Android app for scenario-based construction safety learning. The Godot foundation contains project settings, an icon and placeholder folders. A playable case, Android export preset, local saves and API sync are planned.

| Area | Stack |
| --- | --- |
| Engine and renderer | Godot 4.7, Compatibility |
| Gameplay scripting | GDScript planned |
| Distribution | Android APK when configured |
| Import checks and Git hooks | GitHub Actions, pnpm, Husky and Commitlint |

## Local development

Install [Godot 4.7](https://godotengine.org/download/), [Node.js 24](https://nodejs.org/) and [Git](https://git-scm.com/). Install pnpm for Git hooks with `npm install --global pnpm@10.25.0`. Put the Godot executable on your PATH or substitute its full path.

```sh
git clone https://github.com/ligtas-labs/safety-first-mobile.git
cd safety-first-mobile
pnpm install --frozen-lockfile
godot --editor --path .
```

Import `project.godot` from the Godot Project Manager if using the GUI. Use F6 once a scene exists, or F5 once a main scene is configured.

## Configuration

The foundation needs no environment file or API URL. For Android export, install matching Godot export templates and configure the Android SDK and JDK in Godot. Keep signing keys and passwords outside Git. The Android device range and online API settings are pending.

## Testing

```sh
godot --headless --path . --import
```

This is the current CI import check. The foundation has no gameplay test runner or playable scene. When a case is available, verify it on the target device and record the engine version, build, device, Android version and applicable observed results. Use synthetic scenarios and follow [the test-first workflow](CONTRIBUTING.md#test-driven-development) for shared rules, saves and sync.

## Repository layout

| Path | Purpose |
| --- | --- |
| `project.godot`, `icon.svg`, `icon.svg.import` | Engine settings and icon resources |
| `scenes/`, `scripts/`, `assets/`, `audio/` | Current placeholders |
| `.github/workflows/godot.yml` | Headless import check |
| `docs/` | Product requirements and technical design |

See the [planned simulation layout](docs/DESIGN.md#planned-simulation-layout) and [Godot file protections](docs/DESIGN.md#files-and-identifiers-to-protect).

## Deployment

When an Android debug preset exists, export from the Godot editor or use `godot --headless --path . --export-debug "<preset>" "<path-to-apk>"`. Install the APK on a physical Android device and record the preset and device details. Android distribution has its own release track. Online flows will use the HTTPS API.

## Contributing

Read [CONTRIBUTING.md](CONTRIBUTING.md) for the Linear issue workflow, testing expectations and PR checklist. For agent-assisted work, use [AGENTS.md](AGENTS.md) and the [optional skills instructions](CONTRIBUTING.md#optional-agent-skills).

## Project links

[Web](https://github.com/ligtas-labs/safety-first-web) · [API](https://github.com/ligtas-labs/safety-first-api) · [Mobile](https://github.com/ligtas-labs/safety-first-mobile) · [Linear handbook](https://linear.app/ligtas-labs/document/developer-handbook-mobile-097df6bc3a0b)

[Product requirements](docs/PRD.md) · [Technical design](docs/DESIGN.md) · [Contributing](CONTRIBUTING.md) · [Agent instructions](AGENTS.md)
