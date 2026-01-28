# Zero-to-Launch: Jekyll + Obsidian Digital Garden on GitHub Pages

## Phase 1: The Codebase & Structure

### Directory Structure

```
username.github.io/
├── _layouts/
│   └── default.html
├── _posts/
│   └── (your markdown posts go here)
├── assets/
│   ├── css/
│   │   └── styles.css
│   └── images/
│       └── (your images go here)
├── _config.yml
├── index.html
├── about.md
├── now.md
└── blog.html
```

### File 1: `_config.yml`

```yaml
title: Your Digital Garden
description: A minimal personal site
author: Your Name
email: your.email@example.com

url: "https://username.github.io"
baseurl: ""

permalink: /:title/

markdown: kramdown
kramdown:
  input: GFM
  hard_wrap: false

exclude:
  - .obsidian/
  - README.md
  - Gemfile
  - Gemfile.lock
```

### File 2: `assets/css/styles.css`

```css
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

html {
  font-size: 18px;
}

body {
  background-color: #050505;
  color: #dddddd;
  font-family: 'Courier Prime', 'Courier New', monospace;
  line-height: 1.6;
  padding: 20px;
}

.container {
  max-width: 650px;
  margin: 0 auto;
}

header {
  margin-bottom: 60px;
  padding-bottom: 20px;
  border-bottom: 1px solid #333;
}

h1, h2, h3, h4, h5, h6 {
  color: #ffffff;
  margin-top: 1.5em;
  margin-bottom: 0.5em;
  font-weight: normal;
}

h1 {
  font-size: 2em;
  margin-top: 0;
}

h2 {
  font-size: 1.5em;
}

h3 {
  font-size: 1.2em;
}

a {
  color: #00ff00;
  text-decoration: none;
}

a:hover {
  text-decoration: underline;
}

nav {
  margin-bottom: 40px;
}

nav a {
  margin-right: 20px;
  font-size: 1em;
}

p {
  margin-bottom: 1em;
}

ul, ol {
  margin-bottom: 1em;
  margin-left: 2em;
}

li {
  margin-bottom: 0.5em;
}

code {
  background-color: #0a0a0a;
  padding: 2px 6px;
  border: 1px solid #222;
  font-family: 'Fira Code', 'Courier New', monospace;
  font-size: 0.9em;
}

pre {
  background-color: #0a0a0a;
  border: 1px solid #222;
  padding: 15px;
  overflow-x: auto;
  margin-bottom: 1em;
}

pre code {
  background: none;
  border: none;
  padding: 0;
}

blockquote {
  border-left: 3px solid #00ff00;
  padding-left: 20px;
  margin: 1em 0;
  font-style: italic;
  color: #bbbbbb;
}

img {
  max-width: 100%;
  height: auto;
  display: block;
  margin: 1em 0;
}

hr {
  border: none;
  border-top: 1px solid #333;
  margin: 2em 0;
}

footer {
  margin-top: 80px;
  padding-top: 20px;
  border-top: 1px solid #333;
  font-size: 0.9em;
  color: #888;
}

.post-list {
  list-style: none;
  margin-left: 0;
}

.post-list li {
  margin-bottom: 1.5em;
}

.post-date {
  color: #888;
  font-size: 0.9em;
  margin-right: 10px;
}

.post-meta {
  color: #888;
  font-size: 0.9em;
  margin-bottom: 1em;
}

@media (max-width: 700px) {
  html {
    font-size: 16px;
  }

  body {
    padding: 15px;
  }

  nav a {
    display: block;
    margin-bottom: 10px;
    margin-right: 0;
  }
}
```

### File 3: `_layouts/default.html`

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>{% if page.title %}{{ page.title }} - {{ site.title }}{% else %}{{ site.title }}{% endif %}</title>
  <meta name="description" content="{% if page.description %}{{ page.description }}{% else %}{{ site.description }}{% endif %}">
  <link rel="stylesheet" href="{{ '/assets/css/styles.css' | relative_url }}">
