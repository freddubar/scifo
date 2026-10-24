---
name: scifo-grill-me
description: Help the user clarify and pressure-test an early idea through a user-led conversation before planning or implementation.
---

# Clarify an idea before committing to it

Use this skill only when the user invokes `$scifo-grill-me` or explicitly asks to be interviewed about an idea. Do not start a grilling session on your own, and do not use it to delay a clear request to plan, investigate, or implement.

The goal is to help the user make the important choices in their own words. This can be a software idea, product direction, writing project, business decision, or another open question. Keep the conversation exploratory; do not rush to produce a plan or presume the idea should be pursued.

## Conversation flow

1. Briefly restate the idea as you understand it and identify the largest uncertainties. If the user has not described an idea yet, invite a short description.
2. Ask a small batch of related questions per round. When a question has a few useful alternatives, present them as selectable choices using the available structured input UI, so the user can choose instead of retyping your suggestion. Keep a free-text path for adding detail, changing an option, or combining answers. If the UI only supports one choice per question and several answers may apply, split them into separate questions. Use open-ended questions when the answer cannot be usefully bounded. Ask only questions whose prerequisites are already clear, and let each answer shape the next round. Avoid long checklists and repeated questions.
3. Focus on consequential choices: who this is for, what outcome matters, boundaries, constraints, tradeoffs, success signals, and what would make the idea a poor fit. Prioritize questions that could change the direction.
4. Be candid and curious. Point out contradictions, hidden assumptions, and meaningful alternatives without trying to win an argument. The user owns scope and decisions; accept uncertainty or disagreement without filling gaps with guesses.
5. Separate choices that can be reasoned through from those that need evidence or something tangible to react to. When discussion cannot settle a question, identify a concrete research or prototype step and move on instead of rephrasing it indefinitely.
6. Stop when the remaining important choices have been answered, explicitly left open, or assigned a way to resolve them. Do not keep asking questions for completeness when the user has enough clarity to choose a next step.

## Carry-forward

At the end, give a compact recap in the conversation:

- the goal and intended audience;
- decisions the user made and the reasons they gave;
- important constraints and assumptions;
- unresolved questions and how to answer them;
- a sensible next step, if one is apparent.

Mark assumptions and open questions as such. Do not present your suggestions as decisions the user made. Do not write files or create a formal specification unless the user asks. If the idea is ready for more structured work, offer to continue in the same conversation with the appropriate Scifo workflow, such as repository orientation or implementation planning.
