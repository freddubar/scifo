---
name: scifo-debugging
description: Diagnose a bug or unexpected behavior using repository evidence. Use when asked to investigate an error, regression, failing check, or inconsistent result.
---

1. Capture the observed behavior, expected behavior, and a concrete reproduction or evidence source.
2. Trace the relevant execution path and inspect nearby changes, inputs, and error handling.
3. Form and test the smallest useful hypotheses. Prefer read-only inspection first; run a reproducer or checks only when requested or required to confirm the cause.
4. Separate confirmed causes from plausible explanations. Cite files, symbols, and observed output.
5. If a code change is needed, give Scifo a bounded fix proposal for `scifo_implementer`; do not edit target-project code as the orchestrator.

Never print secret values while inspecting configuration or diagnostic output.