</head>
<body>
  <div class="container">
    <header>
      <h1><a href="{{ '/' | relative_url }}">{{ site.title }}</a></h1>
      <nav>
        <a href="{{ '/' | relative_url }}">Home</a>
        <a href="{{ '/about' | relative_url }}">About</a>
        <a href="{{ '/now' | relative_url }}">Now</a>
        <a href="{{ '/blog' | relative_url }}">Blog</a>
      </nav>
    </header>

    <main>
      {{ content }}
    </main>

    <footer>
      <p>&copy; {{ 'now' | date: "%Y" }} {{ site.author }}. Built with Jekyll.</p>
    </footer>
  </div>
</body>
</html>
```

### File 4: `index.html`

```html
---
layout: default
title: Home
---

<h1>Welcome</h1>

<p>This is my digital garden—a place for ideas, notes, and thinking in public.</p>

<p>I write about technology, learning, and whatever captures my attention.</p>

<h2>Recent Posts</h2>

<ul class="post-list">
{% for post in site.posts limit:5 %}
  <li>
    <span class="post-date">{{ post.date | date: "%Y-%m-%d" }}</span>
    <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
  </li>
{% endfor %}
</ul>

<p><a href="{{ '/blog' | relative_url }}">View all posts →</a></p>
```

### File 5: `blog.html`

```html
---
layout: default
title: Blog
---

<h1>All Posts</h1>

<ul class="post-list">
{% for post in site.posts %}
  <li>
    <span class="post-date">{{ post.date | date: "%Y-%m-%d" }}</span>
    <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
  </li>
{% endfor %}
</ul>
```

### File 6: `about.md`

```markdown
---
layout: default
title: About
permalink: /about/
---

# About

Write your bio here.

## Contact

Email: your.email@example.com
```

### File 7: `now.md`

```markdown
---
layout: default
title: Now
permalink: /now/
---

# What I'm Doing Now

Last updated: {{ 'now' | date: "%B %d, %Y" }}

- Working on...
- Learning...
- Reading...

