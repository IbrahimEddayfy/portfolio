# Ibrahim Eddayfy — Portfolio

A fast, accessible portfolio website for **Ibrahim Eddayfy**, an SEO & WordPress specialist. The site is built as a static website with plain HTML, CSS, and vanilla JavaScript — there is no build step, framework, or runtime dependency.

**Live site:** https://ibrahimeddayfy.github.io/portfolio/

## Highlights

- Responsive single-page portfolio with dedicated blog articles
- SEO foundations: canonical URLs, Open Graph and Twitter Card metadata, JSON-LD `Person` schema, `robots.txt`, and `sitemap.xml`
- Performance-focused static delivery with no third-party scripts
- Contact options via Gmail compose, phone, WhatsApp, and LinkedIn
- Content Security Policy (CSP) and `rel="noopener noreferrer"` on external links

## Project structure

```text
.
├── index.html                  # Main portfolio page
├── 404.html                    # Custom not-found page
├── style.css                   # Site styles
├── script.js                   # Smooth-scroll behavior
├── blog/
│   ├── whos-ibrahim-eddayfy.html
│   ├── seo-mistakes.html
│   ├── web-design-trends.html
│   ├── wordpress-performance.html
│   └── images/                 # Blog cover images
├── images/                     # Site images
├── favicon.png
├── og-image.png
├── robots.txt
├── sitemap.xml
├── .nojekyll                   # Disables Jekyll processing on GitHub Pages
└── .github/
    └── workflows/
        └── static.yml          # GitHub Pages deployment workflow
```

## Run locally

Because the project is fully static, no installation or build command is required.

### Option 1 — Open the file directly

Open `index.html` in a browser.

### Option 2 — Serve over HTTP (recommended)

Serving the directory over HTTP matches production behavior more closely.

Using Python (already available on most systems):

```bash
python -m http.server 8000
```

Then open http://localhost:8000.

Using Node.js:

```bash
npx serve .
```

> Some browsers restrict certain features when pages are opened via `file://`. Serving over HTTP avoids those differences.

## Deployment

The site is deployed automatically to **GitHub Pages** through `.github/workflows/static.yml`.

- **Trigger:** every push to the `main` branch, plus manual runs via **Actions → Deploy static content to Pages → Run workflow**
- **Steps:** checkout the repository, configure GitHub Pages, upload the repository root as the Pages artifact, and deploy
- **Permissions:** the workflow uses least-privilege GitHub token permissions (`contents: read`, `pages: write`, `id-token: write`) required for Pages deployment
- **Concurrency:** only one Pages deployment runs at a time

No manual build artifact is committed; the deployed output is the repository content itself.

## Security practices

- A Content Security Policy is defined in the page `<head>` to restrict resource loading to the site's own origin.
- External links opened in a new tab use `rel="noopener noreferrer"`.
- The deployment workflow requests only the permissions needed to publish to GitHub Pages.
- Workflow actions are pinned to full, immutable commit SHAs.
- No secrets, tokens, or credentials are stored in the repository.

## Contributing

This is a personal portfolio project. Changes are made directly on branches and deployed from `main`.

## Contact

- Website: https://ibrahimeddayfy.github.io/portfolio/
- LinkedIn: https://www.linkedin.com/in/brahim-eddayfy-webdev-seo-wp-cybersecurity/

## License

All rights reserved. No license or permission to reuse, modify, or redistribute this project is granted.
