# Safety First Mobile

Godot 4.7 Compatibility project for the Android simulation. The foundation has an importable icon and placeholder directories. A playable scene, Android export preset and local persistence are pending.

## Local development

Install Godot 4.7, Node.js 24 and pnpm 10.25.0. Install matching Godot export templates and configure the Android SDK/JDK when device export work starts. From the project root:

```sh
pnpm install --frozen-lockfile
godot --editor --path .
godot --headless --path . --import
```

The import matches the CI command. F6 runs a scene after one exists; F5 requires a configured main scene. When the team adds an Android debug preset, export it using the editor or `godot --headless --path . --export-debug "<preset>" "<path-to-apk>"`. Install on a physical Android device and record build, model and OS version. Keep signing keys and passwords outside Git. The planned authenticated HTTPS API origin and supported device range require confirmation.

## Repository layout

```text
project.godot                     # engine settings and project icon reference
icon.svg, icon.svg.import         # asset and import metadata
scenes/, scripts/                 # current placeholders
assets/, audio/                   # current placeholders
docs/                             # PRD and design
.github/workflows/godot.yml       # headless import
```

See [the technical design](docs/DESIGN.md#planned-simulation-layout) for planned case folders and files to protect during reorganization.

## Deployment

Android builds and distribution use Godot export on a separate track. The web and API are Docker services on the Ubuntu VPS behind Caddy. Mobile uses the HTTPS API for planned online flows.

[Product requirements](docs/PRD.md) · [Technical design](docs/DESIGN.md) · [Contributing](CONTRIBUTING.md) · [Agent instructions](AGENTS.md)
