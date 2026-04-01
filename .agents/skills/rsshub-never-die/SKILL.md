```markdown
# rsshub-never-die Development Patterns

> Auto-generated skill from repository analysis

## Overview

This skill teaches you how to contribute to the `rsshub-never-die` project, a TypeScript codebase built on the Hono framework. You'll learn the project's coding conventions, commit patterns, and the main development workflows for dependency management, releases, and feature work. This guide also covers how to structure tests and use common automation commands.

## Coding Conventions

- **File Naming:** Use `camelCase` for file names.
  - Example: `feedParser.ts`, `routeHandler.ts`
- **Import Style:** Both default and named imports are used.
  - Example:
    ```typescript
    import { Hono } from 'hono';
    import config from './config';
    ```
- **Export Style:** Both default and named exports are present.
  - Example:
    ```typescript
    export default function parseFeed() { ... }
    export function getFeedUrl() { ... }
    ```
- **Commit Messages:** Follow the [Conventional Commits](https://www.conventionalcommits.org/) standard.
  - Prefixes: `chore`, `ci`, `fix`, `docs`
  - Example: `fix: handle missing feed URL gracefully`

## Workflows

### Dependency Update (NPM Package)
**Trigger:** When a new version of an npm dependency is released  
**Command:** `/update-dependency`

1. Update the dependency version in `package.json`
2. Regenerate or update `pnpm-lock.yaml` to reflect the new dependency tree
3. Commit both files with a standardized message, e.g.:
    ```
    chore: bump <package-name> to <new-version>
    ```
4. Push changes and open a pull request if required

**Example:**
```bash
pnpm add <package>@latest
git add package.json pnpm-lock.yaml
git commit -m "chore: bump <package> to <new-version>"
git push
```

---

### Dependency Update (GitHub Actions Workflow)
**Trigger:** When a new version of a GitHub Actions action is released  
**Command:** `/update-action`

1. Update the action version in `.github/workflows/*.yml` files
2. Commit the updated workflow files with a standardized message, e.g.:
    ```
    chore(ci): update actions/checkout to v3
    ```
3. Push changes and open a pull request if required

**Example:**
```yaml
# .github/workflows/test.yml
- uses: actions/checkout@v3
```
```bash
git add .github/workflows/test.yml
git commit -m "chore(ci): update actions/checkout to v3"
git push
```

---

### Semantic Release Version Bump
**Trigger:** When publishing a new release after merging features or bugfixes  
**Command:** `/release`

1. Update `CHANGELOG.md` with new release notes
2. Update the version in `package.json`
3. Commit both files with a release message, e.g.:
    ```
    chore(release): v1.2.3
    ```
4. Push changes and tag the release if required

**Example:**
```bash
# After updating CHANGELOG.md and package.json
git add CHANGELOG.md package.json
git commit -m "chore(release): v1.2.3"
git tag v1.2.3
git push --follow-tags
```

---

### Feature or Bugfix with Multifile Touch
**Trigger:** When a new feature or bugfix affects both implementation and documentation/configuration  
**Command:** `/feature-bugfix`

1. Modify implementation files (e.g., `src/routes/index.ts`, `src/utils/helper.ts`)
2. Update configuration files (e.g., `.env`)
3. Update documentation (e.g., `README.md`)
4. Commit all related files with a descriptive message, e.g.:
    ```
    fix: support custom feed URLs in env config
    ```
5. Push changes and open a pull request if required

**Example:**
```bash
git add src/routes/index.ts src/utils/helper.ts .env README.md
git commit -m "feat: add support for custom feed URLs"
git push
```

## Testing Patterns

- **Test File Naming:** Use the pattern `*.test.*` (e.g., `feedParser.test.ts`)
- **Testing Framework:** Not explicitly specified; check for common frameworks like Jest or Vitest.
- **Test Example:**
    ```typescript
    // feedParser.test.ts
    import { parseFeed } from './feedParser';

    test('parses RSS feed correctly', () => {
      const xml = '<rss>...</rss>';
      expect(parseFeed(xml)).toHaveProperty('items');
    });
    ```

## Commands

| Command            | Purpose                                                         |
|--------------------|-----------------------------------------------------------------|
| /update-dependency | Update npm package dependencies and lockfile                    |
| /update-action     | Update GitHub Actions workflow dependencies                     |
| /release           | Bump version, update changelog, and prepare a new release       |
| /feature-bugfix    | Implement a feature or bugfix affecting code and documentation  |
```