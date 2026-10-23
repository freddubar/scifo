---
name: scifo-share-skill
description: Review a project-local agent skill and copy a reusable, secret-free version into the user's shared Codex skill library.
---

# Share a project skill across repositories

Use when the user asks to make a repository-local skill available in other projects. Ask for the skill path only if it is not provided and cannot be inferred from the repository.

1. Read the specified skill's `SKILL.md` and any referenced files that are needed to understand it. Do not inspect secret registries, `.env` files, credential stores, or authentication files.
2. Check whether its guidance is useful outside the source project. Identify project-specific paths, names, commands, URLs, private context, secrets, or assumptions. Do not copy secret values. Generalize project details only when that can be done without changing the skill's purpose; otherwise tell the user what needs adapting.
3. Copy the complete skill directory to `~/.agents/skills/<skill-name>/`. Preserve required supporting files. Keep the existing skill name when free; if a skill with that name exists, stop and explain the conflict rather than overwriting it. Do not silently invent a new command name.
4. Obtain runtime approval for writes outside the current repository if required. Never bypass filesystem controls.
5. Report the installed path, its resulting skill name, and any project-specific content that should be reviewed before reuse.

Do not modify or delete the source project skill. Do not publish the skill or send it to another person or service.
