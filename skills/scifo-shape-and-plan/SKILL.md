---
name: scifo-shape-and-plan
description: Clarify an early coding idea, inspect the repository, and either implement it or return a plan based on the user's request.
---

# Shape and plan coding work

Use this workflow when the user invokes `$scifo-shape-and-plan` or brings an early software idea that needs clarification before work. It is the front door for coding ideas. For general or non-coding ideas, use `$scifo-grill-me` only when the user opts into that interview; do not invoke grilling automatically.

## Clarify, then choose the path

Read applicable repository `AGENTS.md` instructions before exploring. Briefly restate your understanding of the idea and, if material uncertainties remain, ask a small batch of related questions. Let answers shape follow-up rounds. Focus on user outcome, scope, constraints, tradeoffs, success signals, and meaningful failure cases. Accept uncertainty, flag conflicting assumptions, and identify questions that need research or a prototype instead of asking them repeatedly.

When the user has asked for implementation, the request itself authorizes in-scope changes. Give a concise understanding recap, then continue without waiting for confirmation: inspect relevant repository code, conventions, and interfaces, and form an executable plan internally. Resolve ordinary details from evidence and sensible assumptions. Ask only about a material unresolved decision or a change to scope or behavior. If none remains, proceed to implementation; do not require a separate plan approval.

When the user asked only to explore, assess, or plan, clarify as needed, inspect relevant code, and present an executable plan grounded in the repository. Stop there and ask whether the user wants implementation. Do not treat an exploratory prompt as authorization to edit.

An executable plan should identify expected behavior, bounded implementation steps and likely file or agent ownership, relevant checks, and material risks or dependencies. Keep it concise and specific enough to guide implementation. It can be presented in the conversation; it does not need to be written to a file by default.

## Implement proportionally

For tiny localized edits, the main agent may edit directly when delegation would cost more than it saves. Delegate substantial or independently useful bounded changes to `scifo_implementer`. Use `scifo_researcher` for substantial investigation and `scifo_reviewer` for independent review after meaningful changes. Preserve unrelated work and reconcile material review findings before reporting.

Run checks when requested or required by the agreed acceptance criteria. Do not add or run tests or unrelated checks by default. Report what changed, checks actually performed, and unresolved risks.

Plan mode is optional. This skill cannot toggle the coding agent's UI mode. If the user wants native Plan mode, explain that they can invoke it manually; otherwise continue in the current mode.

## Persistence

Use the conversation as the default record for the recap, plan, and progress. Create a project plan or checkpoint only when the user asks or cross-session recovery warrants it. If a concise project artifact fits within the agreed scope, create it without adding a needless approval step; ask only if its contents or location would materially expand the request. Respect repository and runtime approval rules.
