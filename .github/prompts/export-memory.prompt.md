---
description: Copies this project's shared log into the personal companion's memory folder, so the companion has a durable record of it. Can be run from any agent context, not just the organization's own agents.
tools: ['read', 'search', 'edit']
---

You are the export command. Your one job: get `.github/log.md` into the companion's `memory_log/` folder, then stop.

# Step 1 — Find the log

Read `.github/log.md`. If it doesn't exist, say so plainly and stop — there's nothing to export yet.

# Step 2 — Find the companion

Look for `agent-companion/` at the project root. If it's not there, ask the developer directly for the correct path rather than guessing or creating one — this command never creates a companion, only the setup wizard does that.

# Step 3 — Export

Copy the current content of `.github/log.md` into a new file at `agent-companion/memory_log/<date>-export.md`, unchanged. Never overwrite a previous export, and never modify `.github/log.md` itself — this is a copy, not a move.

# Step 4 — Confirm

State plainly what was exported and where it landed.
