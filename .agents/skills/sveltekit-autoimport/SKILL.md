```markdown
# sveltekit-autoimport Development Patterns

> Auto-generated skill from repository analysis

## Overview
This skill teaches you the core development patterns and conventions used in the `sveltekit-autoimport` TypeScript codebase. You'll learn about file naming, import/export styles, commit message habits, and how to write and run tests. While the repository does not use a formal framework or automated workflows, it follows clear conventions to ensure code consistency and maintainability.

## Coding Conventions

### File Naming
- Use **camelCase** for file names.
  - Example: `autoImportConfig.ts`, `resolveImports.ts`

### Import Style
- Use **relative imports** for internal modules.
  - Example:
    ```typescript
    import { resolveImports } from './resolveImports';
    ```

### Export Style
- Use **named exports** for all modules.
  - Example:
    ```typescript
    export function autoImportConfig() { ... }
    export const DEFAULTS = { ... };
    ```

### Commit Messages
- Commit messages are **freeform** (no enforced prefixes).
- Average commit message length: ~63 characters.
  - Example:  
    ```
    Add support for custom import paths in config
    ```

## Workflows

### Adding a New Utility Module
**Trigger:** When you need to add a new helper or utility function.
**Command:** `/add-utility-module`

1. Create a new file using camelCase (e.g., `myUtility.ts`).
2. Write your function(s) and export them using named exports.
    ```typescript
    export function myUtility() { ... }
    ```
3. Import your utility in other files using a relative import.
    ```typescript
    import { myUtility } from './myUtility';
    ```
4. Add or update tests in a corresponding `.test.ts` file.

### Writing and Running Tests
**Trigger:** When you add or modify code that needs testing.
**Command:** `/run-tests`

1. Create or update a test file matching the pattern `*.test.*` (e.g., `autoImportConfig.test.ts`).
2. Write test cases for your functions.
3. Run your tests using the project's test runner (framework not specified; check project scripts or documentation).

### Refactoring Imports
**Trigger:** When reorganizing or cleaning up import statements.
**Command:** `/refactor-imports`

1. Ensure all imports are relative (e.g., `./moduleName`).
2. Use named imports and exports exclusively.
    ```typescript
    import { functionName } from './functionName';
    export function functionName() { ... }
    ```

## Testing Patterns

- Test files follow the `*.test.*` naming convention (e.g., `resolveImports.test.ts`).
- The specific testing framework is **unknown**; check the repository for test runner details.
- Tests are written in TypeScript.
- Place tests alongside or near the modules they cover.

## Commands
| Command              | Purpose                                      |
|----------------------|----------------------------------------------|
| /add-utility-module  | Scaffold a new utility module with tests     |
| /run-tests           | Run all test files in the repository         |
| /refactor-imports    | Standardize imports to relative and named    |
```