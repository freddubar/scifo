---
name: scifo-code-implementation
description: Make a bounded code change after the user has requested implementation. Use to implement a scoped feature, fix, or refactor while following the existing repository patterns.
---

1. Confirm the task boundary and read applicable repository guidance and nearby code.
2. Identify the smallest coherent change and any affected interfaces or callers. Ask only when an unresolved choice would materially change the result.
3. Make the requested change using existing patterns. Preserve unrelated work and avoid broad cleanup.
4. Run checks only when the user requested verification or the acceptance criteria require them. Do not add or run unrelated tests.
5. Report what changed, checks actually performed, and any remaining issue or uncertainty.

When used by Scifo, this skill guides the implementer subagent. The orchestrator delegates target-repository edits and does not edit code directly.
