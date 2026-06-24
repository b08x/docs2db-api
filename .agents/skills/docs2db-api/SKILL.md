```markdown
# docs2db-api Development Patterns

> Auto-generated skill from repository analysis

## Overview
This skill teaches the core development conventions and workflows for the `docs2db-api` TypeScript codebase. It covers file and code style, commit patterns, dependency maintenance workflows, and testing practices to help contributors work effectively and consistently.

## Coding Conventions

- **File Naming:**  
  Use camelCase for file names.  
  *Example:*  
  ```
  getUserData.ts
  processDocuments.test.ts
  ```

- **Import Style:**  
  Use relative imports for internal modules.  
  *Example:*  
  ```typescript
  import { fetchData } from './fetchData';
  ```

- **Export Style:**  
  Use named exports.  
  *Example:*  
  ```typescript
  export function processDocuments() { ... }
  export const API_VERSION = 'v1';
  ```

- **Commit Patterns:**  
  - Use prefixes like `fix` and `chore` in commit messages.
  - Keep commit messages concise (average ~55 characters).
  *Example:*  
  ```
  fix: handle null values in document parser
  chore: update dependencies and lockfile
  ```

## Workflows

### Dependency Update with Lockfile
**Trigger:** When you want to update dependencies to their latest non-major versions.  
**Command:** `/update-dependencies`

1. Update dependency versions in `pyproject.toml`.
2. Regenerate the `uv.lock` lockfile to match the new dependencies.
3. Update the CI workflow file (`.github/workflows/ci.yml`) if necessary.

*Example:*
```bash
# Step 1: Edit pyproject.toml as needed
# Step 2: Regenerate lockfile
uv pip compile
# Step 3: Commit changes
git add pyproject.toml uv.lock .github/workflows/ci.yml
git commit -m "chore: update dependencies and lockfile"
```

### Lockfile Maintenance
**Trigger:** When you want to ensure the lockfile reflects the current dependency state.  
**Command:** `/lockfile-maintenance`

1. Regenerate or update the `uv.lock` lockfile.

*Example:*
```bash
uv pip compile
git add uv.lock
git commit -m "chore: update lockfile"
```

## Testing Patterns

- **Test File Naming:**  
  Test files follow the `*.test.*` pattern.  
  *Example:*  
  ```
  processDocuments.test.ts
  ```

- **Testing Framework:**  
  The specific framework is not detected, but tests are likely written in TypeScript and placed alongside or near the code they test.

- **Example Test File Skeleton:**  
  ```typescript
  import { processDocuments } from './processDocuments';

  describe('processDocuments', () => {
    it('should process input correctly', () => {
      // test logic here
    });
  });
  ```

## Commands

| Command                | Purpose                                               |
|------------------------|-------------------------------------------------------|
| /update-dependencies   | Update dependencies and regenerate lockfile           |
| /lockfile-maintenance  | Regenerate or update the dependency lockfile          |
```
