# Scifo

Scifo is a small, file-based coding-agent buddy. Its main agent orchestrates repository work and delegates bounded code changes to specialist agents. The first version targets Codex; the workflows are written so a Claude adapter can be added later.

## Install Scifo once for your Codex user

1. Install Codex and sign in with `codex login`. Check the active session with `codex login status`.
2. Open this Scifo repository in Codex. The source skill lives at `skills/scifo-install/SKILL.md`, so ask Codex: “Read `skills/scifo-install/SKILL.md` and follow it to install Scifo for this user.”
3. Review and approve the requested writes to your Codex user directories. The installer adds Scifo's core instructions to `~/.codex/AGENTS.md`, its agents to `~/.codex/agents/`, and its skills to `~/.agents/skills/`.
4. Restart Codex so it loads the new global instructions, agents, and skills.

After that, use Codex in any project as usual. Scifo's global instructions and skills are available there without copying the kit into each repository. Run `$scifo-install` from any repository to update the installed files from this source checkout.

The installer keeps existing global instructions, adds or updates only a marked Scifo section, and stops if an agent or skill destination already exists with content it cannot identify as Scifo-owned. It does not change `~/.codex/config.toml` by default. Codex's normal login is the sign-in mechanism; Scifo has no separate account.

## Working with Scifo

For a clear implementation request, describe the change and Scifo will inspect the repository, plan internally, and proceed within the requested scope. It does not require a separate recap or plan approval. If you are exploring an idea or asking for a plan only, Scifo will stop at the plan and ask whether you want implementation. It will ask mid-work only when a material decision or scope change needs your input.

Use `$scifo-shape-and-plan` when an early coding idea needs clarification before repository work. For general, non-coding idea pressure-testing, `$scifo-grill-me` is an explicit opt-in. Native Plan mode is optional and must be invoked manually when desired.

## Optional project context

Use project-local instructions only when a repository has conventions or architecture that should not follow you to other projects. Start with [`templates/project/AGENTS.md`](templates/project/AGENTS.md), merge relevant content into that repository's `AGENTS.md`, and fill in the project facts. Keep shared Scifo behavior in your user-level files and project facts in the project repository.

Project-specific skills can live in that repository's `.agents/skills/`. To reuse a useful skill in other projects, ask Scifo to follow `$scifo-share-skill` and provide the skill directory. It checks that the skill is generic and contains no project secrets, then adds it to `~/.agents/skills/` under a distinct name.

## What is installed

- `AGENTS.md`: orchestration, communication, and safety instructions.
- `.codex/agents/`: researcher, implementer, and reviewer role definitions.
- `skills/`: opt-in general idea clarification, coding idea shaping and implementation planning, repository orientation, implementation, debugging, code review, installation, and skill sharing workflows.
- `.scifo/secrets.example.md`: a safe template for recording environment variable names and purposes.

Scifo's secret registry is for human reference and records names and purposes only. Never put real values in Scifo files, prompts, chat, logs, or command output. Keep them in environment variables or a secret manager. Scifo must not read `.scifo/secrets.local.md`.

## Delegation model

Scifo owns understanding, planning, routing, review synthesis, and the final response. It delegates target-project edits to `scifo_implementer`. `scifo_researcher` investigates without editing, and `scifo_reviewer` independently checks meaningful completed changes. These are behavior instructions, not separate security permissions: Codex subagents inherit the parent session's tools and sandbox. Configure parent permissions deliberately and inspect changes before accepting them.

Scifo asks before destructive actions, external side effects, publishing, deployment, credential use, or out-of-scope changes. Routine repository work can proceed without interruption.

## Maintenance

Keep `AGENTS.md` concise and each skill focused. Do not add application code or a setup script to this kit. The installer and share workflows are instructions that Codex follows with the user's approval for writes outside the current repository.
