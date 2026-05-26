# Waymaster Website

Jekyll site for [waymaster.com](https://waymaster.com).

## Quick Start

### Prerequisites
- Ruby 3.x
- Bundler (`gem install bundler`)

### Run locally
```bash
bundle install
bundle exec jekyll serve
# Open http://localhost:4000
```

---

## How to Add Content

### New Blog Post

Create a file in `_posts/` named `YYYY-MM-DD-your-title.md`:

```markdown
---
layout: post
title: "Your Post Title"
date: 2025-06-01
category: software        # software | mercedes | vw | general
summary: "One or two sentences shown on listing pages."
---

Your post content in Markdown here.

## Subheading

More content...
```

**Categories and their URLs:**
| category | URL |
|----------|-----|
| `software` | `/blog/software/your-title/` |
| `mercedes` | `/blog/mercedes/your-title/` |
| `vw` | `/blog/vw/your-title/` |
| `general` | `/blog/general/your-title/` |

---

### New Dev Log Entry

Create a file in `_devlog/` named `YYYY-MM-DD-your-title.md`:

```markdown
---
layout: devlog
title: "Short technical update title"
date: 2025-06-01
version: "v0.2"           # optional version tag
summary: "One sentence summary."
---

Dev log content here. Keep it concise — this is the short-form technical log.
```

URL will be: `/devlog/2025/06/your-title/`

---

### Update a Vehicle Page

Edit the relevant file in `_vehicles/`:
- `_vehicles/mercedes-560-sec.md`
- `_vehicles/vw-t25-westfalia.md`

Update the `specs:` list in the front matter to change the stat table, and edit the Markdown body for the description.

---

## Deploying to GitHub Pages

### First time setup

1. Create a repo named `waymaster.com` (or any name) on GitHub
2. Push this folder to it
3. Go to **Settings → Pages**
4. Set Source to **GitHub Actions**
5. The workflow in `.github/workflows/jekyll.yml` handles the rest

### Every update after that

```bash
git add .
git commit -m "New post: your title"
git push
```

GitHub Actions will build and deploy automatically. Live in ~60 seconds.

### Custom domain (waymaster.com)

1. Add a file called `CNAME` to the root containing just: `waymaster.com`
2. In your DNS provider, add:
   - `A` record: `@` → `185.199.108.153` (and .109, .110, .111)
   - `CNAME` record: `www` → `your-username.github.io`
3. In GitHub Pages settings, enter `waymaster.com` as the custom domain and enable HTTPS

---

## Site Structure

```
waymaster/
├── _config.yml          # Site settings
├── _layouts/            # Page templates
├── _includes/           # Reusable partials (sidebar etc)
├── _posts/              # Blog posts (YYYY-MM-DD-title.md)
├── _devlog/             # Dev log entries
├── _vehicles/           # Vehicle pages
├── assets/css/main.css  # All styles
├── index.html           # Homepage
├── about.md
├── features.md
├── blog/                # Blog index + category indexes
├── devlog/              # Dev log index
└── vehicles/            # Vehicles index
```
