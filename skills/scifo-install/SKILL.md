---
name: scifo-install
description: Install or update Scifo's Codex instructions, agents, and skills in the current user's home directories from the Scifo source repository.
---

# Install Scifo for this Codex user

Use this skill only when the user asks to install or update Scifo. The source repository is the checkout containing this skill. This is a file-copy workflow, not an application installer.

## Destinations

- Append the contents of the source root `AGENTS.md` to `~/.codex/AGENTS.md` inside a clearly marked `<!-- BEGIN SCIFO -->` / `<!-- END SCIFO -->` block.
- Copy each source `.codex/agents/*.toml` to `~/.codex/agents/` with the same filename.
- Copy each source `skills/scifo-*/` directory to `~/.agents/skills/` with the same directory name.

Create destination directories if they do not exist. Do not install `.codex/config.toml` globally; leave the user's Codex configuration unchanged. Do not copy the secret example or any local secret registry.

## Safe install and update procedure

1. Confirm the current repository is the Scifo source checkout by checking for its `README.md`, `AGENTS.md`, `.codex/agents/`, and `skills/scifo-install/SKILL.md`. If these are absent, ask for the Scifo source path.
2. Read the source instructions, agent TOMLs, and skill files. Do not read `.scifo/secrets.local.md`, `.env` files, authentication files, or any credential store.
3. Inspect only the destination files needed to determine whether Scifo is already installed and whether names conflict. Never print unrelated global instruction contents to the user.
4. For `~/.codex/AGENTS.md`: if absent, create it with the marked Scifo block. If present with no Scifo markers, preserve its contents and append the block, separated by a blank line. If both markers exist once in the correct order, replace only the text between them and preserve all surrounding content. If markers are duplicated, unmatched, or malformed, stop and explain the conflict without changing the file.
5. For each destination agent or skill: if absent, copy it. If present and byte-for-byte identical to the source, leave it. If present and appears Scifo-owned, show the path and ask before replacing it unless the user explicitly requested an update. If present with unknown content, stop on that item and ask; never overwrite or merge blindly. Continue only with other conflict-free destinations if useful, and clearly report any skipped items.
6. Make the requested copies using the available file tools. These destinations are outside the project, so obtain runtime approval if required. Do not use shell tricks to bypass filesystem controls.
7. Summarize installed, updated, unchanged, and skipped paths. Tell the user to restart Codex to load changed global instructions and agents.

An explicit “update Scifo” request authorizes replacing files that are clearly Scifo-owned, including the marked instructions block. It does not authorize overwriting unknown files or resolving malformed markers.

## Login and use

Scifo uses the user's existing Codex login. If the user is not signed in, direct them to run `codex login`; never ask them to share credentials. Once installed, the user can start Codex in any repository. Project-specific instructions and skills remain in that repository and take precedence for its local conventions.
