# Marcussen Motorsports — Metrik

The public Metrik product website at https://marcussenmotorsports.com/.

## Publishing

GitHub Pages publishes the root of `main`. This repository contains the generated static release; no server process or build on GitHub is required. `CNAME` preserves the custom domain, and `.nojekyll` lets Pages serve the `_next` assets unchanged.

The September 8, 2026 release includes the completed gauge animation, phone layout refinements, app previews, and privacy, terms, and refund pages. Support launch remains inactive until the campaign URL is supplied; direct checkout is not enabled.

The website source project generates this release with `node scripts/build.mjs`, then `node scripts/prepare-github-pages.mjs <empty-output-directory>`. That packaging step includes the active render assets and adds directory index files for the policy routes. Keep the source project separately; do not hand-edit generated bundles.

The previous racing-team site is preserved in Git history at `7215189f6f2b721584268ce377f17a77948365fc`. Its original images, videos, styles, and scripts are retained in this repository.
