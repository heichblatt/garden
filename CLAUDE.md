# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with content in this digital garden.

---

## What This Garden Is

A **digital garden**—a space for thinking in public and exploring ideas as they develop. This is not a blog (which is chronological) nor a static portfolio, but a networked collection of thoughts that grows and evolves over time.

The garden is fundamentally self-referential: it uses writing to explore writing, uses note-taking to explore note-taking, and uses digital gardening to think about digital gardening. It is simultaneously a tool and an argument for its own existence.

### Core Themes

- **Writing is thinking** — writing generates ideas; it's not recording existing thoughts but creating new ones
- **Knowledge management** — exploring different frameworks (Zettelkasten, Seeds/Trees/Fruits, epistemic status)
- **The digital garden concept** — its intellectual lineage and theory
- **Creation vs. consumption** — the tension between producing and consuming, collecting and thinking
- **Public thinking** — deliberately thinking in public to create feedback loops and external accountability
- **AI and human collaboration** — how humans and AI can work together, with clear boundaries

---

## The Author's Rules for This Garden

These rules (from [Garden Rules](./content/Garden%20Rules.md)) are non-negotiable guidelines for what gets added here:

1. **Density over quantity** — state your thoughts clearly and concisely; don't pad
2. **Link out, don't copy** — link to others' explanations rather than regurgitating them; only explain what you need to express your distinct thought
3. **Always produce** — the goal is always new content; keep creation/consumption balanced
4. **Epistemic status** — all notes use the seedling/budding/evergreen taxonomy (from Maggie Appleton) to indicate maturity:
   - **Seedling**: Early-stage, rough thought
   - **Budding**: Developed but still evolving
   - **Evergreen**: Mature, relatively stable idea
5. **Connectedness is value** — a note is only useful insofar as it links to and from other notes; the garden's worth lies in its networked structure
6. **Notes progress toward essays** — seedlings mature into budding notes, which eventually become essays

---

## AI and Authorship

The garden has a **firm rule on AI** (see [No AI in the Garden](./content/No%20AI%20in%20the%20Garden.md)):

> Use it to think and write but never let it think or write for you.
> It can be an assistant, never an author.

This means:

- Claude may help brainstorm, clarify thinking, or improve phrasing of existing thoughts
- Claude may not generate or author content for the garden
- The final thought, position, and authorship must be human
- If Claude assists, this should be transparent in the process

---

## Note Structure

Notes follow a loose convention:

- **Frontmatter**: At minimum, include `epistemic-status: seedling|budding|evergreen`
- **Content**: Sparse, dense prose. Start with a clear statement of the thought. Use blockquotes for external attributions.
- **Links**: Use `[[wikilink]]` syntax to link to other notes. Backlinks are automatically generated.
- **External references**: Link out to sources rather than explaining them

Example opening:

```
---
epistemic-status: budding
---

The core assertion: [your thought in one sentence].

[Attribution or blockquote]

[Links to related notes and external sources]
```

---

## Common Patterns in This Garden

- **Thinking through opposition** — many notes explore tensions (e.g., Stream vs Garden, Consumption vs Creation, Stock and Flow)
- **Philosophical grounding** — ideas are connected to intellectual history and referenced thinkers (Vannevar Bush, Luhmann, Maggie Appleton, etc.)
- **Multi-language thinking** — some notes appear in German; the author thinks in multiple languages
- **Impulses as inbox** — [Impulses.md](./content/Impulses.md) is a public scratchpad for half-formed thoughts and questions

---

## Writing Style

- **Analytical and self-aware** — the voice is reflective but not personal
- **Workspace, not blog** — this reads as a thinking tool made public, not a published work
- **Minimal storytelling** — ideas are presented directly; personal anecdotes are rare
- **Functional sparseness** — every sentence should serve a purpose

---

## Quick Start: Local Building

Quartz is the static site generator; it's upstream scaffolding. To preview the garden locally:

```bash
npm run quartz build --serve
# Opens the site at http://localhost:3000
```

To create a new note:

```bash
npm run quartz create path/to/your/note
```

Then edit the resulting file in `content/`. The site hot-reloads.

**Type check and format before committing:**

```bash
npm run check  # catches type errors and formatting issues
```

---

## References

- [Digital Garden](./content/Digital%20Garden.md) — the garden's founding concept
- [Seeds, Trees and Fruits](./content/Seeds,%20Trees%20and%20Fruits.md) — the maturity model for notes
- [Think in Public](./content/Think%20in%20Public.md) — why this is public
- [AI Engagement Patterns](./content/AI%20Engagement%20Patterns.md) — taxonomy of human-AI collaboration patterns

## Tools & Workflows

- [[review-uncommitted]] — skill for reviewing staging area before commits
