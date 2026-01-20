# Claude Context

> **Read this first.** This document contains everything Claude needs to help with your tasks.

> **Note:** This is a template. Customize it with your own business info, MCP tools, and database schema.

## Business Overview

[YOUR BUSINESS NAME] is a [YOUR BUSINESS TYPE]. We help [YOUR TARGET AUDIENCE] with [YOUR VALUE PROPOSITION].

**Services:**
- [Service 1]
- [Service 2]
- [Service 3]

**Website:** [your-domain.com]

---

## Available MCP Tools

### Database (Supabase/Your DB)
| Tool | Description |
|------|-------------|
| `Run SQL` | Execute SELECT queries on the database. Read-only. |
| `Manage Keywords` | Insert, update, or delete keywords in the keywords table. |

### Google Search Console
| Tool | Description |
|------|-------------|
| `Search_Analytics` | Get clicks, impressions, CTR, position. Group by page, query, date. |
| `Inspect_URL` | Check if a specific URL is indexed in Google. |

### Google Analytics 4
| Tool | Description |
|------|-------------|
| `Run_Report` | Get traffic data, sessions, page views, etc. |
| `Run_Realtime_Report` | Get current active users and pages. |

### Gmail (Optional)
| Tool | Description |
|------|-------------|
| `Get_many` | Get emails from inbox with date filters. |
| `Draft_a_Reply` | Create a draft reply to a specific thread. |

### Blog Posts
| Tool | Description |
|------|-------------|
| `list_posts` | List all posts (drafts + published) |
| `create_post` | Create new draft post |
| `update_post` | Update a post |

---

## Database Schema

### posts
- `slug`, `title`, `description`, `content`
- `author`, `tags[]`, `draft`, `published_at`
- `meta_title`, `focus_keyword`
- `charts` - JSON array of chart configurations

### keywords
- `keyword` (unique) - the search term
- `volume` - monthly search volume
- `competition_index` - 0-100, lower is better
- `status` - available, used, rejected
- `used_in_post` - slug of post that used this keyword

---

## Common Tasks

### "Write a blog post"
1. Query existing posts to avoid duplicates
2. Query keywords to find available topics
3. Follow BLOG_WRITING_GUIDE.md for content rules
4. Submit via create_post as draft

### "Check SEO performance"
1. Use Search_Analytics to get clicks/impressions by page
2. Filter for high impressions, low CTR (optimization opportunities)
3. Check what keywords pages are ranking for

### "Find keyword opportunities"
1. Query existing keywords
2. Suggest new keywords based on gaps
3. User checks Google Ads Keyword Planner
4. Analyze CSV for volume ≥5000, competition ≤25

---

## Critical Rules

### Research Before Writing
Always search for stats and studies BEFORE drafting content. Never invent data.

### No Em Dashes
Em dashes (—) are flagged as AI content. Use commas, periods, or parentheses instead.

### H2s as Questions
Every H2 should be phrased as a question users would ask AI assistants.

### Visual Density
Target 8-12 visuals per 2,500 word post. No more than 3-4 paragraphs without a visual.