*This is a [now page](https://nownownow.com/about).*
```

---

## Phase 2: The Obsidian Configuration

### Step 1: Open Repository as Vault

1. Launch Obsidian
2. Click "Open folder as vault"
3. Navigate to your local `username.github.io` folder
4. Select folder and confirm

### Step 2: Disable Wikilinks

1. Open Settings (gear icon)
2. Navigate to **Files & Links**
3. Set "Use [[Wikilinks]]" to **OFF**
4. Confirm links now use standard Markdown format: `[text](path)`

### Step 3: Configure Image Handling

1. In Settings → **Files & Links**
2. Set "Default location for new attachments" to **In subfolder under current folder**
3. Set "Subfolder name" to: `assets/images`
4. When pasting images, they will auto-save to `assets/images/`

### Step 4: Create Front Matter Template

1. Create folder: `.obsidian/templates/`
2. Create file: `.obsidian/templates/post-template.md`

```markdown
---
layout: default
title:
date: {{ date:YYYY-MM-DD }}
permalink: /{{ title | slugify }}/
---

#

```

3. In Settings → **Core plugins** → Enable "Templates"
4. In Settings → **Templates** → Set "Template folder location" to `.obsidian/templates`

### Step 5: Create Posts in Obsidian

When creating a new post:

1. Create file in `_posts/` folder
2. Name format: `YYYY-MM-DD-title-slug.md` (e.g., `2026-01-26-my-first-post.md`)
3. Insert template (Ctrl/Cmd + P → "Insert template")
4. Fill in front matter and write content
5. Use standard Markdown links: `[link text](/path/to/page)`
6. Use relative image paths: `![alt text](/assets/images/image.png)`

---

## Phase 3: Deployment & DNS

### Step 1: Create GitHub Repository

1. Log into GitHub
2. Click "New repository"
3. Name: `username.github.io` (replace `username` with your GitHub username)
4. Set to **Public**
5. Do NOT initialize with README
6. Click "Create repository"

### Step 2: Connect with GitHub Desktop

1. Open GitHub Desktop
2. Click **File** → **Add Local Repository**
3. Click **Choose...** and select your `username.github.io` folder
4. If prompted "This directory does not appear to be a Git repository", click **Create a repository**
5. Confirm the path and click **Create Repository**
6. Click **Publish repository** (top bar)
7. Uncheck "Keep this code private"
8. Click **Publish Repository**

### Step 3: Initial Commit & Push

1. In GitHub Desktop, you should see all files listed as changes
2. In "Summary" field (bottom left), type: `Initial commit`
3. Click **Commit to main**
4. Click **Push origin** (top bar)

### Step 4: Enable GitHub Pages

1. Go to your repository on GitHub.com
2. Click **Settings** tab
3. Scroll to **Pages** section (left sidebar)
4. Under "Source", select **main** branch
5. Click **Save**
6. Site will be live at `https://username.github.io` within 1-2 minutes

### Step 5: Custom Domain Setup (Optional)

#### DNS Configuration (at your domain registrar):

**For apex domain (example.com):**

Add **A Records** pointing to:
```
185.199.108.153
185.199.109.153
185.199.110.153
185.199.111.153
```

**For www subdomain:**

Add **CNAME Record**:
```
www  →  username.github.io
```

#### GitHub Configuration:

1. In repository **Settings** → **Pages**
2. Under "Custom domain", enter: `example.com`
3. Click **Save**
4. Wait for DNS check (may take up to 24 hours)
5. Once verified, check **Enforce HTTPS**

---

## Phase 4: Maintenance SOP

### Publishing Checklist

```markdown
## New Post Workflow

- [ ] Open Obsidian vault
- [ ] Create new file in `_posts/`
- [ ] Name file: `YYYY-MM-DD-title-slug.md`
- [ ] Insert post template (Ctrl/Cmd + P → Templates)
- [ ] Fill in front matter:
  - [ ] title
  - [ ] date (YYYY-MM-DD format)
  - [ ] permalink
- [ ] Write content using standard Markdown
- [ ] Verify links use `[text](path)` format (not wikilinks)
- [ ] Check images are in `/assets/images/`
- [ ] Save file (Ctrl/Cmd + S)
- [ ] Open GitHub Desktop
- [ ] Review changes in left panel
- [ ] Write commit summary (e.g., "Add post: Title")
- [ ] Click "Commit to main"
- [ ] Click "Push origin"
- [ ] Wait 1-2 minutes for GitHub Pages to rebuild
- [ ] Verify post at `https://username.github.io/title-slug/`
```

### Common Commands Reference

| Task | Action |
|------|--------|
| **View local changes** | Open GitHub Desktop |
| **Commit changes** | Summary + "Commit to main" |
| **Publish to site** | Click "Push origin" |
| **Undo last commit** | Right-click commit → "Revert this commit" |
| **Check build status** | GitHub repo → Actions tab |
| **Force rebuild** | Make any change, commit, push |

### Troubleshooting

**Post not appearing:**
- Verify filename format: `YYYY-MM-DD-title.md`
- Check front matter has `layout: default`
- Ensure date is not in the future
- Check GitHub Actions for build errors

**Images broken:**
- Confirm images are in `/assets/images/`
- Use absolute paths: `/assets/images/file.png`
- Verify images were committed and pushed

**Build failures:**
- Check GitHub repo → Actions tab for error details
- Common cause: YAML syntax errors in front matter
- Ensure no wikilinks: `[[link]]` → `[link](path)`

---

## Optional: Color Scheme Variant

To use **blue** instead of green, modify `assets/css/styles.css`:

```css
a {
  color: #0000ff;  /* changed from #00ff00 */
  text-decoration: none;
}

blockquote {
  border-left: 3px solid #0000ff;  /* changed from #00ff00 */
  padding-left: 20px;
  margin: 1em 0;
  font-style: italic;
  color: #bbbbbb;
}
```

Commit and push to apply changes.
