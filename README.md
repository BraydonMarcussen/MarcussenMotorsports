# Marcussen Motorsports — Metrik

The public Metrik product website at https://marcussenmotorsports.com/.

## Publishing

GitHub Pages publishes the root of `main`. This repository contains the generated static release; no server process or build on GitHub is required. `CNAME` preserves the custom domain, and `.nojekyll` lets Pages serve the `_next` assets unchanged.

The September 10, 2026 update uses the supplied Marcussen Motorsports M/checkered-flag brandmark as the website favicon, with a navy SVG backdrop and PNG/ICO fallbacks. The separate gradient app icon is not the website favicon. Sharper 1800×2250 PC animation frames, the existing 900×1125 phone frames, first-scroll loading improvements, and corrected ultrawide and assembly framing remain included. The completed gauge animation, phone layout refinements, app previews, and privacy, terms, and refund pages remain included. Support launch remains inactive until the campaign URL is supplied; direct checkout is not enabled.

The website source project generates this release with `node scripts/build.mjs`, then `node scripts/prepare-github-pages.mjs <empty-output-directory>`. That packaging step includes the active render assets and adds directory index files for the policy routes. Keep the source project separately; do not hand-edit generated bundles.

Desktop animation now has a 1.5GB budget for its estimated working set:76 decoded full-resolution frames, up to2 in-flight decodes, the96MiB compressed cache and128MiB rendering reserve. It looks up to60 source frames ahead and14 behind, with4 background downloads plus4 foreground slots. This is an animation budget, not a cap on browser-wide or GPU memory. Phones and touch-only tablets retain the smaller12-frame cache. The loader also retains a usable late frame without repeatedly decoding and evicting it. Image resolution and scroll timing are unchanged.

The previous racing-team site is preserved in Git history at `7215189f6f2b721584268ce377f17a77948365fc`. Its original images, videos, styles, and scripts are retained in this repository.

The approved trimmed-frame update removes invisible padding from all840 desktop and840 phone frames and restores their original positions during drawing. Logical resolution, screen overlays, dimensions and scroll timing stay the same. Decoded pixel storage falls74.3% on desktop and73.7% on phones; frame downloads fall10.3% and6.2%, respectively. Exports retain the previous quality settings, use stronger WebP encoding and preserve transparency exactly. Original full-frame assets remain available at `?frames=original` for comparison; the default loads the trimmed sequence. The existing76/12-frame cache capacities remain unchanged, and the desktop budget remains conservatively based on full-size images. These are asset-size measurements, not a browser FPS guarantee.
