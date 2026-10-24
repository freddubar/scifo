---
name: scifo-shape-and-plan
description: Clarify a rough software idea with the user, inspect the repository, and get approval on an executable plan before implementation.
---

# Shape an idea, plan it, then build it

Use this workflow when the user invokes `$scifo-shape-and-plan` or explicitly asks to shape an early coding idea into an implementation plan and then proceed. It is intended for software work. For non-coding or general ideas, use `$scifo-grill-me` and stop at the conversational recap.

Keep the user involved at two decision points: first confirm that the clarified idea is accurate, then approve the implementation plan. Do not edit files before the plan is approved.

## 1. Clarify the idea

Before the interview, read the applicable `AGENTS.md` instructions so the workflow follows repository guidance. Do not explore relevant code yet. Start from the user's rough idea, even if it is incomplete. Restate your understanding and ask a small batch of related, consequential questions. Use the answers to choose the next round; ask only questions whose prerequisites are clear. Explore intended users and outcomes, scope boundaries, constraints, tradeoffs, success signals, and important failure cases as relevant.

Be candid about conflicting assumptions and alternatives, while leaving decisions with the user. Accept "I don't know" as a valid answer. If discussion cannot resolve a question, record it as an open item with a concrete research or prototype step instead of repeatedly rephrasing it. Keep the session focused and stop when the remaining decisions are settled or explicitly left open.

Give a concise recap of the goal, audience, decisions, constraints, assumptions, and open questions. Ask the user to confirm or correct this recap. Do not inspect relevant code or draft the executable implementation plan until the user confirms the recap.

## 2. Inspect and plan

After confirmation, inspect the current repository instructions and relevant code, using `scifo-repo-orientation` when the project is unfamiliar or the exploration is substantial. Ground the plan in actual repository structure and conventions. Resolve straightforward implementation details from repository evidence; ask the user only about remaining choices that materially change the result.

Produce an executable plan with the expected behavior, bounded implementation steps and likely ownership/files, relevant checks, and material risks or unresolved dependencies. Keep it concise and specific enough that another implementer can act on it. Present the plan in the conversation and ask the user to approve it or request changes. Do not edit files while approval is pending.

Plan mode is optional. This skill cannot toggle the coding agent's UI mode. If the user wants native Plan mode, explain that they can invoke it manually; otherwise continue the clarification and planning workflow in the current mode.

## 3. Implement after approval

Once the user approves the plan, continue in the same conversation. Follow Scifo's existing orchestration instructions: delegate bounded target-project edits to `scifo_implementer`, preserve unrelated work, and ask `scifo_reviewer` for an independent read-only review after meaningful changes. Use `scifo_researcher` for substantial independent investigation where useful. Reconcile review findings through the implementer, then report the resulting behavior, files changed, checks actually run, and any unresolved risks.

Do not add or run tests unless requested or required by the agreed acceptance criteria. Follow applicable repository and runtime approval rules for checks and side effects.

## Persistence

Keep the recap, plan, and progress in the conversation by default. Write a plan or progress artifact only when the user asks, or when a handoff across threads or sessions is needed to recover the agreed context. If that becomes necessary, tell the user what artifact you intend to create and keep it within the approved project scope.
