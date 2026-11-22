# Contributing to Safety First Mobile

Start with the [README](README.md) for setup and supported commands. Use the [PRD](docs/PRD.md) and [technical design](docs/DESIGN.md) for requirements and design decisions.

## Project Structure

```text
safety-first-mobile/
├── .github/           # GitHub automation and PR templates
│   └── workflows/     # Continuous integration workflows
│       └── godot.yml  # Validates Godot headless import
├── assets/            # Placeholder for shared visual assets
├── audio/             # Placeholder for audio resources
├── docs/              # Requirements, design, and development guides
├── scenes/            # Placeholder for Godot scenes
├── scripts/           # Placeholder for GDScript code
├── icon.svg           # Project icon
├── icon.svg.import    # Godot import settings for the icon
└── project.godot      # Godot project entry point and engine settings
```

## Ticket and branch workflow

1. Pick up the Linear issue and confirm ownership, affected repos, dependencies and acceptance criteria. Use stable PRD requirement IDs where they apply.
2. Create new ticket branches from an updated `development` using `<type>/<lowercase-linear-id>-<short-slug>`. Use `feature/`, `fix/`, `refactor/`, `setup/` or `docs/`. Continue work on an existing ticket branch when one is assigned. Use a descriptive branch name for unticketed work.
3. Stage one logical change, inspect `git diff --cached`, and use Conventional Commits. Example: `docs(contributing): explain the test-first workflow`.
4. Open ticket PRs into `development`. Use a descriptive title and body and keep the Linear ID in the branch name. For cross-repo work, identify dependencies and merge order. Request teammate review and wait for applicable CI.
5. Verify the integrated result on `development` and record evidence in Linear before closing the ticket. For a sprint release, open a `development` → `main` PR, use a merge commit, and include applicable artifact versions, migration and rollback steps. Tag the accepted release. Merge urgent changes on `main` back into `development`.

## Test-driven development

1. **Red**. Turn one acceptance criterion into a test at the public interface. Run it and confirm the expected failure. For a bug, reproduce the existing behavior first.
2. **Green**. Make the smallest implementation that passes. Run the same test again.
3. **Refactor**. Clean up with the test green, then run the relevant suite and [repository checks](README.md#testing). Repeat for the next criterion.

For assessment, save or sync behavior, start with one observable outcome and a synthetic case. Exercise the shared script's public methods when an automated harness is available. The current project has no automated gameplay runner. Record a reproducible scene or device check for engine-dependent behavior. Where applicable, include offline save, process restart, reconnect and duplicate submission, with the device and Android version. For docs, visual or device checks, record the environment, steps, expected result and observed result. Use synthetic fixtures. Record failures and any checks still pending.

## Code organization

Keep a case's scene, script and exclusive resources together under `scenes/cases/<case>/` as cases land. Keep shared touch controls in `scenes/shared/` and reusable assessment, attempt and sync logic under `scripts/` when used. Use snake_case for GDScript files, functions and variables and PascalCase for named classes and nodes.

Move referenced resources in Godot with their metadata. Run headless import and check affected scene references afterward. Preserve UIDs, `res://` references, `user://` save compatibility, stable attempt IDs and versioned case and rubric identifiers. Keep generated imports and signing keys out of Git. See [Godot file protections](docs/DESIGN.md#files-and-identifiers-to-protect).

Reference: [Godot project organization](https://docs.godotengine.org/en/stable/tutorials/best_practices/project_organization.html).

## Pull request checklist

- [ ] Summarize the observed behavior and applicable requirement IDs.
- [ ] Record checks run, observed results and any remaining verification. Include screenshots, device details or migration evidence where relevant.
- [ ] Update affected setup instructions, contracts or configuration examples.
- [ ] Keep credentials, participant data and generated files out of the diff and evidence.

## Optional agent skills

Use [AGENTS.md](AGENTS.md) for repository instructions. The team bundle is optional for local agent-assisted work. List the available skills, install a selected one in this checkout, then start a new agent session and invoke it by name.

```sh
npx skills add MJayConstantino/skills --list
npx skills add MJayConstantino/skills --skill verification-before-completion --agent codex claude-code
```

Review the skill before use. Keep participant records and secrets out of agent prompts. Review agent changes and run the relevant checks before submitting a PR.
