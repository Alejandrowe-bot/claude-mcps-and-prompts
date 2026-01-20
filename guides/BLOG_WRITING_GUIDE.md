# Blog Writing Guide

This guide contains everything you need to write SEO-optimized blog posts.

> **Note:** This is a template based on the actual guide used to generate 6k+ impressions in 30 days. Customize it for your own setup.

---

## ⚠️ ABSOLUTE RULE: NO EM DASHES

**Em dashes (—) are strictly forbidden in all posts.** They are flagged as AI-generated content and will be rejected.

Use commas, periods, colons, or parentheses instead.

---

## Quick Start

1. Read this guide completely before starting
2. Check existing posts via your database or CMS
3. Follow the content rules below
4. Submit posts as drafts for review

**Before submitting, verify:**
- [ ] No H1 (`#`) in content (title is displayed separately)
- [ ] `charts` array exists and contains all referenced charts
- [ ] Every `{{chart:N}}` marker has a corresponding chart at index N
- [ ] No em dashes (—)
- [ ] External links have full URLs

---

## Critical Rules

### Meta Descriptions

Meta descriptions are your pitch to get clicks. They should make readers curious, not just inform them.

**Length:**
- Target: 150-155 characters (hard max: 160)
- Front-load the hook in the first 120 characters (mobile cutoff)

**Structure: Problem → Value → Qualifier**

1. **Lead with the problem/pain point** (what hurts)
2. **Promise specific value** (what they'll learn)
3. **Add a qualifier** (why this is different/credible)

**Examples:**

❌ Bad:
`Learn about business automation, ROI calculation, and implementation strategies for enterprises looking to automate processes.`

✅ Good:
`Most automation projects fail in the first 90 days. The ones that succeed share three things that have nothing to do with the technology.`

### Never Use Em Dashes

Instead of em dashes, use:
- Commas for parenthetical information
- Periods to split into separate sentences
- Colons to introduce lists or explanations
- Parentheses for asides

❌ `The automation saved 40 hours per week — a significant improvement.`
✅ `The automation saved 40 hours per week, a significant improvement.`

---

## Content Structure

### No H1 in Content
**NEVER start content with `# Title`.** The title is already displayed at the top of the page.

### Length & Density
- Target: 2,500-3,000 words
- Every paragraph delivers value, no filler

### H2 Formatting (Critical for AI Search)

Every H2 must be phrased as a question users would ask ChatGPT/Claude/Perplexity.

❌ `Automation Cost Savings`
✅ `How much can automation save my business?`

Immediately after each H2: 1-2 sentences giving a direct, factual answer with stats/studies when available.

### Research & Authority (MANDATORY)

**⚠️ CRITICAL: Research BEFORE writing, not after.**

Before drafting any content:
1. Use web search to find 5-10 relevant statistics, studies, and data points
2. Save the URLs of sources you'll cite
3. Only then start writing, weaving in the research naturally

**External links are required:**
- Every post must include external links to sources backing up claims
- Link to the actual source page (not just the domain)
- Never invent data or statistics

---

## Charts & Visual Components

Posts should include **8-12 visuals** for a 2,500 word post (roughly 1 visual per 200-250 words).

Use `{{chart:N}}` markers in content where visuals should appear.

### Available Chart Types

- **Line Chart** - trends over time
- **Area Chart** - like line but filled
- **Bar Chart** - comparing categories
- **Pie Chart** - proportions of a whole
- **Radar Chart** - comparing multiple variables (max 2 series)
- **Scatter Chart** - correlation between variables
- **Funnel Chart** - conversion stages

### Visual Components

- **Stat Row** - animated numbers (great for opening)
- **Callout** - colored boxes for tips/warnings (max 2-3 per post)
- **Process Flow** - step-by-step diagrams (3-5 steps)
- **Quote** - pull quotes for key insights
- **Comparison Card** - before/after comparisons
- **Metric Bars** - horizontal progress bars

### Chart JSON Example

```json
{
  "type": "bar",
  "title": "Processing Time by Method",
  "data": [
    { "method": "Manual", "hours": 45 },
    { "method": "Automated", "hours": 5 }
  ],
  "xKey": "method",
  "yKey": "hours"
}
```

### Visual Distribution

- Opening visual immediately after intro
- 1-2 visuals per major H2 section
- Process diagram for any step-by-step explanation
- Comparison card for any before/after content
- No more than 3-4 paragraphs without a visual

---

## Keywords

**Keyword criteria:**
- Volume ≥ 5,000 monthly searches
- Competition index ≤ 25
- Buyer intent (targets decision-makers, not DIY builders)

**Reject DIY-signal keywords containing:**
- "software", "tools", "platform" (DIYers looking for tools)
- "free", "template", "tutorial" (low buyer intent)
- "how to build", "open source" (DIYers)

**Keyword workflow:**
1. Query existing keywords to avoid duplicates
2. Suggest 10 NEW keywords not similar to existing ones
3. Check Google Ads Keyword Planner for volume/competition
4. Pick best candidate based on volume, competition, YoY growth
5. Save qualifying keywords for future use

---

## Post JSON Structure

```json
{
  "title": "How to Automate Invoice Processing: A Complete Guide",
  "slug": "automate-invoice-processing-guide",
  "description": "Learn how to automate invoice processing to save 15+ hours per week.",
  "meta_title": "Automate Invoice Processing: Save 15+ Hours/Week",
  "focus_keyword": "automate invoice processing",
  "author": "Your Name",
  "tags": ["automation", "invoicing", "finance"],
  "content": "Your markdown content here with {{chart:0}} markers...",
  "charts": [
    {
      "type": "bar",
      "title": "Time Savings",
      "data": [...],
      "xKey": "process",
      "yKey": "hours"
    }
  ]
}
```

---

## Content Tightening Principles

**Convert formats for scannability:**
- Bullet lists → Tables (when comparing options)
- Text explanations → Process diagrams
- Before/after lists → Comparison cards
- Stats in prose → Stat-rows

**Cut redundancy:**
- Remove paragraphs that say the same thing multiple ways
- Cut "setup" sentences ("Let's explore...", "It's worth noting...")
- Trim sections that don't match search intent

**Tighten H2s:**
- ❌ "What is data entry automation and how does it work?"
- ✅ "What is data entry automation?"
