---
name: dependency-update-with-lockfile
description: Workflow command scaffold for dependency-update-with-lockfile in docs2db-api.
allowed_tools: ["Bash", "Read", "Write", "Grep", "Glob"]
---

# /dependency-update-with-lockfile

Use this workflow when working on **dependency-update-with-lockfile** in `docs2db-api`.

## Goal

Updates project dependencies and lockfile, often triggered by automated tools like Renovate.

## Common Files

- `pyproject.toml`
- `uv.lock`
- `.github/workflows/ci.yml`

## Suggested Sequence

1. Understand the current state and failure mode before editing.
2. Make the smallest coherent change that satisfies the workflow goal.
3. Run the most relevant verification for touched files.
4. Summarize what changed and what still needs review.

## Typical Commit Signals

- Update dependency versions in pyproject.toml
- Regenerate uv.lock lockfile
- Update CI workflow if necessary

## Notes

- Treat this as a scaffold, not a hard-coded script.
- Update the command if the workflow evolves materially.