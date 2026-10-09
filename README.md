# jiseop-byeon.github.io

Personal homepage, built by GitHub Pages (plain Jekyll, no theme).

The homepage follows the usual PhD-student layout: short bio with photo, a link row, News, and
Selected Publications. Everything shown comes from the files in `_data/`.

## Editing content

| File | What it controls |
| --- | --- |
| `profile.yml` | Name, role, photo, bio paragraphs, and the link row (Email / CV / Google Scholar / GitHub / LinkedIn). `tba: true` on a link shows "(TBA)" instead of a link. |
| `news.yml` | News list, newest first (keep it to about six items) |
| `publications.yml` | Papers: title, authors (your name is bolded automatically), venue, year, links, and `thumb` (the paper's key figure, 480x360 WebP in `assets/images/pubs/`) |
| `research.yml`, `projects.yml` | Research/project entries (currently all hidden) |
| `education.yml`, `honors.yml`, `skills.yml`, `certificates.yml` | Used by the full CV page (see below) |

Any entry with `hidden: true` stays in the file but is left off the site. Delete that line to show it again.

To add a news item, add two lines at the top of `_data/news.yml`:

```yaml
- date: Oct 2026
  text: "[XR-DT](#hrc) presented at **IROS 2026**."
```

## Pages

- `index.html` — homepage
- `cv.html` — `/cv/`, currently a "TBA" placeholder while the CV is revised
- `research.html`, `projects.html` — redirects so old links still work
  (`/research/#arcas` → `/#arcas`, `/research/` → `/#publications`, `/projects/` → `/`)
- `_archive/` — kept in the repo but not published (Jekyll skips folders starting with `_`):
  the full CV page, the Itaewon drawings page, and the previous site's long write-ups. See `_archive/README.md`.
- Layout and styles: `_layouts/default.html`, `assets/css/site.css`

## Images

Originals live in `assets/images/`. The site shows smaller copies:

- `assets/images/pubs/<paper>.webp` — publication figures (480x360)
- `assets/images/web/` — profile photo and other web-sized copies
- Site icon: `assets/images/icons/favicon-32.png`, `favicon-192.png`, plus `apple-touch-icon.png` and `favicon.ico` at the root — all made from `assets/images/profile.jpg`. If you change the photo, regenerate them and bump `?v=` in `_includes/head.html`.

Images of hidden entries are listed under `exclude` in `_config.yml`, so they stay in the repo but are not published.

To make a thumbnail from a new paper figure (Python with Pillow):

```python
from PIL import Image, ImageOps
im = Image.open("figure.png").convert("RGB")
ImageOps.fit(im, (480, 360), Image.LANCZOS).save("assets/images/pubs/new_paper.webp", quality=85)
```

## Preview locally

```bash
bundle install
bundle exec jekyll serve
```

Then open http://127.0.0.1:4000/.
