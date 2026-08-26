---
name: dependency-update-github-actions-workflow
description: Workflow command scaffold for dependency-update-github-actions-workflow in rsshub-never-die.
allowed_tools: ["Bash", "Read", "Write", "Grep", "Glob"]
---

# /dependency-update-github-actions-workflow

Use this workflow when working on **dependency-update-github-actions-workflow** in `rsshub-never-die`.

## Goal

Updates the version of a GitHub Actions workflow dependency (such as Docker or pnpm actions) in workflow YAML files.

## Common Files

- `.github/workflows/docker.yml`
- `.github/workflows/release.yml`
- `.github/workflows/test.yml`

## Suggested Sequence

1. Understand the current state and failure mode before editing.
2. Make the smallest coherent change that satisfies the workflow goal.
3. Run the most relevant verification for touched files.
4. Summarize what changed and what still needs review.

## Typical Commit Signals

- Update the action version in .github/workflows/*.yml files
- Commit the updated workflow files with a standardized message

## Notes

- Treat this as a scaffold, not a hard-coded script.
- Update the command if the workflow evolves materially.