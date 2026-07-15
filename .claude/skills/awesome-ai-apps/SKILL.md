```markdown
# awesome-ai-apps Development Patterns

> Auto-generated skill from repository analysis

## Overview
This skill provides guidance on the development patterns used in the `awesome-ai-apps` repository. The codebase is written in TypeScript without a specific framework, and it organizes code using clear conventions for file naming, imports, and exports. It also includes workflows for dependency management across multiple packages and describes testing patterns.

## Coding Conventions

### File Naming
- **Convention:** camelCase for file names.
- **Example:**  
  ```
  aiHelper.ts
  appConfig.ts
  ```

### Import Style
- **Convention:** Use relative imports for modules within the project.
- **Example:**
  ```typescript
  import { fetchData } from './apiClient';
  import { processResult } from '../utils/resultProcessor';
  ```

### Export Style
- **Convention:** Use named exports for all modules.
- **Example:**
  ```typescript
  // In aiHelper.ts
  export function generateAIResponse(input: string): string {
    // ...
  }
  ```

## Workflows

### update-npm-dependencies-multi-package
**Trigger:** When you need to update npm dependencies across multiple packages or subprojects (e.g., in a monorepo).
**Command:** `/update-dependencies`

1. Identify outdated dependencies in all `package.json` files.
2. Update the version numbers for those dependencies in each `package.json`.
3. Regenerate the corresponding lock files (`package-lock.json`, `pnpm-lock.yaml`, etc.).
4. Commit all updated `package.json` and lock files together.

**Files Involved:**
- `**/package.json`
- `**/package-lock.json`
- `**/pnpm-lock.yaml`

**Example:**
```sh
# Manually updating dependencies in multiple packages
cd packages/app1
npm update
cd ../app2
npm update
# Regenerate lock files as needed
# Commit changes
git add packages/*/package.json packages/*/package-lock.json
git commit -m "chore: update dependencies across packages"
```

## Testing Patterns

- **Test File Pattern:** Files are named with the `.test.` infix (e.g., `myModule.test.ts`).
- **Testing Framework:** Not explicitly detected; check the repository for specific test runner configuration.
- **Example:**
  ```typescript
  // In mathUtils.test.ts
  import { sum } from './mathUtils';

  test('sum adds two numbers', () => {
    expect(sum(2, 3)).toBe(5);
  });
  ```

## Commands

| Command               | Purpose                                                    |
|-----------------------|------------------------------------------------------------|
| /update-dependencies  | Update npm dependencies across all packages and lock files. |
```
