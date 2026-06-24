---
name: lockfile-maintenance
description: Workflow command scaffold for lockfile-maintenance in docs2db-api.
allowed_tools: ["Bash", "Read", "Write", "Grep", "Glob"]
---

# /lockfile-maintenance

Use this workflow when working on **lockfile-maintenance** in `docs2db-api`.

## Goal

Performs maintenance on the dependency lockfile, typically to keep it in sync or up-to-date.

## Common Files

- `uv.lock`

## Suggested Sequence

1. Understand the current state and failure mode before editing.
2. Make the smallest coherent change that satisfies the workflow goal.
3. Run the most relevant verification for touched files.
4. Summarize what changed and what still needs review.

## Typical Commit Signals

- Regenerate or update uv.lock lockfile

## Notes

- Treat this as a scaffold, not a hard-coded script.
- Update the command if the workflow evolves materially.