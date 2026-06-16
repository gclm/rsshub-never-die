---
name: semantic-release-version-bump
description: Workflow command scaffold for semantic-release-version-bump in rsshub-never-die.
allowed_tools: ["Bash", "Read", "Write", "Grep", "Glob"]
---

# /semantic-release-version-bump

Use this workflow when working on **semantic-release-version-bump** in `rsshub-never-die`.

## Goal

Performs a release: bumps the version, updates CHANGELOG.md, and updates package.json version.

## Common Files

- `CHANGELOG.md`
- `package.json`

## Suggested Sequence

1. Understand the current state and failure mode before editing.
2. Make the smallest coherent change that satisfies the workflow goal.
3. Run the most relevant verification for touched files.
4. Summarize what changed and what still needs review.

## Typical Commit Signals

- Update CHANGELOG.md with new release notes
- Update the version in package.json
- Commit both files with a release message

## Notes

- Treat this as a scaffold, not a hard-coded script.
- Update the command if the workflow evolves materially.