---
name: dependency-update-npm-package
description: Workflow command scaffold for dependency-update-npm-package in rsshub-never-die.
allowed_tools: ["Bash", "Read", "Write", "Grep", "Glob"]
---

# /dependency-update-npm-package

Use this workflow when working on **dependency-update-npm-package** in `rsshub-never-die`.

## Goal

Updates the version of an npm package dependency (production or development) using Dependabot or similar automation.

## Common Files

- `package.json`
- `pnpm-lock.yaml`

## Suggested Sequence

1. Understand the current state and failure mode before editing.
2. Make the smallest coherent change that satisfies the workflow goal.
3. Run the most relevant verification for touched files.
4. Summarize what changed and what still needs review.

## Typical Commit Signals

- Update the dependency version in package.json
- Regenerate or update pnpm-lock.yaml to reflect the new dependency tree
- Commit both files with a standardized message

## Notes

- Treat this as a scaffold, not a hard-coded script.
- Update the command if the workflow evolves materially.