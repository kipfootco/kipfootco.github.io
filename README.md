# Kipfoot Co. GitHub Pages Hub

This repository is the public GitHub Pages hub for Kipfoot Co.

Expected public URL:

```text
https://kipfootco.github.io/
```

## Structure

```text
index.html                 - Public hub landing page
tools/                     - Engineering tools directory
apps/                      - Larger web apps directory
explainers/                - Visual and technical explainers
blog/                      - Updates and writing
design-system/             - Kipfoot design system and prototype package
shared/                    - Shared styles and assets for the hub shell
.github/workflows/         - GitHub Pages deployment workflow
404.html                   - Static fallback page
.nojekyll                  - Disables Jekyll processing
```

The current design-system prototype is intentionally housed under `/design-system/` so the root site can grow into a broader hub for tools, apps, and content.

## Deployment

The included workflow publishes the repository root to GitHub Pages on every push to `main`.

If GitHub Pages is not already active, set the repository Pages source to **GitHub Actions** in repository settings.
