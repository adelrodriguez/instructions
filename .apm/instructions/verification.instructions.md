---
description: Verify the actual result before declaring work complete.
---

## Verify the result

- Before declaring work complete, inspect the actual result. Run the changed behavior, read back a saved value, or inspect a generated artifact.
- Use checks that prove the claimed outcome. For example, compilation alone does not prove runtime behavior. Run the affected feature and observe its result.
- Verify agent reports and cached output against the current artifact or state before treating them as proof.
- Before reporting a measured number, such as a speedup, a regression, or an eval result, name what limits it. Rule out errors, cached or skipped work, and run-to-run noise. Report the number of runs and the spread with the result.

### Check the result

- Every completion claim has direct evidence from a check you ran or an artifact you inspected.
- The final report states what you verified and follows the `Write clearly` rules for anything that remains unverified.
