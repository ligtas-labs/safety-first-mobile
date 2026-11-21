# Safety First Mobile agent instructions

Read [the PRD](docs/PRD.md), [the design](docs/DESIGN.md), [the contribution workflow](CONTRIBUTING.md), and the linked Linear ticket when one exists. Use the commands in the [README](README.md).

Follow the [Godot file protections](docs/DESIGN.md#files-and-identifiers-to-protect). Verify affected references and headless import after moving resources. For gameplay changes record scene/APK, device, engine, network state, save/restart and retry results.

Use synthetic fixtures. Include requirement IDs, applicable verification results and unexecuted checks in the PR. Keep credentials and participant data out of code, logs and review artifacts. Pending safety content, scoring, research and integration decisions require the appropriate owner before implementation.
