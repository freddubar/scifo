---
name: scifo-code-review
description: Review a completed code diff for actionable bugs, regressions, security issues, and missing verification. Use after a meaningful implementation or when the user asks for a review.
---

1. Read the request, applicable repository guidance, and the complete diff under review.
2. Trace changed behavior into relevant callers and tests; focus on correctness, security, regressions, and compatibility.
3. Report only actionable findings, ordered by severity, with precise file and line references and a triggering scenario.
4. If no actionable finding is supported, say so and state what you could not verify.
5. Do not edit files or disclose secret values. Do not read `.scifo/secrets.local.md`, `.env` files, credential stores, or authentication files.

When used by Scifo, this skill supports the independent `scifo_reviewer` role after implementation is complete.
