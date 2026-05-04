# GitHub Pages Deployment Notes

This folder is now structured as a static GitHub Pages site.

## Pages Entry Points

- `index.html` - master design-system hub and default Pages entry.
- `preview/index.html` - component and token gallery index.
- `ui_kits/homepage/index.html` - homepage/app shell prototype.
- `ui_kits/tool-library/index.html` - tool library prototype.
- `ui_kits/engineering-tool/index.html` - Beam Analysis tool prototype.
- `404.html` - simple fallback page.
- `.nojekyll` - prevents Jekyll processing.

## Recommended Publish Options

### Option A: Publish This Folder Directly

Use a GitHub Actions workflow that uploads the contents of `kipfoot` as the Pages artifact. The published site root will serve this folder's `index.html`.

### Option B: Publish From `/docs`

If using GitHub Pages branch settings instead of Actions, copy or move the contents of `kipfoot` into a repository-level `docs` folder, then set Pages to publish from `main` and `/docs`.

### Option C: Make `kipfoot` The Repository Root

If this is a standalone repository for the design system, place these files at the repository root and publish from `main` and `/`.

## Static Site Constraints

- No build step is required.
- External network dependency: Google Fonts.
- All prototype links are relative and should work under a subpath.
- SVG assets are local in `assets/`.
- The UI kit pages currently inline many styles. For a production design-system site, the next cleanup pass should move shared styles into `colors_and_type.css` or a companion site stylesheet.

## Preflight Checklist

- Open `index.html` locally and verify the hub loads.
- Open `preview/index.html` and verify every component preview link resolves.
- Open each `ui_kits/*/index.html` page and verify cross-links work.
- Test at desktop and mobile widths.
- Confirm the Pages source points at the folder containing this `index.html`.
