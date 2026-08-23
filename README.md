# rachelbeecham.dev

Personal portfolio site for Rachel Beecham — AI + business systems, workflow automation, and technical operations. Live at **[rachelbeecham.dev](https://rachelbeecham.dev)**.

## Tech

Static HTML/CSS, no build step, no JavaScript framework. Fonts are loaded from Google Fonts (Bricolage Grotesque, DM Mono, Instrument Serif). Hosted on GitHub Pages with a custom domain via `CNAME`.

## Local preview

No build tooling is required. Open `index.html` directly in a browser, or serve the folder locally:

```bash
python3 -m http.server 8000
# then visit http://localhost:8000
```

## Deployment

Push to the default branch of this repo (`rbeecham1076.github.io`). GitHub Pages serves `index.html` from the repo root automatically at the custom domain configured in `CNAME` (`rachelbeecham.dev`).

## File structure

| File | Purpose |
|---|---|
| `index.html` | The entire site — markup, styles, and content in one file. |
| `robots.txt` | Crawler rules; points crawlers at `sitemap.xml`. |
| `sitemap.xml` | Lists indexable URLs for search engines. Add a `<url>` entry here if a new page is ever published. |
| `CNAME` | GitHub Pages custom-domain config — do not remove. |
| `resume.pdf` | Linked from the hero, résumé/profile card, and contact section. Replace this file (keeping the same name) to update the résumé everywhere at once. |
| `project-screenshot.png` / `project-screenshot.webp` | Screenshot of the AI Customer Inquiry Organizer project. The `<picture>` element in `index.html` serves the WebP to browsers that support it and falls back to the PNG. Regenerate both if the screenshot changes (same dimensions: 1600×1243). |
| `og-image.jpg` | Social preview image (1200×630) used for Open Graph and Twitter Card previews when the link is shared. Generated to match the site's palette/type — regenerate at the same dimensions if the brand identity changes. |

## Updating project content

The featured project (AI Customer Inquiry Organizer) lives inside `<article class="project" id="inquiry-organizer">` in `index.html`. Edit the heading, description paragraphs, principle list, tech chips, and action links directly there — everything is plain HTML, no templating.

To add a second project, duplicate the `.folder` nav entry and the `<article class="project">` block, giving the new article a unique `id` and updating the `.directory-nav` link's `href` to match.

## SEO

- `<title>`, meta description, canonical URL, Open Graph, Twitter Card, and Person JSON-LD structured data are all set in `<head>`.
- `robots.txt` and `sitemap.xml` are at the repo root (required paths for GitHub Pages + custom domain).
- Analytics and search-engine verification are **not yet installed**. See the HTML comment in `<head>` for exactly where to add a real Google Analytics 4 Measurement ID, Google Search Console DNS verification, Bing Webmaster Tools, and Pinterest domain verification once those are set up — never commit a placeholder/fake token.

## Post-deployment checklist (one-time)

1. Add `rachelbeecham.dev` as a Domain property in [Google Search Console](https://search.google.com/search-console) and complete DNS verification.
2. Submit `https://rachelbeecham.dev/sitemap.xml`.
3. Inspect the homepage URL and request indexing.
4. Repeat steps 2–3 for any new page added later.
