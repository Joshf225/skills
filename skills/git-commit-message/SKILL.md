---
name: git-commit-message
description: Generate git commit messages in Conventional Commits format for changes made during the current agent session. Use when the user says things like "lets commit this", "make a commit message", "commit these changes", "commit this", "create a commit message", "generate a commit", or any request to prepare or write a git commit. Lists all files modified, added, or deleted during the session, categorized by change type. Does NOT run git commands — output only.
---

# Git Commit Message

Generate a Conventional Commits message and a categorized file list for the changes made during the current agent session.

## Workflow

1. **Identify session files** — Recall which files were created, modified, or deleted during this conversation session. Only include files the agent touched in this session. Do NOT include files that were already changed before the session began.

2. **Categorize files** into three groups:
   - **Added** — New files created during this session
   - **Modified** — Existing files edited during this session
   - **Deleted** — Files removed during this session

3. **Determine the commit type** from the Conventional Commits spec:
   - `feat` — A new feature or capability
   - `fix` — A bug fix
   - `refactor` — Code restructured without changing behaviour
   - `chore` — Maintenance, config, dependency updates
   - `docs` — Documentation only changes
   - `style` — Formatting, whitespace (no logic changes)
   - `test` — Adding or updating tests
   - `perf` — Performance improvements
   - `build` — Build system or tooling changes
   - `ci` — CI/CD configuration changes

   If the session touched multiple concerns, pick the **dominant** type and note the others in the commit body.

4. **Write the commit message**:
   - Format: `type(optional-scope): short imperative summary`
   - Subject line: max 72 characters, imperative mood (e.g., "add", not "added" or "adds")
   - Scope: optional, use the feature area or module (e.g., `auth`, `api`, `ui`, `dashboard`)
   - Body: include a bullet-point body only when the changes are complex or span multiple concerns — explain the **why**, not the what

5. **Present the output** in the format below. Do NOT run any git commands.

## Output Format

```
## Commit Message

<type>(<scope>): <subject>

<optional body with bullet points explaining why>

## Files Changed This Session

### Added
- path/to/new-file.ts

### Modified
- path/to/changed-file.ts
- path/to/another-file.tsx

### Deleted
- path/to/removed-file.ts
```

Omit any category section (Added / Modified / Deleted) if it has no files.

## Examples

**Simple fix, no body needed:**
```
## Commit Message

fix(auth): resolve token expiry not clearing user session

## Files Changed This Session

### Modified
- src/store/authSlice.ts
- src/utils/tokenHelper.ts
```

**Multi-concern feature, body included:**
```
## Commit Message

feat(invoices): add PDF export and status filter

- PDF export required a new utility and updates to the invoice detail page
- Status filter required changes to the Redux slice and the API query params

## Files Changed This Session

### Added
- src/utils/exportPdf.ts

### Modified
- src/pages/InvoiceDetail.tsx
- src/store/invoiceSlice.ts
- src/api/invoicesApi.ts
```
