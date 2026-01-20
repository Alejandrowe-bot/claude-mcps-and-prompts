# Prompt 1: Setup

Use this at the start of each session to load context into Claude.

```
Read /BLOG_WRITING_GUIDE.md and /CLAUDE_CONTEXT.md in the codebase at [YOUR_CODEBASE_PATH] to understand blog writing rules, chart types, and submission process. Then check Supabase for existing posts using list_posts or a SQL query. Once you understand everything, say "Ready" and wait for the topic.
```

## What This Does

1. Loads the blog writing rules (formatting, chart types, visual components)
2. Loads your business context (MCP tools, database schema, workflows)
3. Checks existing posts to avoid duplicate topics
4. Waits for your keyword/topic input

## Customization

Replace `[YOUR_CODEBASE_PATH]` with the actual path to your guides, e.g.:
- `/Users/yourname/Documents/your-project`
- Or wherever you store your BLOG_WRITING_GUIDE.md and CLAUDE_CONTEXT.md
