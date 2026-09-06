# Agent-Companion 0.1

**A small organization of agents for your codebase — and one companion that remembers you.**

Drop this into a project. One command reads your stack, builds a team shaped to it, and gets out of the way. No dashboards, no config files to tune, no new vocabulary to learn beyond three job titles you already understand.

---

## 🏢 The organization

- **CEO** — the management layer. No tools that touch a file. It brainstorms with you, and can pull in one or more Managers for their own domain's technical read on a question — then compiles what comes back, flags it if two Managers actually disagree, and can search the web to ground a factual answer.
- **Manager**, one per part of your stack — frontend, backend, data, whatever you actually have. The balanced layer: plans work, creates and delegates to Specialists, and answers the CEO's questions from its own domain knowledge without spinning anyone up just to do that.
- **Specialist** — the technical layer. A real file, not a one-off. The first time a Manager needs one for a task, it creates it; if that same task comes up again later, the same file picks up where it left off instead of starting over.

Nobody skips the chain of command. Nobody edits outside their lane. It's all written down in one file, and every agent reads it before doing anything.

## 🪪 How something worth remembering actually gets logged

Three layers, three ways in — and only two of them can actually write:

- A **Specialist** logs from its own initiative, straight from real implementation work with you.
- A **Manager** logs from its own initiative too, and it's also the one who decides whether something the CEO noticed is actually worth keeping — it can reframe it, build on it, or just let it drop.
- The **CEO** never writes an entry itself. If a brainstorming session turns up something worth remembering, it hands that thought to whichever Manager it actually belongs to. If nothing fits clearly enough to hand off, it's fine for it to just not get saved — not every stray idea from a pure conversation needs a permanent record.

## 🎯 Which one to talk to

The three roles aren't just a hierarchy, they're three different kinds of conversation:

- **CEO — brainstorming and cross-domain thinking.** Think something through, scope out an idea, or ask a question that touches more than one part of your stack — it'll pull in the relevant Managers and give you one compiled answer. Nothing gets built here, and that's the point.
- **Manager — everyday technical work.** Planning a handful of related changes, repetitive updates across similar files, anything at ordinary complexity that a Manager can break down using its own glossary of current docs and hand off cleanly.
- **Manager, for the hard stuff too.** High complexity, precision-sensitive work still starts with that domain's Manager — it's who creates and delegates to a Specialist when a task genuinely needs that level of focus. You don't address a Specialist directly.

Pick the level that matches what you're actually trying to do, not just the one that feels closest to "talking to the app."

## 🧭 Grounded, not guessing

Every domain gets a short glossary — a handful of links to the actual current docs for the language, framework, and key dependencies in play, gathered once when the team is built. Specialists work from those links instead of leaning on memory that might be a version or two behind, and it's also what a Manager answers the CEO's questions from. Where a security-advisory feed exists for your stack, it's in there too — surfaced as a note for you to act on, never acted on quietly.

## 🧠 One companion, remembering on your terms

A personal companion agent lives alongside your project, gitignored, local to you. It doesn't watch every keystroke — it only ever sees what you choose to hand it, when you choose to hand it over, via one explicit export. No background syncing, no silent collection.

## 🚀 Getting started

1. Add this to your project so its files sit at the root, alongside your own.
2. Open an agent-capable chat in your coding assistant of choice.
3. Run the setup command. It scans, builds the team, and reports what it found.
4. Talk to the CEO if you're not sure where to start, or go straight to a Manager if you already know.

That's it. Everything else — how delegation works, what gets logged, how the companion fits in — lives in the project's own rules file, written in plain language, one page you can actually read.

## 📜 License

```
X11 License

Copyright (c) 2026 BLELLETTA Marouan

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL
BLELLETTA MAROUAN BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY,
WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR
IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.

Except as contained in this notice, the name of BLELLETTA Marouan shall not
be used in advertising or otherwise to promote the sale, use or other
dealings in this Software without prior written authorization from
BLELLETTA Marouan.
```
