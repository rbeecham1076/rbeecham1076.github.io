# rachelbeecham.dev

Personal portfolio site for Rachel Beecham — AI + business systems, workflow automation, and technical operations. Live at **[rachelbeecham.dev](https://rachelbeecham.dev)**.

## Tech

Static HTML/CSS, no build step, no JavaScript framework. Fonts are loaded from Google Fonts (Bricolage Grotesque, DM Mono, Fraunces). Hosted on GitHub Pages with a custom domain via `CNAME`. Three pages: `index.html` (home), `raydar.html` (Raydar case study), `resume.html` (web résumé) — each is self-contained (its own `<style>` block) rather than sharing a stylesheet, matching the no-build-step approach.

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
| `index.html` | The home page — markup, styles, and content in one file. |
| `raydar.html` | Raydar flagship case study — problem, system, scoring, human-in-the-loop, public/private boundary. Uses only public-safe facts (the public `raydar-demo` repo/README); never pulls from the private `sunnie-ray-trend-ops` data. |
| `resume.html` | Web/HTML résumé, kept in sync with `resume.pdf`. Update both when experience or projects change. |
| `robots.txt` | Crawler rules; points crawlers at `sitemap.xml`. |
| `sitemap.xml` | Lists indexable URLs for search engines. Add a `<url>` entry here if a new page is ever published. |
| `CNAME` | GitHub Pages custom-domain config — do not remove. |
| `resume.pdf` | Linked from the hero, résumé page, and contact section. Replace this file (keeping the same name) to update the downloadable résumé; update `resume.html` to match. |
| `project-screenshot.png` / `project-screenshot.webp` | Screenshot of the AI Customer Inquiry Organizer project. The `<picture>` element in `index.html` serves the WebP to browsers that support it and falls back to the PNG. Regenerate both if the screenshot changes (same dimensions: 1600×1243). |
| `og-image.jpg` | Social preview image (1200×630) used for Open Graph and Twitter Card previews when the link is shared. Generated to match the site's palette/type — regenerate at the same dimensions if the brand identity changes. |

## Updating project content

Work has two projects in `index.html`: `<article class="project" id="inquiry-organizer">` and `<article class="project" id="raydar">` (the latter is a summary card — the full write-up lives in `raydar.html`). Edit headings, description paragraphs, principle lists, tech chips, and action links directly — everything is plain HTML, no templating.

To add a third project, duplicate the `.folder` nav entry and a `<article class="project">` block, giving it a unique `id` and matching `.directory-nav` `href`.

`#design-intelligence` in `index.html` is a separate, non-project editorial section (currently a "coming soon" state) — don't merge future project write-ups into it, and don't pull from the private `sunnie-ray-trend-ops` folder to populate it.

## SEO

- `<title>`, meta description, canonical URL, Open Graph, Twitter Card, and Person JSON-LD structured data are all set in `<head>`.
- `robots.txt` and `sitemap.xml` are at the repo root (required paths for GitHub Pages + custom domain).
- Analytics and search-engine verification are **not yet installed**. See the HTML comment in `<head>` for exactly where to add a real Google Analytics 4 Measurement ID, Google Search Console DNS verification, Bing Webmaster Tools, and Pinterest domain verification once those are set up — never commit a placeholder/fake token.

## Post-deployment checklist (one-time)

1. Add `rachelbeecham.dev` as a Domain property in [Google Search Console](https://search.google.com/search-console) and complete DNS verification.
2. Submit `https://rachelbeecham.dev/sitemap.xml`.
3. Inspect the homepage URL and request indexing.
4. Repeat steps 2–3 for any new page added later.
