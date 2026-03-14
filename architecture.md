## 🤖 AI Assistant Commit Guidelines
All commits must follow **Conventional Commits** specification. This applies to all AI assistants (Claude, Gemini, etc.) contributing to this project.

### Conventional Commit Format
```
<type>(<scope>): <subject>

<body>

<footer>
```

### Types
- **feat:** A new feature
- **fix:** A bug fix
- **docs:** Documentation only changes
- **style:** Changes that don't affect code meaning (formatting, missing semicolons, etc.)
- **refactor:** Code change that neither fixes a bug nor adds a feature
- **perf:** Code change that improves performance
- **test:** Adding missing tests or correcting existing tests
- **chore:** Changes to build process, dependencies, or tooling
- **ci:** Changes to CI/CD configuration

### Scope
The scope should specify the component or area being affected (e.g., `auth`, `transactions`, `categories`, `api`, `ui`).

### Subject
- Use imperative, present tense: "add" not "added" or "adds"
- Don't capitalize first letter
- No period (.) at the end
- Limit to 50 characters

### Body
- Optional but recommended for non-trivial changes
- Explain **what** and **why**, not **how**
- Wrap at 72 characters
- Separate from subject with a blank line

### Footer
- Reference issues: `Closes #123` or `Fixes #456`
- Breaking changes: `BREAKING CHANGE: description`

### Examples
```
feat(auth): implement JWT token refresh mechanism

Add automatic token refresh when tokens expire within 5 minutes.
Implement refresh token rotation for improved security.

Closes #42
```

```
fix(transactions): correct category balance calculation

The activity sum was not accounting for cleared transactions.
Now only cleared transactions contribute to the category total.

Fixes #89
```

```
docs(readme): update setup instructions for PostgreSQL 15
```

```
refactor(api): simplify transaction query logic

Extract common filter logic into a shared utility function
to reduce duplication across endpoints.
```