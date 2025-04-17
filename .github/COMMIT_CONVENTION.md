# Commit Convention (Based on Angular Convention)

This document outlines the commit convention used for my project, aligning with the widely adopted Angular Commit Convention. Following this convention helps to maintain a clear, consistent, and easily understandable commit history, facilitating collaboration and project maintenance.

**TL;DR:**

Messages must be matched by the following regex:
```
`/^(revert: )?(feat|fix|docs|style|refactor|perf|test|build|ci|chore|types)(\(.+\))?!?: .{1,72}/;`
```

## Commit Message Format:

Each commit message should consist of a **type**, an optional **scope**, and a **subject**. The subject should be followed by an optional **body** and an optional **footer(s)**.

```
<type>(<scope>): <subject>

<body (optional)>

<footer> (optional)
```

## 1\. Type:

The `<type>` is mandatory and describes the nature of the change introduced by the commit. Use one of the following types (similar to Angular):

  * **feat**: A new feature.
  * **fix**: A bug fix.
  * **docs**: Documentation only changes.
  * **style**: Changes that do not affect the meaning of the code (white-space, formatting, missing semi-colons, etc.).
  * **refactor**: A code change that neither fixes a bug nor adds a feature.
  * **perf**: A code change that improves performance.
  * **test**: Adding missing tests or correcting existing tests.
  * **build**: Changes that affect the build system or external dependencies (e.g., npm, yarn, webpack).
  * **ci**: Changes to our CI configuration files and scripts (e.g., GitHub Actions, Travis CI).
  * **chore**: Other changes that don't modify source or test files (e.g., updating dependencies, task runners).
  * **revert**: Reverts a previous commit.

## 2\. Scope (Optional):

The `<scope>` is optional and provides context about the area of the codebase affected by the commit. This could be a specific component, module, directory, or feature area.

  * Use a lowercase noun enclosed in parentheses, e.g., `(profile)`, `(inventory)`, `(shop)`.
  * If the change affects more than one scope, you can use `*` or be more specific if it improves clarity.

## 3\. Subject:

The `<subject>` is a concise description of the change.

  * Use the imperative, present tense ("change" not "changed" nor "changes").
  * Capitalize the first word.
  * Do not use a trailing period.
  * Keep it brief (ideally under 50 characters).

## 4\. Body (Optional):

The `<body>` provides a more detailed explanation of the commit, justifying the changes and providing context.

  * Separate it from the subject with a blank line.
  * Use the imperative, present tense.
  * Wrap lines at 72 characters.
  * Explain the *what* and *why* of the change, not just the *how*.

## 5\. Footer(s) (Optional):

The `<footer>` can contain metadata about the commit, such as:

  * **BREAKING CHANGE:** Indicate major API changes. Prefix with `BREAKING CHANGE:` followed by a description of the change, justification, and migration instructions.
  * **Closes**: References one or more issues that this commit closes (e.g., `Closes #123`, `Closes #456, #789`).
  * **Fixes**: References one or more issues that this commit fixes (e.g., `Fixes #123`).
  * **Refs**: References one or more issues that this commit relates to (e.g., `Refs #123`).
  * **Co-authored-by**: Indicate collaborators on the commit using the `Co-authored-by: Name <email@example.com>` format.

## Examples:

```
feat(profile): implement user profile creation

Adds the functionality for users to create their profiles
with basic information like username and timezone.

Closes #10

```

```
fix(shop): prevent selling resources for negative Pebs

Addresses an issue where selling certain resources could
result in the user receiving a negative amount of Pebs.

Refs #25

```

```
docs(commit-convention): add explanation of the scope

Clarifies the usage and purpose of the optional scope
in commit messages for better understanding.

```

```
chore: update dependencies to latest versions

Updates all project dependencies listed in package.json
to their most recent stable releases.

```

```
BREAKING CHANGE: The 'oldFunction' has been renamed to 'newFunction'.

To migrate, update all instances of 'oldFunction' to 'newFunction'.

```

## Benefits of Following This Convention:

  * **Automated Changelog Generation:** Tools like `conventional-changelog` can automatically generate changelogs based on the commit history.
  * **Improved Code Review:** Clear and consistent commit messages make it easier for reviewers to understand the purpose of each change.
  * **Better Project History:** A standardized commit history improves project maintainability and makes it easier to track changes and understand the project's evolution.
  * **Semantic Versioning:** The commit types help in automatically determining the next semantic version release.
  * **Better Collaboration:** Provides a common language for contributors to describe their changes.

By adhering to this commit convention, we can maintain a more organized and understandable project history for Alikuxac, following best practices from the Angular community.
```