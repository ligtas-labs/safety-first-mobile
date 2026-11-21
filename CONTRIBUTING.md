# Contributing to Safety First Mobile

## Ticket to release

1. Open the real Linear ticket and confirm ownership, affected repositories, dependencies and acceptance criteria. Use stable PRD requirement IDs when applicable.
2. Update local `development` from `origin/development` with a fast-forward and create the ticket branch from it. Use `<type>/<linear-id>-<short-ticket-slug>`. Types include `setup`, `feature`, `fix`, `refactor` and `docs`. Example shapes are `setup/lig-123-neon-postgresql` and `feature/lig-124-submit-attempt`. Substitute the real assigned ID. For local work without a ticket, keep a descriptive branch without inventing a Linear ID.
3. Commit by purpose using Conventional Commits. Verify with the [README commands](README.md) and record observed results, including failure paths.
4. Open ticket PRs into `development`. Keep the Linear ID in the branch name only. Use a descriptive PR title and body. Have a teammate review and wait for applicable CI.
5. Open the sprint release PR from `development` into `main`. Summarize delivered changes and include applicable tested image digests or Android build, migrations and rollback evidence. Use a merge commit to preserve the long-lived branch history. Tag the accepted release. Merge urgent releases from `main` back into `development`.

## Optional agent skills

List the available skills with `npx skills add MJayConstantino/skills --list`. The repository contains `grill-me`, `coding-standards`, and `verification-before-completion`. Use [AGENTS.md](AGENTS.md) for repository-specific guidance.
