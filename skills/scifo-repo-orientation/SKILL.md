---
name: scifo-repo-orientation
description: Map an unfamiliar code repository before making changes. Use when asked to explain a project, find entry points, identify conventions, or prepare a focused implementation plan.
---

1. Read the applicable `AGENTS.md` and project documentation before exploring.
2. Identify the language, frameworks, package boundaries, application entry points, and relevant data flow using focused searches and file reads.
3. Find existing conventions and the commands the project documents for building, testing, linting, or running locally. Do not run commands unless the task calls for them.
4. Ground conclusions in file paths and symbols. Distinguish observed facts from inferences and call out material unknowns.
5. Return a compact map of the relevant areas, suggested files to inspect next, and a likely work plan. Do not change files as part of orientation.

Never inspect secret values or authentication files while mapping a repository.
