# Agent-Companion

**A small, fixed agent organization generated around the real domains in a codebase.**

The distributable starts with only two operational references:

- `.github/copilot-instructions.md` — the organization-wide role, safety, delegation, and reporting contract.
- `.github/prompts/wizard.prompt.md` — the setup and reconciliation workflow.

Run the wizard once in a target project. It inspects the stack, creates the organization, and keeps task-specific work out of persistent agent definitions.

## Organization

### CEO

The CEO is the management-only layer. It plans with the developer, delegates domain work to Managers, reconciles their reports, and flags contradictions. It has no file-editing or execution capability and never calls a Specialist directly.

### Managers

The wizard creates one Manager for each substantial project domain, such as frontend, backend, data, document intelligence, or documentation. Managers own domain boundaries and authoritative glossaries. They never edit project files.

A normal Manager receives a fixed pair:

- **Implementer** — investigates, edits, executes, and validates within a complete task brief.
- **Critical Reviewer** — independently and skeptically checks the implementation, searches for unsupported assumptions and regressions, and reports findings without editing.

A documentation-only Manager receives one documentation Implementer. The Manager performs the acceptance check itself.

### Specialists are stateless

The wizard creates Specialists during setup, not during each task. Their files contain stable role and domain instructions only.

For every invocation, the Manager passes a complete brief containing the task identifier, objective, exact paths, allowed actions, exclusions, definition of done, validation requirements, relevant glossary references, and expected report. When the invocation ends, its purpose is finished. A later task starts a fresh invocation with a fresh brief.

This design:

- Keeps the number of registered agents bounded.
- Avoids mutable task state in agent files.
- Preserves stable prompts for better caching.
- Isolates technical work from the CEO and Manager context windows.
- Makes review an independent verification step rather than self-approval.

Delegated calls still consume tokens and AI credits. The pair primarily improves context isolation, consistency, and quality; it does not guarantee lower total token consumption.

## Cascading configuration

CEO → Manager → Specialist requires nested subagents in VS Code:

`chat.subagents.allowInvocationsFromSubagents`

The wizard explains this requirement and asks whether to enable it in the workspace. If declined, it leaves settings unchanged. The generated organization still supports direct conversations with Managers, and cascading can be enabled later.

VS Code manages automatic conversation compaction. `/compact` remains a user/session command and is not treated as an agent tool.

## Grounding and safety

Each Manager receives a short glossary of current official documentation for its language, framework, major dependencies, and available security advisory sources. Only relevant rows are passed into a Specialist brief.

Agents do not read environment files, credential stores, or live secrets. Implementers stop when correctness requires an unlisted path, action, or decision. Reviewers distinguish verified defects from uncertainty and report evidence before conclusions.

## Project log

The wizard can initialize an append-only project log for durable preferences, decisions, and patterns. Routine task details are excluded.

## Getting started

1. Copy the `.github` folder into the target project root.
2. Open a local agent-capable chat in VS Code.
3. Run `/wizard`.
4. Answer the nested-subagent configuration question.
5. Review the detected domains and generated routing.
6. Talk to the CEO for cross-domain coordination or directly to a Manager for domain work.

## Re-running the wizard

The wizard reconciles missing Managers and fixed Specialists, refreshes wizard-owned routing lists, and preserves the project log and deliberate project-specific content. It does not automatically delete unknown or legacy task-specific agents; those are reported for developer review.
