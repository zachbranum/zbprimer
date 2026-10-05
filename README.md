# Communication Theory Website (Jekyll + GitHub Pages)

This repository contains a Jekyll site scaffold for a public-facing communication theory project aimed at non-technical audiences.

## What is included

- GitHub Pages-ready Jekyll structure
- Accessible default layout and navigation
- Virginia Tech-inspired maroon/orange visual system
- Home page and six required subpages
- `images/` directory for media assets
- GitHub Actions workflow to build the site on every push to `main`

## Project structure

```text
.
├── .github/workflows/jekyll-build.yml
├── _config.yml
├── _layouts/default.html
├── assets/css/style.css
├── images/
├── index.md
└── pages/
    ├── transmission-view.md
    ├── meaning-and-culture.md
    ├── interpretation-and-power.md
    ├── interpretation-and-intention.md
    ├── reader-guidance.md
    └── how-i-built-this-site.md
```

## Local development

1. Install Ruby (3.1+ recommended).
2. Install dependencies:
   ```bash
   bundle install
   ```
3. Run local server:
   ```bash
   bundle exec jekyll serve
   ```
4. Open `http://127.0.0.1:4000/zbprimer/`.

## Publishing behavior

- Workflow file: `.github/workflows/jekyll-build.yml`
- Trigger: every commit pushed to `main` (plus manual dispatch)
- Build command:
  ```bash
  bundle exec jekyll build --baseurl "${{ steps.pages.outputs.base_path }}"
  ```

## Content authoring guide

You can replace all placeholder text without changing the page structure.

### Editing existing pages

- Home page: `/index.md`
- Subpages: `/pages/*.md`

Each page has front matter like this:

```yaml
---
layout: default
title: Your title
permalink: /pages/your-page/
description: Short summary
---
```

Keep these fields to preserve navigation and page metadata.

### Adding new pages

1. Create a new markdown file in `/pages/`.
2. Add front matter with `layout`, `title`, and `permalink`.
3. Add a link to the new page in `_layouts/default.html` navigation.

### Working with images

1. Put images in `/images/`.
2. Reference them in markdown using:
   ```markdown
   ![Descriptive alt text]({{ '/images/your-image.jpg' | relative_url }})
   ```
3. Always write meaningful alt text for accessibility.

## CSS customization reference

Edit `assets/css/style.css` and adjust variables in `:root`:

- `--vt-maroon`
- `--vt-orange`
- `--vt-smoke`
- `--vt-ink`
- `--vt-white`
- `--vt-link`
- `--vt-link-hover`
- `--vt-focus`
- `--content-max-width`

Recommended process:

1. Update one variable at a time.
2. Reload local preview.
3. Verify contrast (especially text/link/focus colors).

## Accessibility checklist for content edits

- Use headings in order (`h1` → `h2` → `h3`).
- Keep link text descriptive (avoid “click here”).
- Include alt text for every informative image.
- Avoid color-only meaning in diagrams/charts.
- Keep paragraph length moderate for readability.

## Notes

- This scaffold is intentionally content-light so you can add your own graded analysis.
- The structure and workflow are in place; your writing can now be added directly to the existing pages.
