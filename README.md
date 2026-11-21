# Safety First Mobile

Use Godot 4.7 with matching export templates, Git and pnpm 10.25.0 for the commit hooks. Run `pnpm install --frozen-lockfile`, then import project.godot into the editor with `godot --editor --path .`. Run an individual scene with F6 or a configured main scene with F5. For a clean import run `godot --headless --path . --import`. Configure the Android SDK, matching export templates and a debug export preset before exporting an APK. Record the preset name, device and Android version in the PR. Demonstrate offline save, restart, reconnection and a duplicate retry against synthetic data as those features land. Keep signing keys outside Git. APKs run on phones.


## Product scope

Give Civil Engineering students repeatable offline construction safety practice on Android.

[Requirements](docs/PRD.md) · [Design](docs/DESIGN.md) · [Contributing](CONTRIBUTING.md) · [Agent instructions](AGENTS.md)
