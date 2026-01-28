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
- Verify template folder is set to `templates`

## How to Add Images to a Post

### Method 1: Drag and Drop (Recommended)

1. Open your post in Obsidian
2. Drag an image file from your file explorer directly into the editor
3. Obsidian will automatically:
   - Copy the image to `assets/images/`
   - Insert the markdown image syntax: `![filename](../assets/images/filename.png)`
4. **Important:** Change the path to absolute format:
   - Change `![filename](../assets/images/filename.png)`
   - To: `![Alt text here](/assets/images/filename.png)`
   - (Remove the `..` and make it start with `/`)

### Method 2: Copy and Paste

1. Copy an image (from browser, screenshot tool, etc.)
2. Paste directly into your Obsidian post (Ctrl+V / Cmd+V)
3. Obsidian will auto-save it to `assets/images/`
4. Fix the path to absolute format (see step 4 above)

### Method 3: Manual Upload

1. Copy your image file to `C:\Users\James\Documents\GitHub\Lasenby.com\assets\images\`
2. In your post, add the markdown:
   ```markdown
   ![Description of image](/assets/images/your-image.png)
   ```

### Image Path Format

**Always use absolute paths starting with `/`:**

✅ Correct:
```markdown
![My photo](/assets/images/photo.jpg)
```

❌ Wrong (relative path won't work on published site):
```markdown
![My photo](../assets/images/photo.jpg)
```

### Example Post with Image

```markdown
---
layout: default
title: My Photo Post
date: 2026-01-27
permalink: /my-photo-post/
---

# My Photo Post

Here's a cool photo I took:

![Beautiful sunset](/assets/images/sunset.jpg)

The photo shows...
```

## How to Publish Using GitHub Desktop

### First-Time Setup

1. **Install GitHub Desktop** (if not already installed)
   - Download from: https://desktop.github.com
2. **Sign in** with your GitHub account
3. **Add repository:**
   - File → Add Local Repository
   - Choose: `C:\Users\James\Documents\GitHub\Lasenby.com`
   - Click "Add Repository"

### Publishing Workflow (Every Time)

#### Step 1: Open GitHub Desktop

1. Launch GitHub Desktop
2. Make sure "Current Repository" shows: **Lasenby.com** (or **jlasenby.github.io**)

#### Step 2: Review Your Changes

1. You'll see a list of changed files on the left:
   - Green `+` = New file
   - Yellow dot = Modified file
   - Red `-` = Deleted file
2. Click on any file to see exactly what changed (right side shows diff)
3. Verify the changes are correct

#### Step 3: Commit Your Changes

1. At the bottom left, you'll see two fields:
   - **Summary** (required): Write a short description of what you did
     - Example: "Add hello world post"
     - Example: "Update about page with new bio"
     - Example: "Add sunset photo to latest post"
   - **Description** (optional): Add more details if needed
2. Click the blue **"Commit to main"** button

#### Step 4: Push to GitHub

1. After committing, click the **"Push origin"** button at the top
   - This uploads your changes to GitHub
   - Your site will automatically rebuild
2. Wait 1-2 minutes for GitHub Pages to publish
3. Visit your site to see the changes live

### Complete Example

**Scenario:** You wrote a new post with an image

1. Open GitHub Desktop
2. You see these changes:
   - `+ _posts/2026-01-27-my-trip.md` (new post)
   - `+ assets/images/beach.jpg` (new image)
3. Summary: `Add post about my beach trip`
4. Click "Commit to main"
5. Click "Push origin"
6. Wait 1-2 minutes
7. Visit: `https://jlasenby.github.io/my-trip/`

### Quick Reference

| Action | What to Do |
|--------|-----------|
| **See what changed** | Open GitHub Desktop |
| **Save changes locally** | Write summary → "Commit to main" |
| **Publish to website** | Click "Push origin" |
| **Undo last commit** | Right-click commit → "Revert this commit" |
| **Check build status** | Visit: https://github.com/jlasenby/jlasenby.github.io/actions |

### Common Commit Messages

Use clear, descriptive commit messages:

- ✅ `Add post about Python tutorial`
- ✅ `Update about page with new contact info`
- ✅ `Fix typo in hello world post`
- ✅ `Add photos to travel post`
- ❌ `Update` (too vague)
- ❌ `Changes` (not descriptive)
- ❌ `asdfasdf` (meaningless)

### Troubleshooting GitHub Desktop

**"Push origin" button is grayed out:**
- No commits to push yet
- Make sure you clicked "Commit to main" first

**Error: "Failed to push":**
- Click "Repository" → "Pull" first
- Then try pushing again

**Don't see your repository:**
- File → Add Local Repository
- Navigate to `C:\Users\James\Documents\GitHub\Lasenby.com`

**Changes not showing up:**
- Make sure you saved your file in Obsidian (Ctrl+S)
- Click "Fetch origin" button to refresh
