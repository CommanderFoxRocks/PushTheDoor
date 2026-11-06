# Tracker: Local Roadmap (Studio-first)

Work for this game is tracked as **markdown planning files**, not code. The game's Luau and instances live in the Roblox cloud experience (edited through Studio MCP) — this folder only holds the roadmap, PRDs, slices, and design briefs. Best for solo devs working in Studio without a Git remote. This is the default.

## Layout

- `ROADMAP.md` at the root is the human-readable index of slices, using the pack's checkbox convention:
  - `[ ]` not started
  - `[~]` built and tested in Studio, awaiting human approval
  - `[x]` built, playtested, and explicitly approved (append the approval date)
- One feature per directory: `roadmap/<feature-slug>/`
  - PRD: `roadmap/<feature-slug>/PRD.md`
  - Slices: `roadmap/<feature-slug>/slices/NN-<slug>.md`, numbered from `01`
- Triage state is a `Status:` line near the top of each slice file (see `triage-labels.md` for the role strings).
- Comments/decisions append to the bottom of the slice file under a `## Notes` heading.

## When a skill says "publish to the tracker"

Create the file under `roadmap/<feature-slug>/` (creating the directory if needed) and add a matching checkbox line to `ROADMAP.md`.

## When a skill says "fetch the item"

Read the referenced file (the user usually passes the path or slice number), or the matching line in `ROADMAP.md`.

## Backup to GitHub

This folder is a clone of the **public** repo https://github.com/CommanderFoxRocks/PushTheDoor (branch `main`). Git is used only to back up and version the planning files above. It is not the issue tracker and not the game's source.

- Commit only planning artifacts: `ROADMAP.md`, `roadmap/`, `design/`, `docs/`, `CLAUDE.md`, and `.claude/skills/`.
- Never commit game code or Studio exports (`.rbxl`, `.rbxlx`, `.rbxm`, `.rbxmx`, Rojo `src/` trees). `.gitignore` blocks the common ones.
- The repo is public: don't put secrets, API keys, or private player data in any planning file.
- Commit and push only when the user asks.
