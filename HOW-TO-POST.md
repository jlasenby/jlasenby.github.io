# How to Create a New Post

## Quick Steps

1. **Open Obsidian** to the Lasenby.com vault
2. **Create new file** in `_posts/` folder
3. **Name the file:** `YYYY-MM-DD-title-slug.md` (e.g., `2026-01-27-my-first-post.md`)
4. **Insert template:** Press `Ctrl+P` (or `Cmd+P` on Mac) → type "template" → select "Insert template" → choose "post-template"
5. **Fill in front matter:**
   - `title:` Add your post title
   - `date:` Auto-filled with today's date
   - `permalink:` Replace `{{title}}` with URL-friendly slug (e.g., `/my-first-post/`)
6. **Write your content** below the `#` heading
7. **Save** (Ctrl+S / Cmd+S)
8. **Publish:** Open GitHub Desktop → Commit → Push

## First-Time Obsidian Setup

If you haven't configured Obsidian yet:

1. **Open Obsidian** → Settings (gear icon)
2. **Files & Links:**
   - Turn OFF "Use [[Wikilinks]]"
   - Set "Default location for new attachments" to: **In subfolder under current folder**
   - Set "Subfolder name" to: `assets/images`
3. **Core Plugins:**
   - Enable "Templates"
4. **Templates Settings:**
   - Set "Template folder location" to: `.obsidian/templates`

## Example Post

**Filename:** `_posts/2026-01-27-hello-world.md`

```markdown
---
layout: default
title: Hello World
date: 2026-01-27
permalink: /hello-world/
---

# Hello World

This is my first post.

## A Subheading

Some more content here.

- List item 1
- List item 2

[Link to another page](/about/)
```

## Tips

- **File naming:** The date in the filename must match the date in the front matter
- **Permalinks:** Keep them short, lowercase, use hyphens (not spaces)
- **Images:** Paste directly into Obsidian and they'll auto-save to `assets/images/`
- **Links:** Use standard markdown `[text](/path/)` not wikilinks `[[page]]`
- **Preview:** Your site rebuilds automatically within 1-2 minutes after pushing to GitHub

## Troubleshooting

**Post doesn't appear on site:**
- Check filename format: `YYYY-MM-DD-title.md`
- Verify front matter has all required fields
- Ensure date is not in the future
- Check GitHub Actions tab for build errors

**Template not working:**
- Make sure Templates plugin is enabled in Obsidian settings
- Verify template folder is set to `.obsidian/templates`
