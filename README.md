# Claude MCPs and Prompts for SEO Blog Automation

Automated SEO blog generation using Claude with MCPs. Includes n8n workflows, prompts, and style guides.

**Results:** 0 → 6,000+ impressions in 30 days with a brand new domain (DR 0).

## What's Included

```
├── workflows/          # n8n MCP server workflows
├── prompts/            # The prompts I use with Claude
└── guides/             # Style guides Claude follows
```

## The Stack

- **Claude.ai** with MCPs (not the API)
- **n8n** for MCP servers
- **Supabase** for posts and keyword tracking
- **Google Search Console** for performance data
- **Google Analytics 4** for traffic data

## Setup

### 1. Import n8n Workflows

Import the JSON files from `/workflows` into your n8n instance:

- `mcp-servers.json` - Main MCP server with all tools
- `subworkflow-search-analytics.json` - GSC search analytics
- `subworkflow-ga4-report.json` - GA4 reports
- `subworkflow-ga4-realtime.json` - GA4 realtime data

### 2. Configure Credentials

Replace these placeholders in `mcp-servers.json`:

- `YOUR_SUPABASE_URL` - Your Supabase project URL
- `YOUR_SUPABASE_SERVICE_KEY` - Your Supabase service role key

Replace in `subworkflow-search-analytics.json`:

- `YOUR_DOMAIN` - Your domain (e.g., `example.com`)

### 3. Set Up OAuth

You'll need to create OAuth credentials for:

- Gmail (for email tools)
- Google Search Console
- Google Analytics 4

### 4. Connect to Claude

Add your n8n MCP server URLs to Claude.ai under Settings → Connectors.

## Usage

### Prompt 1: Setup

Use this at the start of each session to load context:

```
Read /BLOG_WRITING_GUIDE.md and /CLAUDE_CONTEXT.md in the codebase at [YOUR_PATH] to understand blog writing rules, chart types, and submission process. Then check Supabase for existing posts using list_posts or a SQL query. Once you understand everything, say "Ready" and wait for the topic.
```

### Prompt 2: Write a Post

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

## Key Rules from the Style Guide

- **No em dashes** (—) - Instant AI tell
- **H2s as questions** - Matches how people search
- **8-12 visuals per post** - Charts, stat-rows, comparison cards
- **2,500-3,000 words** - Dense, no filler
- **Research before writing** - Every claim needs a source

## Customization

The guides in `/guides` are specific to my setup but show the structure. You'll want to:

1. Update `CLAUDE_CONTEXT.md` with your business info and MCP tools
2. Adjust `BLOG_WRITING_GUIDE.md` for your style preferences
3. Modify the Supabase schema references to match your database

## Questions?

Open an issue or reach out on Reddit (u/[YOUR_USERNAME]).
