# Scifo

Scifo is a small, file-based coding-agent kit. Its main agent orchestrates work and delegates code edits to a specialist. The first version targets Codex; its skills are portable so a Claude adapter can be added later.

## What is included

- `AGENTS.md`: Scifo's orchestration, communication, and safety instructions.
- `.codex/agents/`: researcher, implementer, and reviewer role definitions.
- `.codex/config.toml`: enables Codex subagents with a small concurrency cap.
- `skills/`: portable repo orientation, code implementation, debugging, and code review workflows. Copy these into the target repository's `.agents/skills/` directory.
- `.scifo/secrets.example.md`: a safe template for recording secret variable names and purposes.

## Use Scifo in a project

1. Install and sign in to Codex. For ChatGPT sign-in, run `codex login` and complete the browser flow. Check the current session with `codex login status`.
2. Copy Scifo's `AGENTS.md` guidance into the target repository's root `AGENTS.md`. If that file already exists, merge the Scifo sections into it and preserve project-specific instructions.
3. Copy the contents of `skills/` into the target repository's `.agents/skills/` directory.
4. Copy `.codex/agents/` into the target repository's `.codex/agents/` directory. Merge the `[agents]` settings from `.codex/config.toml` into an existing project config rather than replacing it.
5. Copy `.scifo/secrets.example.md` to `.scifo/secrets.local.md` if you want a local variable-name registry. Add `.scifo/secrets.local.md` to the target repository's `.gitignore`.
6. Open the target repository in Codex and trust it when prompted so its project-scoped Codex files can load. Start with a small request such as: “Have Scifo map this repository and summarize its conventions.”

Scifo's secret registry contains names and purposes only. Put real values in environment variables or a secret manager; never paste them into Scifo files, prompts, chat, logs, or command output. The registry is for the human maintainer and Scifo is instructed not to read it.

## Delegation model

Scifo owns understanding, planning, routing, review synthesis, and the final response. It delegates target-project edits to `scifo_implementer`. `scifo_researcher` investigates without editing, and `scifo_reviewer` independently checks meaningful completed changes. These are behavior instructions, not separate security permissions: Codex subagents inherit the parent session's tools and sandbox. Configure the parent session's permissions for the repository and inspect changes before accepting them.

Scifo asks before destructive actions, external side effects, publishing, deployment, credential use, or out-of-scope changes. Routine repository work can proceed without interruption.

## Maintenance

Keep `AGENTS.md` concise, and keep each skill focused on one workflow. Update the README's copy steps when the file layout changes. Do not add application code or a setup script to this kit.
