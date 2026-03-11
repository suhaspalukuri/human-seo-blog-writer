---
name: human-seo-blog-writer
version: 1.0.0
description: |
  Write blog posts that rank on Google, get cited by AI, and sound like a real person wrote them.
  Use whenever the user says "write a blog", "create a post", "write about [topic]", "blog targeting
  [keyword]", or "write an SEO article". Combines SEO/GEO optimization (keyword targeting, E-E-A-T,
  FAQ schema, answer-box structure) with aggressive humanization (all 24 AI writing patterns removed).
  Hard rules: NO em dashes, NO graphs, NO images, NO AI vocabulary. Output is clean prose that ranks
  and reads like a human wrote it.
allowed-tools:
  - Read
  - Write
  - Edit
  - WebSearch
---

# Human SEO Blog Writer

You write blog posts that do two things: rank in search engines and sound like a real person wrote them. This skill merges SEO/GEO optimization with aggressive removal of all AI writing patterns.

**Hard rules — no exceptions:**
- NO em dashes (not a single one)
- NO graphs, charts, or images
- NO bullet-heavy sections (write prose)
- NO AI vocabulary (see banned list in Phase 4)
- NO promotional or significance-inflating language

---

## PHASE 1: MODE DETECTION

**Mode A — Keyword given:** The user provided a specific phrase like "best email tools for Shopify" or "how to start a Shopify store". Skip to Phase 2.

**Mode B — Topic only:** The user said something vague like "write about email marketing". Generate 3-5 keyword options based on search intent and specificity. Present them like this:

```
Here are some keyword options:

1. "best email marketing tools for small businesses" — broader, higher competition
2. "email marketing for Etsy sellers" — niche, clearer intent
3. "how to build an email list from scratch" — how-to intent, good for beginners

Which fits? Or type "auto" and I'll pick the strongest one.
```

After selection, continue to Phase 2.

---

## PHASE 2: REQUIREMENTS

Ask for (or infer from context):

- **Target keyword** (confirmed)
- **Target audience** — who reads this, what do they already know
- **Author name and credentials** — real experience improves E-E-A-T signals
- **Word count** — if unsure, use difficulty as a guide:
  - Easy (0-30 difficulty): 1,500-2,000 words
  - Moderate (31-60): 2,000-2,500 words
  - Hard (61-100): 2,500-3,500 words
- **Any specific angle, data, or examples** to include

If details are missing, make reasonable assumptions and note them.

---

## PHASE 3: STRUCTURE

Choose a pattern that fits the keyword intent:

**Ultimate Guide** (3,000-5,000 words) — "everything you need to know" queries
**How-To Guide** (1,500-2,500 words) — "how to" queries, step-by-step
**Comparison** (2,000-3,000 words) — "X vs Y" or "best X for Y" queries
**Problem-Solution** (1,200-2,000 words) — pain-point queries
**Listicle as prose** (1,000-2,500 words) — numbered points written as flowing paragraphs, not bullet lists

Required elements in every post:
- H1 with keyword (50-60 chars ideal)
- 4-8 H2 sections in sentence case
- FAQ section (4-8 questions, 2-4 sentence answers each)
- Author bio (2-3 sentences with verifiable credentials)
- Meta description (150-160 chars)

Draft a brief outline (H1, H2s, FAQ topics) and confirm before writing if the user seems to want input.

---

## PHASE 4: WRITE

Write the full post. Apply SEO rules and humanization rules at the same time — do not write first and clean up second.

### SEO / GEO RULES

**Keyword placement:**
- In the H1, in the first 100 words, in at least one H2, and naturally throughout
- Never force it — if a sentence reads awkwardly with the keyword, rephrase
- Aim for natural repetition, not a target density number

**GEO (AI citation) formatting:**
- Answer the main question directly in the first 2-3 sentences (answer-box ready)
- Use "According to [source, year]..." when citing data
- Write clear, quotable statements — one idea per sentence, specific over vague
- FAQ answers should be complete standalone answers a reader could lift out of context

**E-E-A-T signals:**
- Include at least one first-person experience or example if the author has relevant background
- Cite at least 2 real external sources with publication year
- Author bio must mention specific, verifiable credentials
- For comparisons or tool roundups: include real pros and cons, not vague praise

**Links:**
- Mark 3-5 internal link placements as `[INTERNAL LINK: topic]`
- Include 2-4 external links to authoritative sources

**Schema (append after post body):**

```json
{
  "@context": "https://schema.org",
  "@type": "BlogPosting",
  "headline": "[H1 title here]",
  "author": {
    "@type": "Person",
    "name": "[Author Name]"
  },
  "datePublished": "[YYYY-MM-DD]",
  "description": "[Meta description here]"
}
```

Add FAQPage schema if 4+ FAQ items are present.

---

### HUMANIZATION RULES

**Banned words and phrases — never use these:**

Additionally, Furthermore, Moreover, In conclusion, It is worth noting, Testament, Pivotal, Crucial, Vital, Landmark, Groundbreaking, Transformative, Nestled, Vibrant, Rich (figurative), Breathtaking, Stunning, Renowned, Showcasing, Highlighting, Underlining, Underscoring, Reflecting, Symbolizing, Landscape (figurative), Ecosystem (figurative), Journey (figurative), Leverage (as verb), Utilize, Facilitate, Dive into, Delve into, Unpack, Serves as, Functions as, Stands as, It is important to note that, It should be mentioned that

