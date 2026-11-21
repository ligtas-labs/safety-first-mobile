# Safety First Mobile

Use Godot 4.7 with matching export templates, Git and pnpm 10.25.0 for the commit hooks. Run `pnpm install --frozen-lockfile`, then import project.godot into the editor with `godot --editor --path .`. Run an individual scene with F6 or a configured main scene with F5. For a clean import run `godot --headless --path . --import`. Configure the Android SDK, matching export templates and a debug export preset before exporting an APK. Record the preset name, device and Android version in the PR. Demonstrate offline save, restart, reconnection and a duplicate retry against synthetic data as those features land. Keep signing keys outside Git. APKs run on phones.

# Development workflow

Take one Linear issue. Confirm the outcome, owner, affected repositories and acceptance examples. Link dependencies. For cross-repository work designate one final PR to complete the story.

| Issue title prefix | Branch prefix | Commit type |
| --- | --- | --- |
| feat, ui | feature/ | feat |
| fix | fix/ | fix |
| refactor | refactor/ | refactor |
| chore, ci, setup, test | setup/ | chore, ci, build or test |
| docs | docs/ | docs |

Use <prefix>/<lowercase-linear-id>-<short-kebab-title>. Example using the existing LIG-7 CI ticket:

```sh
git fetch origin
git switch development
git pull --ff-only origin development
git switch -c setup/lig-7-configure-ci-cd-for-dev
# Edit, inspect git diff, stage the intended files, run repository checks.
git commit -m "ci: build the API image for LIG-7"
git push -u origin HEAD
```

Open a PR targeting development. Title example: "ci(api): build the API image (LIG-7)". Put "Completes LIG-7" in the final implementing PR and "Refs LIG-7" on supporting PRs. One teammate reviews the diff and evidence. Merge after CI passes. At sprint review demo the integrated development branch. Open a release PR from development to main with ticket list, image digests, Android version, migrations and rollback record. Use a merge commit for that long-lived branch pair. Tag the accepted release. If main receives an urgent fix, merge main back into development.

In GitHub, create development from the verified main head in each repo. Protect both branches with PR review and the checks actually emitted by that repo. In Linear workspace integrations connect the three GitHub repos. In Ligtas Labs team Git automation set an opened reviewable PR to In Review and a qualifying merge targeting development to Done. If the team needs a separate release status use release tracking for the sprint. Validate with one real issue: branch links, PR appears, supporting PR leaves story open, final merge completes it, release PR lists delivered tickets. Enable only transitions available in workspace settings. Linear's suggested branch currently includes the username; use the typed branch example to preserve the team prefix.

## Coding with agents

Read AGENTS.md, the ticket, its acceptance criteria and the current code before edits. Give the agent an explicit repository, allowed scope, fixture, required checks and expected output. Ask for a short plan before changes involving scoring, sync, access or migrations. A developer checks the diff, runs the tests, records observed results, and owns the PR. Use synthetic records. Keep research recordings, names, tokens and credentials out of prompts, commits and logs.

Install Node 22.20+ and Git. Discover bundled skills with `npx skills add MJayConstantino/skills --list`. In the intended checkout install a selected skill with `npx skills add MJayConstantino/skills --skill grill-me --agent codex claude-code`. For all bundled skills substitute `--skill '*'`. Add `-g` for device-wide installation or `--copy` if Windows linking is unavailable. Start a fresh session and request the skill by name. Record the selection and review updates before adopting them.
