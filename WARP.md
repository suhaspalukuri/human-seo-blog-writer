# WARP.md

This file provides guidance to WARP (warp.dev) when working with code in this repository.

## What this repo is

This repository is a **Claude Code skill** implemented entirely as Markdown.

The "runtime" artifact is `SKILL.md`: Claude Code reads the YAML frontmatter (name, version, description, allowed-tools) and the prompt/instructions that follow.

`README.md` is for humans: installation, usage, the 24-pattern table, and version history.

## Key files

- **`SKILL.md`** — The skill definition. YAML frontmatter followed by the full writing workflow (6 phases). This is the source of truth for behavior.
- **`README.md`** — Installation instructions, usage examples, pattern reference table, before/after examples.
- **`WARP.md`** — This file. Context for AI-assisted editing.

When changing behavior, edit `SKILL.md` first, then update `README.md` to stay consistent.

## Common commands

### Install the skill into Claude Code

```bash
mkdir -p ~/.claude/skills
git clone https://github.com/yourusername/human-seo-blog-writer.git ~/.claude/skills/human-seo-blog-writer
```

### Manual install (skill file only)

```bash
mkdir -p ~/.claude/skills/human-seo-blog-writer
cp SKILL.md ~/.claude/skills/human-seo-blog-writer/
```

## How to invoke (Claude Code)

```
Write a blog post targeting "best email marketing tools for Shopify"
```

Or for topic-based mode:

```
Write a blog post about email marketing
```

## Architecture

The skill runs a 6-phase workflow:

1. Mode detection (keyword given vs topic only)
2. Requirements gathering (audience, author, word count)
3. Structure selection (5 content patterns)
4. Writing (SEO/GEO rules + 24 humanization rules applied simultaneously)
5. Self-audit (AI-detection check + rewrite)
6. Delivery (meta tags, article, schema, notes)

## Making changes safely

### Versioning

`SKILL.md` has a `version:` field in YAML frontmatter. `README.md` has a Version History section. Update both when bumping the version.

### Editing SKILL.md

- Preserve valid YAML frontmatter formatting and indentation
- The banned word list and 24-pattern list are referenced by both the skill and the README table — keep them in sync
- Hard rules (no em dashes, no images, no graphs) appear at the top of the skill and must not be softened

### What "no em dashes" means for edits

The skill itself must not contain any em dashes in its example "After" text. The "Before" examples may contain them to show what to remove. If you add new before/after examples, check that the After version is clean.

### Adding new patterns

If you add a pattern beyond the current 24, number it sequentially, add it to both the Phase 4 list in `SKILL.md` and the table in `README.md`, and note it in Version History.

### Documenting fixes

If you change the prompt to handle a specific failure mode (e.g., the skill kept producing em dashes in FAQ answers, or kept using "delve into" despite the ban), add a short note to README.md's Version History describing what was fixed and why.