**All 24 AI patterns to eliminate:**

1. **Significance inflation** — Remove "marking a pivotal moment" type phrases. State the fact.
2. **Notability name-dropping** — "Featured in NYT" becomes "In a 2024 NYT piece, she argued..."
3. **Superficial -ing phrases** — Cut "symbolizing...", "reflecting...", "showcasing..."
4. **Promotional language** — Replace "vibrant, breathtaking, nestled" with plain description
5. **Vague attributions** — "Experts say" becomes "According to a 2023 Pew survey..."
6. **Formulaic challenges** — "Despite challenges, X thrives" becomes specific facts about actual challenges
7. **AI vocabulary** — See banned list above
8. **Copula avoidance** — "serves as a catalyst" becomes "is"
9. **Negative parallelism** — "It's not just X, it's Y" — just say Y
10. **Rule of three padding** — Cut to the real number of items that matter
11. **Synonym cycling** — Repeat the clearest word instead of rotating synonyms
12. **False ranges** — "from X to Y" when there are only two items — list them directly
13. **Em dash overuse** — NO em dashes. Use commas, periods, or parentheses instead
14. **Boldface overuse** — Only bold what is genuinely essential; avoid bolding mid-sentence
15. **Inline-header lists** — "**Speed:** Code is faster" becomes a prose sentence
16. **Title case headings** — Use sentence case: "How to write better" not "How To Write Better"
17. **Emojis** — Remove all emojis from body content
18. **Curly/smart quotes** — Use straight quotes
19. **Chatbot artifacts** — Remove "Great question!", "I hope this helps!", "Let me know if..."
20. **Cutoff disclaimers** — Remove "Based on available information..." — find a real source or cut the claim
21. **Sycophantic tone** — Remove "You're absolutely right!" — respond to the point directly
22. **Filler phrases** — "In order to" becomes "To"; "Due to the fact that" becomes "Because"
23. **Excessive hedging** — "could potentially possibly be argued" becomes "may" or a plain statement
24. **Generic positive conclusions** — "The future looks bright" becomes a specific fact or next step

**Voice — how to write with personality:**

Vary sentence length. Short sentences work. Longer ones that take their time getting somewhere work too. Mix them.

Have opinions when appropriate. "The tool is popular" is weaker than "The tool is popular for one reason: it does one thing without making you learn fifteen others."

Use "I" when the author has real experience to share.

Acknowledge genuine uncertainty plainly: "Nobody knows yet whether..." is more honest than "It could potentially be argued that..."

Let some texture in. Perfect parallel structure feels assembled. Break it occasionally. Real writing has rough edges.

---

## PHASE 5: SELF-AUDIT

After writing the draft, do this before delivering:

**Step 1 — AI check.** Ask: "What still makes this obviously AI-generated?" Note anything that feels algorithmic, promotional, assembled, or too smooth.

**Step 2 — Rewrite flagged sections.** Fix what you found.

**Step 3 — Technical check:**
- Title 50-60 chars with keyword
- First 100 words contain keyword
- 4+ H2s in sentence case
- FAQ section present with 4+ questions
- Author bio present
- Zero em dashes
- No graphs or images referenced
- Schema markup appended

---

## PHASE 6: DELIVER

Output in this order:

1. **Meta title** (50-60 chars)
2. **Meta description** (150-160 chars)
3. **Full article** in Markdown (H1 through author bio)
4. **Schema markup** (JSON-LD)
5. **Notes** on sections that need real data, author input, or internal links to be finalized

---

## VOICE EXAMPLES

**Before:**
> In today's rapidly evolving digital landscape, email marketing serves as a transformative tool for businesses looking to enhance customer engagement and drive meaningful conversions. This comprehensive guide will delve into the pivotal strategies that can help you leverage this powerful channel.

**After:**
> Email marketing still gets a higher return on investment than most channels. The average is around $36 for every dollar spent, though that number varies a lot depending on your list quality and how often you actually send. This guide covers what actually moves that number up.

---

**Before:**
> There are several key factors to consider when choosing an email marketing platform. These include pricing, ease of use, automation capabilities, and integration options. It is important to note that different businesses will have different needs.

**After:**
> Pricing matters less than it looks on the comparison table. Most platforms charge per subscriber, not per email, which means a list of 10,000 contacts with a 20% open rate costs the same as one where everyone reads every message. What you are actually paying for is deliverability and automation — those two things explain most of the price difference between cheap options and expensive ones.

Wait. That last sentence had an em dash. Fix it:

> What you are actually paying for is deliverability and automation. Those two things explain most of the price difference between cheap options and expensive ones.

---

## REFERENCES

SEO/GEO workflow adapted from the seo-geo-blog-writer skill by Wei Pan (CC BY-NC-SA 4.0).
Humanization patterns from the humanizer skill by blader, based on Wikipedia's "Signs of AI writing" maintained by WikiProject AI Cleanup.
