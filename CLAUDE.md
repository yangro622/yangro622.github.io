# Personal Website — yangro622.github.io

## Overview

Personal website for Robert Yang (杨天一). Built with Astro, hosted on GitHub Pages. Auto-deploys on push to `main` via GitHub Actions.

**Live URL:** https://yangro622.github.io

## Publishing Workflow

1. Make changes (write content, edit pages, update styles)
2. Verify build passes: `npm run build`
3. Commit and push to `main`
4. GitHub Actions deploys automatically (~30 seconds)

Local dev server: `npm run dev`

## Content

Content lives in `src/content/` as Markdown files with YAML frontmatter.

### Blog Posts — `src/content/blog/`

Filename convention: `slug-like-title.md`

```yaml
---
title: "Post Title"
description: "Brief summary for listing pages and meta tags."
date: 2026-01-15
tags: ["tag1", "tag2"]
draft: false          # set true to hide from listings
---
```

### Projects — `src/content/projects/`

```yaml
---
title: "Project Name"
description: "What this project does."
url: "https://live-url.com"       # optional
repo: "https://github.com/..."    # optional
tags: ["tech1", "tech2"]
order: 1                          # lower = listed first
---
```

## Architecture

```
src/
├── content/           # Markdown content (blog, projects)
├── components/        # Reusable Astro components (Header, Footer)
├── layouts/Base.astro # Shared page layout (head, nav, footer)
├── pages/             # File-based routing
│   ├── index.astro    # Home page
│   ├── blog/          # Blog listing + [id].astro for posts
│   └── projects/      # Project showcase
└── styles/global.css  # Design tokens, base styles, dark mode
```

## Design Principles

- Minimalist — lots of whitespace, restrained color
- Monochrome + blue accent (`--c-accent: #3b82f6`)
- Dark mode via `prefers-color-scheme`
- Max content width: 640px
- Typography: Inter for body, monospace for accents/dates
- Subtle interactions (hover shifts, underline animations)
- Do not add visual clutter — when in doubt, leave it out

## Notes

- Identity: "Robert Yang" for professional context, "杨天一" (Tianyi Yang) for Chinese context
- The "ry." logo in the header uses monospace font + blue dot
- Custom domain not yet configured — good candidates: `tianyiyang.dev`, `robertyang.dev`, `tryang.dev`
