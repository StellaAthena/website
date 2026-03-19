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

All publications are stored in a single CSV spreadsheet at `assets/publications.csv`. The Publications page is generated automatically from this file at build time — no Markdown files are needed.

#### CSV columns

| Column | Description |
|---|---|
| `year` | Four-digit publication year (used for grouping and sorting) |
| `authors` | Author string exactly as it should appear on the page |
| `title` | Paper title |
| `venue` | Conference or journal name (rendered in italics) |
| `paper_url` | URL for the **[Paper]** link — leave blank if none |
| `artifacts_url` | URL for the **[Artifacts]** link — leave blank if none |
| `code_url` | URL for the **[Code]** link — leave blank if none |
| `models_url` | URL for the **[Models]** link — leave blank if none |
| `slides_url` | URL for the **[Slides]** link — leave blank if none |
| `talk_url` | URL for the **[Talk]** link — leave blank if none |

**Steps:**

1. Open `assets/publications.csv`.
2. Add a new row for the paper. Quote any field that contains a comma (e.g. the `authors` field).
3. Leave URL columns empty for links that do not exist.
4. Commit and push — the Publications page updates automatically on next build.

Example row:

```
2025,"Smith, Jones, and Biderman","My New Paper","International Conference on Machine Learning (ICML)",https://arxiv.org/abs/XXXX.XXXXX,,,,,
```

> **Note:** "Biderman" is automatically rendered in bold wherever it appears in the `authors` field. Authors with equal contribution are indicated with `*` directly in the author string (e.g. `Smith* and Jones*`).

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
