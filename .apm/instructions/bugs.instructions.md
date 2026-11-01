---
description: Route bugs found during a task by scope and conflicts with the current changes.
---

## Handle bugs

### Check the scope

For an in-scope bug, use the `testing` skill to write a failing test, then fix the bug. Report the bug and fix to the user.

If a bug is outside the current scope, use the `issue` skill to file it and suggest another PR.

### Find the root cause

- Before adding a guard, ask whether the state that triggered the bug is legitimate. If the system may be in that state, handle it where the code broke. If the state should never exist, find the code that produced it and fix that code instead.
- After fixing one instance, search for the same fault elsewhere and fix every instance.
- When two fixes based on the same assumption have failed the same check, write the assumption down and test it directly before you try another fix.

### Choose the PR for an out-of-scope fix

- If the fix will conflict with the current changes, suggest a stacked PR.
- If the fix will not conflict, suggest a sibling PR based on the current PR's base branch.

Continue the current task. Fix an out-of-scope bug only if the user asks.
