---
name: scifo-code-implementation
description: Implement a requested feature, fix, or refactor using repository patterns and proportionate delegation.
---

1. Read applicable repository guidance and inspect nearby code. For a clear implementation request, the request itself authorizes changes within its scope; do not ask for an extra task recap or plan approval.
2. Identify the smallest coherent change and affected interfaces or callers. Resolve ordinary details from repository conventions. Ask the user only when a material behavior, scope, or tradeoff decision remains unresolved.
3. Make tiny, localized edits directly when that is more efficient. Delegate substantial or independently useful bounded work to `scifo_implementer`, giving it clear ownership, context, and an expected result. Preserve unrelated work and avoid broad cleanup.
4. Request independent `scifo_reviewer` review for meaningful completed changes, reconcile material findings, and inspect the final diff.
5. Run checks only when requested or required by the agreed acceptance criteria. Do not add or run tests or unrelated checks by default.
6. Report what changed, checks actually performed, and any remaining issue or uncertainty.

When delegated, this skill guides the implementer subagent. If implementation reveals a material decision outside the approved scope, pause that part and return a clear question or options to the orchestrator rather than guessing.
