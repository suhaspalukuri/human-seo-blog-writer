# Human SEO Blog Writer

A Claude Code skill that writes blog posts optimized for Google rankings and AI citations — and actually sounds like a human wrote them.

This skill combines two approaches: SEO/GEO content structure (so posts rank and get cited by ChatGPT, Perplexity, and Claude) and aggressive AI-pattern removal (so the writing doesn't read like it was assembled by a language model).

## Installation

### Recommended (clone directly into Claude Code skills directory)

```bash
mkdir -p ~/.claude/skills
git clone https://github.com/yourusername/human-seo-blog-writer.git ~/.claude/skills/human-seo-blog-writer
```

### Manual install

```bash
mkdir -p ~/.claude/skills/human-seo-blog-writer
cp SKILL.md ~/.claude/skills/human-seo-blog-writer/
```

## Usage

### If you already have a keyword

```
Write a blog post targeting "best email marketing tools for small businesses"

Author: Jane Smith, email marketing consultant, 7 years experience
Audience: Small business owners
Word count: 2,000 words
```

### If you just have a topic

```
Write a blog post about email marketing
```

Claude will suggest 3-5 keyword options, you pick one, and it proceeds.

### Auto-select keyword

```
Write about email marketing — auto select keyword
```

## What this skill does

Six-phase workflow:

1. **Keyword detection** — determines if you gave a keyword or just a topic, and handles each path
2. **Requirements** — collects audience, author credentials, and word count guidance
3. **Structure** — selects a content pattern (guide, how-to, comparison, problem-solution) based on search intent
4. **Write** — applies SEO/GEO rules and humanization rules simultaneously
5. **Self-audit** — runs a two-step AI-detection check and rewrites flagged sections
6. **Deliver** — outputs meta title, meta description, full article, schema markup, and a notes section

## Hard rules (no exceptions)

- No em dashes
- No graphs or images
- No bullet-heavy sections (prose only)
- No AI vocabulary (see banned list in SKILL.md)
- No promotional or significance-inflating language

## SEO/GEO features

- Keyword in H1, first 100 words, H2s, and natural body placement
- Answer-box friendly intro (direct answer in first 2-3 sentences)
- FAQ section with standalone answers for AI citation
- E-E-A-T signals: author bio, real citations, first-person experience
- Internal and external link placeholders
- BlogPosting + FAQPage schema markup (JSON-LD)
- Sentence-case headings throughout

## 24 AI patterns removed

### Content patterns

| # | Pattern | Before | After |
|---|---------|--------|-------|
| 1 | Significance inflation | "marking a pivotal moment in the evolution of..." | State the fact plainly |
| 2 | Notability name-dropping | "cited in NYT, BBC, FT, and The Hindu" | "In a 2024 NYT piece, she argued..." |
| 3 | Superficial -ing phrases | "symbolizing... reflecting... showcasing..." | Remove or rewrite with a real source |
| 4 | Promotional language | "nestled within the breathtaking region" | Plain description |
| 5 | Vague attributions | "Experts believe it plays a crucial role" | "According to a 2019 survey by..." |
| 6 | Formulaic challenges | "Despite challenges... continues to thrive" | Specific facts about actual challenges |

### Language patterns

| # | Pattern | Before | After |
|---|---------|--------|-------|
| 7 | AI vocabulary | "Additionally... testament... landscape..." | Plain alternatives |
| 8 | Copula avoidance | "serves as... features... boasts" | "is... has" |
| 9 | Negative parallelism | "It's not just X, it's Y" | Just say Y |
| 10 | Rule of three | "innovation, inspiration, and insights" | Use the real number |
| 11 | Synonym cycling | "protagonist... central figure... hero" | Repeat the clearest word |
| 12 | False ranges | "from the Big Bang to dark matter" | List the topics directly |

### Style patterns

| # | Pattern | Before | After |
|---|---------|--------|-------|
| 13 | Em dash overuse | "institutions — not the people — yet this..." | Commas or periods |
| 14 | Boldface overuse | "**OKRs**, **KPIs**, **BMC**" | "OKRs, KPIs, BMC" |
| 15 | Inline-header lists | "**Performance:** Performance improved" | Prose sentence |
| 16 | Title case headings | "Strategic Negotiations And Partnerships" | "Strategic negotiations and partnerships" |
| 17 | Emojis | "🚀 Launch Phase: 💡 Key Insight:" | Removed |
| 18 | Curly quotes | smart quotes | straight quotes |

### Communication patterns

| # | Pattern | Before | After |
|---|---------|--------|-------|
| 19 | Chatbot artifacts | "I hope this helps! Let me know if..." | Removed |
| 20 | Cutoff disclaimers | "While details are limited..." | Find a source or remove the claim |
| 21 | Sycophantic tone | "Great question! You're absolutely right!" | Respond directly |

### Filler and hedging

| # | Pattern | Before | After |
|---|---------|--------|-------|
| 22 | Filler phrases | "In order to", "Due to the fact that" | "To", "Because" |
| 23 | Excessive hedging | "could potentially possibly" | "may" |
| 24 | Generic conclusions | "The future looks bright" | Specific fact or next step |

## Before / After example

**Before (AI-sounding):**
> In today's rapidly evolving digital landscape, email marketing serves as a transformative tool for businesses looking to enhance customer engagement and drive meaningful conversions. This comprehensive guide will delve into the pivotal strategies that can help you leverage this powerful channel.

**After:**
> Email marketing still gets a higher return on investment than most channels. The average is around $36 for every dollar spent, though that number varies depending on your list quality and how often you actually send. This guide covers what actually moves that number up.

## Content patterns supported

- **Ultimate Guide** (3,000-5,000 words) — for comprehensive evergreen content
- **How-To Guide** (1,500-2,500 words) — step-by-step process posts
- **Comparison** (2,000-3,000 words) — "X vs Y" and "best X for Y"
- **Problem-Solution** (1,200-2,000 words) — pain-point driven posts
- **Listicle as prose** (1,000-2,500 words) — numbered points written as paragraphs

## References

- [Wikipedia: Signs of AI writing](https://en.wikipedia.org/wiki/Wikipedia:Signs_of_AI_writing) — humanization patterns
- [WikiProject AI Cleanup](https://en.wikipedia.org/wiki/Wikipedia:WikiProject_AI_Cleanup) — pattern source
- SEO/GEO workflow based on the [seo-geo-blog-writer](https://github.com/weipanux/seo-geo-blog-writer) skill by Wei Pan
- Humanization patterns from the [humanizer](https://github.com/blader/humanizer) skill by blader

## Version history

- **1.0.0** — Initial release. Combined SEO/GEO workflow with full humanizer pattern removal. Hard rules: no em dashes, no images, no graphs, prose-only output.

## License

MIT
