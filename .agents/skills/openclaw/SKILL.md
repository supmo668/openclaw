```markdown
# openclaw Development Patterns

> Auto-generated skill from repository analysis

## Overview
This skill introduces the core development patterns and conventions used in the `openclaw` TypeScript codebase. You'll learn how to write code that fits the project's style, structure your files, manage imports/exports, and follow commit and testing practices. This guide is ideal for contributors aiming for consistency and maintainability in openclaw.

## Coding Conventions

### File Naming
- Use **camelCase** for file names.
  - Example: `userService.ts`, `apiClient.test.ts`

### Import Style
- Use **absolute imports** throughout the codebase.
  - Example:
    ```typescript
    import { fetchData } from 'services/apiClient';
    ```

### Export Style
- Use **named exports** rather than default exports.
  - Example:
    ```typescript
    // In userService.ts
    export function getUser(id: string) { ... }
    export const USER_ROLE = 'admin';

    // In another file
    import { getUser, USER_ROLE } from 'services/userService';
    ```

### Commit Messages
- Follow **conventional commit** format.
- Common prefixes: `feat`, `chore`.
- Example:
  ```
  feat: add user authentication middleware
  chore: update dependencies to latest versions
  ```

## Workflows

### Making a Feature Change
**Trigger:** When adding new functionality  
**Command:** `/feature-change`

1. Create a new branch for your feature.
2. Write code using camelCase file names, absolute imports, and named exports.
3. Add or update tests in `*.test.*` files.
4. Commit changes with a `feat:` prefix and a clear, concise message.
5. Open a pull request for review.

### Running Tests
**Trigger:** Before pushing or merging changes  
**Command:** `/run-tests`

1. Identify test files matching the `*.test.*` pattern.
2. Use the project's test runner (framework is unspecified; check project docs or scripts).
3. Run all tests and ensure they pass.
4. Address any failures before proceeding.

### Chore or Maintenance Update
**Trigger:** When updating dependencies, configs, or non-feature code  
**Command:** `/chore-update`

1. Make necessary changes (e.g., update dependencies).
2. Commit with a `chore:` prefix and a descriptive message.
3. Run tests to verify nothing is broken.
4. Open a pull request for review.

## Testing Patterns

- Test files use the pattern `*.test.*` (e.g., `apiClient.test.ts`).
- The specific testing framework is not detected; refer to project documentation or package.json for details.
- Place tests alongside the code they verify or in a dedicated `tests` directory.
- Example test file:
  ```typescript
  // apiClient.test.ts
  import { fetchData } from 'services/apiClient';

  describe('fetchData', () => {
    it('returns data for valid input', () => {
      // test implementation
    });
  });
  ```

## Commands
| Command         | Purpose                                      |
|-----------------|----------------------------------------------|
| /feature-change | Add or update a feature                      |
| /run-tests      | Run all tests before pushing or merging      |
| /chore-update   | Perform maintenance or dependency updates    |
```