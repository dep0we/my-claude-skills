# Notion Bookmark Skill

This skill helps create bookmarks in Notion databases.

## When to Use

Invoke this skill when the user asks to:
- Save a URL to Notion
- Create a bookmark
- Add a link to their bookmarks database

## Instructions

When creating a Notion bookmark:

1. **Fetch the database schema first** using the Notion MCP search/fetch tools
2. **Extract metadata** from the URL (title, description if possible)
3. **Always include**:
   - URL (required)
   - Date Added (use current date in YYYY-MM-DD format)
   - Tags/Category (ask user if not specified)
   - Brief summary or title
4. **Verify all required properties** from the schema are populated
5. **Confirm** the entry was created successfully

## Example Workflow

```
User: "Save this URL to my bookmarks: https://example.com"

1. Search for bookmarks database in Notion
2. Fetch the database schema
3. Create page with properties:
   - URL: https://example.com
   - Date Added: [current date]
   - Tags: [ask user or infer]
   - Title: [extract from page or ask]
4. Verify creation
```

## Allowed Tools

- mcp__notion__search
- mcp__notion__fetch
- mcp__notion__notion-create-pages
