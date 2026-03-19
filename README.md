# Stella Biderman's Website

Source code for [stellabiderman.ai](https://stellabiderman.ai), built with [Hugo](https://gohugo.io) and the PaperMod theme.

## Repository layout

```
content/        ← Markdown pages (papers, talks, bio, research)
static/         ← Files served directly (PDFs, images, favicon)
assets/css/     ← Custom CSS overrides
config.yml      ← Site-wide settings (title, nav, social links, etc.)
archetypes/     ← Templates for new content entries
```

## How to add files

### Replace your CV or profile photo

These files live in `static/` and are referenced by name in `config.yml`:

| File | Purpose |
|------|---------|
| `static/cv.pdf` | CV linked from the social-icon row on the home page |
| `static/picture.jpeg` | Profile photo shown on the home page |

To update either one, simply overwrite the existing file with your new version (keeping the same filename), then commit and push.

### Add a downloadable file (PDF, dataset, slides, …)

1. Place the file in `static/`, e.g. `static/my-paper.pdf`.
2. It will be available at `https://stellabiderman.ai/my-paper.pdf`.
3. Link to it from any Markdown page using the root-relative path: `[Download paper](/my-paper.pdf)`.

### Add a new publication

Each paper lives in its own folder under `content/papers/`:

```
content/papers/
└── my-paper/
    ├── index.md        ← metadata + abstract + citation
    └── my-paper.pdf    ← (optional) local copy of the paper
```

**Steps:**

1. Create a folder: `content/papers/my-paper/`
2. Copy `archetypes/paper.md` into the folder and rename it `index.md`.
3. Fill in the front-matter fields (`title`, `date`, `author`, `description`, `summary`, `tags`) and replace the placeholder body text with your abstract and citation.
4. If you want to host the PDF yourself, place it in the same folder and update the download link in `index.md`. Otherwise link directly to arXiv/DOI.

Example front-matter for a new paper:

```yaml
---
title: "My New Paper"
date: 2024-11-01
tags: ["large language models", "evaluation"]
author: ["Stella Biderman", "Co-Author Name"]
description: "One-sentence description for search engines."
summary: "Two-sentence summary shown on the Publications list page."
editPost:
    URL: "https://arxiv.org/abs/XXXX.XXXXX"
    Text: "arXiv"
---
```

### Add a new talk

Talks are listed under `content/talks/`. Create a new Markdown file there:

```
content/talks/my-talk.md
```

Use the front-matter format from an existing talk or the `archetypes/` templates as a starting point. The `date` field controls sort order on the Talks page.

### Edit the Bio or Research pages

These are single Markdown files:

- `content/bio.md` — Bio page
- `content/research.md` — Research overview page

Open the file, edit the Markdown body, save, and push.

### Update site-wide settings

`config.yml` controls:

- **Profile subtitle** (`params.profileMode.subtitle`) — the intro text on the home page
- **Social icons** (`params.socialIcons`) — links in the icon row (CV, email, Google Scholar, GitHub, Twitter)
- **Navigation menu** (`menu.main`) — top-nav and home-page button links
- **Email address, base URL, site title**

## Local development

Install [Hugo](https://gohugo.io/installation/) (v0.147.2+), then run:

```bash
hugo server
```

The site is available at <http://localhost:1313> and rebuilds automatically on every save.

## Deployment

Push any branch to GitHub. The GitHub Actions workflow (`.github/workflows/hugo.yml`) builds the site with Hugo and deploys it to GitHub Pages automatically.

## License

[MIT License](LICENSE.md)
