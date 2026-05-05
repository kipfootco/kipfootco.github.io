# Kipfoot Co. Pages Authoring Guide

This repo powers the public Kipfoot Co. GitHub Pages site:

```text
https://kipfootco.github.io/
```

Use this guide as the starting point for adding tools, apps, explainers, blog posts, and design-system updates that should be served through the Pages hub.

## Local Project

Local folder:

```text
C:\Users\wscar\OneDrive\Documents\Projects\GitHub\Reference\kipfootco.github.io
```

GitHub repo:

```text
https://github.com/kipfootco/kipfootco.github.io
```

Primary branch:

```text
main
```

Publishing:

- The repo contains a GitHub Pages workflow at `.github/workflows/pages.yml`.
- Pushing to `main` publishes the repository root to GitHub Pages.
- The live root page is `index.html`.

## Site Structure

```text
index.html                 Public hub landing page
tools/                     Engineering tools directory
apps/                      Larger web apps directory
explainers/                Technical explainers and visual walkthroughs
blog/                      Updates, notes, release posts, and essays
design-system/             Kipfoot design system and prototype package
shared/                    Shared CSS and site-level assets
docs/                      Authoring and repository documentation
404.html                   Static fallback page
.nojekyll                  Prevents Jekyll processing
```

## Content Types

### Tools

Use `tools/` for engineering calculators and focused technical workflows.

Recommended pattern:

```text
tools/
  beam-analysis/
    index.html
```

Each tool page should include:

- Clear engineering scope.
- Inputs with explicit units.
- Results with traceable calculations.
- Assumptions and code references where relevant.
- Links back to `tools/index.html` and the root hub.

### Apps

Use `apps/` for larger browser experiences that are more than a single calculator.

Recommended pattern:

```text
apps/
  project-name/
    index.html
```

Good candidates:

- Multi-step workflows.
- Persistent interactive demos.
- Tools with multiple screens or modes.
- Prototype apps that may later become separate repos.

### Explainers

Use `explainers/` for educational technical content.

Recommended pattern:

```text
explainers/
  topic-name/
    index.html
```

Explainers should favor:

- Visual examples.
- Short sections.
- Engineering assumptions.
- Equations with variables defined.
- Links to related tools.

### Blog

Use `blog/` for updates, release notes, design notes, and development logs.

Recommended pattern:

```text
blog/
  2026-05-04-post-title/
    index.html
```

Use dates in folder names when chronology matters.

### Design System

Use `design-system/` for the Kipfoot visual system, component previews, and UI kit prototypes.

Important entry points:

```text
design-system/index.html
design-system/preview/index.html
design-system/ui_kits/homepage/index.html
design-system/ui_kits/tool-library/index.html
design-system/ui_kits/engineering-tool/index.html
```

## Adding A New Page

1. Pick the right section: `tools`, `apps`, `explainers`, `blog`, or `design-system`.
2. Create a folder with a clear lowercase hyphenated name.
3. Add an `index.html` file inside that folder.
4. Link the new page from the section index.
5. Link the section index from the root hub if it is a major addition.
6. Use relative paths so the page works locally and on GitHub Pages.

Example:

```text
tools/beam-analysis/index.html
```

Link to it from `tools/index.html`:

```html
<a href="beam-analysis/index.html">Beam Analysis</a>
```

From the root page, link with:

```html
<a href="tools/beam-analysis/index.html">Beam Analysis</a>
```

## Styling Guidance

Use the shared site shell for hub-level pages:

```html
<link rel="stylesheet" href="../shared/styles/site.css">
```

Adjust the relative path based on folder depth.

For design-system pages, use the existing design-system tokens:

```html
<link rel="stylesheet" href="colors_and_type.css">
```

or, from nested design-system folders:

```html
<link rel="stylesheet" href="../colors_and_type.css">
```

Keep the interface consistent with Kipfoot:

- Dark-first surfaces.
- Precise engineering language.
- Explicit units.
- Functional technical visuals.
- Compact, readable layouts.
- No decorative filler.

## Assets

Put shared hub assets in:

```text
shared/assets/
```

Put design-system-specific assets in:

```text
design-system/assets/
```

Use relative paths. Avoid absolute filesystem paths inside HTML.

## Publishing Workflow

Common local workflow:

```powershell
cd C:\Users\wscar\OneDrive\Documents\Projects\GitHub\Reference\kipfootco.github.io
git status
git add .
git commit -m "Add new Kipfoot content"
git push origin main
```

After push:

1. GitHub Actions runs `.github/workflows/pages.yml`.
2. GitHub Pages publishes the repo root.
3. The page becomes available under `https://kipfootco.github.io/`.

The Codex GitHub connector now has write access to this repo, so future updates can also be made through the connector when that is the better workflow.

## Preflight Checklist

Before publishing:

- The new page has a reachable `index.html`.
- Local links use relative paths.
- Navigation links back to the section index or root hub.
- Text has no placeholder copy unless intentionally marked as scaffolded.
- Engineering units are explicit.
- Visuals are functional or clearly illustrative.
- The page works at mobile and desktop widths.
- `git status` only shows intentional changes.

## Good Next Content Additions

Useful early additions for this site:

- A real `tools/` directory page with a first tool card set.
- A first explainer connected to the Beam Analysis prototype.
- A short blog post announcing the design-system prototype.
- A content template for tool pages.
- A content template for explainers.
