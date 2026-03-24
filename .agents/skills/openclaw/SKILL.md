---
name: openclaw-conventions
description: Development conventions and patterns for openclaw. TypeScript Express project with conventional commits.
---

# Openclaw Conventions

> Generated from [supmo668/openclaw](https://github.com/supmo668/openclaw) on 2026-03-24

## Overview

This skill teaches Claude the development patterns and conventions used in openclaw.

## Tech Stack

- **Primary Language**: TypeScript
- **Framework**: Express
- **Architecture**: type-based module organization
- **Test Location**: colocated
- **Test Framework**: vitest

## When to Use This Skill

Activate this skill when:
- Making changes to this repository
- Adding new features following established patterns
- Writing tests that match project conventions
- Creating commits with proper message format

## Commit Conventions

Follow these commit message conventions based on 8 analyzed commits.

### Commit Style: Conventional Commits

### Prefixes Used

- `fix`
- `refactor`
- `feat`
- `chore`
- `docs`

### Message Guidelines

- Average message length: ~60 characters
- Keep first line concise and descriptive
- Use imperative mood ("Add feature" not "Added feature")


*Commit message example*

```text
chore: trigger CI/CD deploy
```

*Commit message example*

```text
ci: trigger deploy with org-level Fly token
```

*Commit message example*

```text
feat: set Cerebras as default LLM model for production
```

*Commit message example*

```text
test(identity-e2e): 37-case E2E suite for identity-scoped memory pipeline
```

*Commit message example*

```text
docs(identity-stack): rewrite feature documentation with source-verified accuracy
```

*Commit message example*

```text
Merge pull request #2 from supmo668/feat/auth-memory-gate
```

*Commit message example*

```text
ci: enable Fly.io deploy on feat/auth-memory-gate branch
```

*Commit message example*

```text
feat: externalize secrets, enable all channels, fix whoami command
```

## Architecture

### Project Structure: Monorepo

This project uses **type-based** module organization.

### Source Layout

```
src/
├── acp/
├── agents/
├── auto-reply/
├── browser/
├── canvas-host/
├── channels/
├── cli/
├── commands/
├── compat/
├── config/
```

### Entry Points

- `src/index.ts`

### Configuration Files

- `.github/workflows/auto-response.yml`
- `.github/workflows/ci.yml`
- `.github/workflows/deploy-fly.yml`
- `.github/workflows/docker-release.yml`
- `.github/workflows/formal-conformance.yml`
- `.github/workflows/install-smoke.yml`
- `.github/workflows/labeler.yml`
- `.github/workflows/sandbox-common-smoke.yml`
- `.github/workflows/stale.yml`
- `.github/workflows/workflow-sanity.yml`
- `Dockerfile`
- `Swabble/.github/workflows/ci.yml`
- `docker-compose.yml`
- `extensions/auth-memory-gate/package.json`
- `extensions/bluebubbles/package.json`
- `extensions/copilot-proxy/package.json`
- `extensions/diagnostics-otel/package.json`
- `extensions/discord/package.json`
- `extensions/feishu/package.json`
- `extensions/google-antigravity-auth/package.json`
- `extensions/google-gemini-cli-auth/package.json`
- `extensions/googlechat/package.json`
- `extensions/imessage/package.json`
- `extensions/irc/package.json`
- `extensions/line/package.json`
- `extensions/llm-task/package.json`
- `extensions/lobster/package.json`
- `extensions/matrix/package.json`
- `extensions/mattermost/package.json`
- `extensions/memory-core/package.json`
- `extensions/memory-graphiti/package.json`
- `extensions/memory-lancedb/package.json`
- `extensions/minimax-portal-auth/package.json`
- `extensions/msteams/package.json`
- `extensions/nextcloud-talk/package.json`
- `extensions/nostr/package.json`
- `extensions/open-prose/package.json`
- `extensions/openai-codex-auth/package.json`
- `extensions/persist-postgres/package.json`
- `extensions/persist-user-identity/package.json`
- `extensions/signal/package.json`
- `extensions/slack/package.json`
- `extensions/telegram/package.json`
- `extensions/tlon/package.json`
- `extensions/twitch/package.json`
- `extensions/voice-call/package.json`
- `extensions/whatsapp/package.json`
- `extensions/zalo/package.json`
- `extensions/zalouser/package.json`
- `package.json`
- `packages/clawdbot/package.json`
- `packages/moltbot/package.json`
- `scripts/docker/cleanup-smoke/Dockerfile`
- `scripts/docker/install-sh-e2e/Dockerfile`
- `scripts/docker/install-sh-nonroot/Dockerfile`
- `scripts/docker/install-sh-smoke/Dockerfile`
- `scripts/e2e/Dockerfile`
- `tsconfig.json`
- `ui/package.json`
- `ui/vite.config.ts`
- `ui/vitest.config.ts`
- `vendor/a2ui/.github/workflows/docs.yml`
- `vendor/a2ui/.github/workflows/editor_build.yml`
- `vendor/a2ui/.github/workflows/inspector_build.yml`
- `vendor/a2ui/.github/workflows/java_build_and_test.yml`
- `vendor/a2ui/.github/workflows/lit_samples_build.yml`
- `vendor/a2ui/.github/workflows/ng_build_and_test.yml`
- `vendor/a2ui/.github/workflows/python_samples_build.yml`
- `vendor/a2ui/.github/workflows/web_build_and_test.yml`
- `vendor/a2ui/renderers/angular/package.json`
- `vendor/a2ui/renderers/angular/tsconfig.json`
- `vendor/a2ui/renderers/lit/package.json`
- `vendor/a2ui/renderers/lit/tsconfig.json`
- `vendor/a2ui/specification/0.8/eval/package.json`
- `vendor/a2ui/specification/0.8/eval/tsconfig.json`
- `vendor/a2ui/specification/0.9/eval/package.json`
- `vendor/a2ui/specification/0.9/eval/tsconfig.json`
- `vitest.config.ts`

### Guidelines

- Group code by type (components, services, utils)
- Keep related functionality in the same type folder
- Avoid circular dependencies between type folders

## Code Style

### Language: TypeScript

### Naming Conventions

| Element | Convention |
|---------|------------|
| Files | camelCase |
| Functions | camelCase |
| Classes | PascalCase |
| Constants | SCREAMING_SNAKE_CASE |

### Import Style: Mixed Style

### Export Style: Mixed Style


## Testing

### Test Framework: vitest

### File Pattern: `*.test.ts`

### Test Types

- **Unit tests**: Test individual functions and components in isolation
- **Integration tests**: Test interactions between multiple components/services
- **E2e tests**: Test complete user flows through the application

### Mocking: vi.mock

### Coverage

This project has coverage reporting configured. Aim for 80%+ coverage.


*Test file structure*

```typescript
import { describe, it, expect } from 'vitest'

describe('MyFunction', () => {
  it('should return expected result', () => {
    const result = myFunction(input)
    expect(result).toBe(expected)
  })
})
```

## Error Handling

### Error Handling Style: Try-Catch Blocks


*Standard error handling pattern*

```typescript
try {
  const result = await riskyOperation()
  return result
} catch (error) {
  console.error('Operation failed:', error)
  throw new Error('User-friendly message')
}
```

## Common Workflows

These workflows were detected from analyzing commit patterns.

### Database Migration

Database schema changes with migration files

**Frequency**: ~4 times per month

**Steps**:
1. Create migration file
2. Update schema definitions
3. Generate/update types

**Files typically involved**:
- `**/types.ts`
- `**/schema.*`

**Example commit sequence**:
```
feat(sessions): add createdAt tracking and date-range filtering
feat(persist-postgres): PostgreSQL persistence plugin
Revert "feat(linq): add interactive onboarding adapter"
```

### Feature Development

Standard feature implementation workflow

**Frequency**: ~10 times per month

**Steps**:
1. Add feature implementation
2. Add tests for feature
3. Update documentation

**Files typically involved**:
- `src/config/sessions/*`
- `src/gateway/protocol/schema/*`
- `src/gateway/*`
- `**/*.test.*`

**Example commit sequence**:
```
feat(sessions): add createdAt tracking and date-range filtering
feat(persist-postgres): PostgreSQL persistence plugin
Revert "feat(linq): add interactive onboarding adapter"
```


## Best Practices

Based on analysis of the codebase, follow these practices:

### Do

- Use conventional commit format (feat:, fix:, etc.)
- Write tests using vitest
- Follow *.test.ts naming pattern
- Use camelCase for file names
- Prefer mixed exports

### Don't

- Don't write vague commit messages
- Don't skip tests for new features
- Don't deviate from established patterns without discussion

---

*This skill was auto-generated by [ECC Tools](https://ecc.tools). Review and customize as needed for your team.*
