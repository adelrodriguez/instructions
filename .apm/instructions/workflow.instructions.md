---
description: Follow these patterns when working with the user on a task
---

## How we work

- Follow the repository's own conventions. Where its `CODING_STANDARDS.md` or `AGENTS.md` differs from these rules, the repository wins.
- Before adding a structure, name, CI job, or script, check comparable examples in my other repositories. Reuse conventions that fit the current repository. When a convention changes, propose applying it to every repository that uses it.
- Before changing module boundaries, public APIs, or folder organization, use the `codebase-design` skill. Rank the options, explain your recommendation, and show a dry run. Wait for my agreement before implementation.
- For edits across many files, migrations, or analysis, write a codemod or script instead of working by hand. Do the first unit by hand, then check the script against it. Keep the script so that a reviewer can run it again.
- In a sweep or migration, verify each change before you start the next one. Order commits so that the history makes the case: removal before reshaping, scaffold before feature, and a failing test before its fix.
- When a step is in scope and can be undone, do it and report it. Do not end a reply by asking whether to do it.
- Prefer a package or module the repository already has. Ask before adding a dependency, and install it following its official docs.
- Answer a "why" question with the reason. Change code only when I ask.
- Make changes through pull requests. Merge only when I ask.
- Fix the cause of a failure. Do not add an exception, allowlist, or suppression in its place.
- Before disabling a lint rule, read its documentation and check its configuration options. If an upstream tool has a bug, file an issue or submit a fix. Link any local workaround to the upstream issue and state when to remove it.
