# Prompt 2: Write a Post

Use this after running Prompt 1 to start the blog writing workflow.

```
Let's write a blog post. Follow BLOG_WRITING_GUIDE.md and this workflow:

1. KEYWORDS: Query all keywords (used + available) and all published posts' focus_keywords. Give me 10 NEW keywords not in Supabase, not similar to existing ones, no DIY signals (software, tools, platform, free, template, tutorial). List each keyword on its own line (no code block) so I can copy them individually. I'll paste back Google Ads CSV.

2. ANALYSIS: From CSV, find best opportunity (vol ≥5000, comp ≤25, YoY growth, buyer intent). Compare with available keywords. VERIFY no cannibalization against used keywords, published titles, and focus_keywords. Present winner. Save other qualifying keywords to Supabase.

3. TITLES: Search top 10 ranking posts for the keyword. Suggest 3 title options merging best patterns. Suggest 3 meta descriptions (150-155 chars, Problem → Value → Qualifier).

4. OUTLINE: H2s as questions, indicate 8-12 visuals, internal links, ROI calculator if relevant.

5. RESEARCH: Search for 5-10 stats/studies. Save URLs. Mandatory before drafting.

6. DRAFT: Submit via create_post with all fields, charts array, 8-12 visuals, internal/external links, 2500-3000 words. Update keyword to 'used'.

Start by querying keywords and posts now.
```

## The Workflow

### Step 1: Keywords
Claude queries your existing keywords and posts, then suggests 10 new keywords. You copy these into Google Ads Keyword Planner and paste back the CSV.

### Step 2: Analysis
Claude analyzes the CSV for:
- Volume ≥ 5,000
- Competition index ≤ 25
- Year-over-year growth
- Buyer intent (not DIY signals)

### Step 3: Titles & Meta
Claude searches top 10 ranking posts for the keyword and suggests titles/descriptions based on what's working.

### Step 4: Outline
H2s phrased as questions (matches AI search queries), planned visuals, internal links.

### Step 5: Research
Claude searches for recent stats and studies. This is mandatory before writing.

### Step 6: Draft
Claude writes the full post with charts/visuals and submits via MCP.

## Customization

Adjust the criteria based on your niche:
- Volume threshold (5,000 might be too high for niche topics)
- Competition index (25 is conservative, you might go higher)
- Word count (2,500-3,000 works for SEO, adjust for your needs)
