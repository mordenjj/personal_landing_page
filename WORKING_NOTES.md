# Working Notes — Josh Morden Personal Landing Page

> **Internal document — not intended for public audiences.**
> This file is for developer and AI assistant reference only. Update it at the end of every working session before closing the project.

---

## How to Use This File (For AI Assistants)

1. Read this entire file before suggesting any changes or writing any code.
2. Read `README.md` for the public-facing project description and feature list.
3. Read `PRD.md` for the product requirements and content spec. Read `STANDARDS.md` for all technical and design rules that govern every file.
4. Do not change the folder structure or file naming conventions without discussing it first.
5. Follow every convention listed in the Conventions section below exactly — do not improvise alternatives.
6. Do not suggest any approach listed in the "What Was Tried and Rejected" section.
7. Ask clarifying questions before making large structural changes (e.g., adding JavaScript, splitting into multiple pages, changing the color palette).
8. This project is AI-assisted (Replit Agent / Claude). Refactor conservatively — prefer targeted edits over rewrites. Do not restructure working code unless explicitly asked.

---

## Current State

**Last Updated:** 2026-03-11

This is a complete, deployed static personal landing page. All required PRD sections are built and styled. The page is live on Replit and serves correctly via Python's built-in HTTP server. The color palette was updated from teal to an earthy red/tan/gold scheme after initial delivery. No JavaScript has been added. No known rendering bugs exist in tested browsers.

### What Is Working
- [x] Sticky navigation bar with anchor links (About, Skills, Projects, Contact)
- [x] Hero section — circular headshot, name H1, tagline
- [x] About/Bio section with real resume content
- [x] Skills section — technical pill tags (earthy red) and methodology pill tags (outlined)
- [x] Three project cards in a two-column responsive grid
- [x] Contact section — LinkedIn, GitHub, and university email badges
- [x] Earthy red / tan / gold color palette applied throughout
- [x] Fully responsive layout (tested at 320 px, 375 px, 768 px, 1280 px)
- [x] WCAG 2.2 Level AA: semantic HTML5, heading hierarchy, alt text, keyboard nav
- [x] External links open in new tab with `rel="noopener noreferrer"`
- [x] `README.md` complete with all 16 sections
- [x] Replit workflow configured — Python HTTP server on port 5000
- [x] Static deployment configured in `.replit`

### What Is Partially Built
- [ ] `STANDARDS.md` — Section 1 (Project Overview) and the color/font table rows are still template placeholder text; they were not filled in by the author before the coding sessions began

### What Is Not Started
- [ ] Favicon — no `.ico` or SVG favicon exists; browser tab shows default icon
- [ ] GitHub links on project cards — all three projects lack live repository URLs
- [ ] Dark mode — no `prefers-color-scheme: dark` media query exists
- [ ] LICENSE file — README references `LICENSE` but the file has not been created

---

## Current Task

**What I was working on when I last stopped:** The `WORKING_NOTES.md` file was just generated as an internal reference document. Prior to that, `README.md` was generated covering all 16 required sections. Before that, the color palette was changed from teal to earthy red (`#8B3626`), warm tan (`#F7F0E3`), and gold (`#B8922A`) across `css/stylesheet.css`.

**The very next step is:** Create a `LICENSE` file in the repository root containing the MIT License text so the link in `README.md` is not broken.

---

## Architecture and Tech Stack

| Technology | Version | Why It Was Chosen |
|---|---|---|
| HTML5 | Living standard | Required by `STANDARDS.md`; semantic elements needed for WCAG compliance |
| CSS3 | Living standard | Required by `STANDARDS.md`; no framework rule means vanilla CSS only |
| Inter (Google Fonts) | Variable | Clean, professional, highly legible sans-serif; fits the "professional but approachable" tone in `STANDARDS.md` |
| Python `http.server` | 3.x (system) | Zero-dependency static file server available in Replit environment without installing anything; development only |
| shields.io | N/A (CDN) | Standard README badge service; no account or API key required |

---

## Project Structure Notes

```
personal_landing_page/
├── index.html                # Entire site — single HTML file per STANDARDS.md
├── css/
│   └── stylesheet.css        # All styles — no inline CSS, no <style> tags anywhere
├── images/
│   └── headshot.jpeg         # Must stay at this path — index.html references it as images/headshot.jpeg
├── PRD.md                    # Product requirements — authoritative source for content decisions
├── STANDARDS.md              # Technical/design rules — authoritative source for code decisions
├── README.md                 # Public-facing project documentation
├── WORKING_NOTES.md          # This file
├── Josh_Morden.pdf           # Source resume — do NOT link to or embed this on the site (STANDARDS.md rule)
├── replit.md                 # Replit Agent memory file — update after architectural changes
└── .replit                   # Replit workflow and deployment config — do not edit manually
```

**Non-obvious decisions:**
- `css/` is a subfolder (not `stylesheet.css` in the root) because `STANDARDS.md` explicitly defines this folder structure.
- There is no `js/` folder or `scripts.js` — `STANDARDS.md` specifies "no JavaScript" for this project. Do not create these files.
- `Josh_Morden.pdf` is in the root because it was uploaded to the repository directly. It must never be linked or embedded on the site.

**Files that must not be changed without discussion:**
- `PRD.md` — product source of truth
- `STANDARDS.md` — design/technical source of truth
- `images/headshot.jpeg` — path is hardcoded in `index.html`; renaming breaks the image

---

## Data / Database

This project has no persistent data, no database, and no flat data files. All content is hardcoded in `index.html` from the author's resume (`Josh_Morden.pdf`) and `PRD.md`. There is no server-side rendering, no API, and no dynamic content.

---

## Conventions

### Naming Conventions
- HTML file: `index.html` (lowercase, root only)
- CSS file: `css/stylesheet.css` (lowercase, inside `css/` subfolder)
- Image files: lowercase with no spaces (e.g., `headshot.jpeg`)
- CSS class names: BEM-style — block (`site-nav`), element (`site-nav__inner`), modifier (`tag--technical`)
- CSS custom properties: `--color-*` prefix for colors, `--font` for font stack, descriptive names

### Code Style
- 2-space indentation throughout HTML and CSS
- All CSS custom properties defined in `:root` at the top of the stylesheet
- No inline `style=""` attributes anywhere in HTML — zero exceptions
- No `<style>` tags in any HTML file — zero exceptions
- Semantic HTML5 elements used for structure; `<div>` and `<span>` only for non-semantic grouping
- All external links include `target="_blank" rel="noopener noreferrer"`
- All `<img>` elements have a descriptive `alt` attribute
- Heading hierarchy is strict: `<h1>` → `<h2>` → `<h3>`, no levels skipped

### Git Commit Message Style
- Imperative mood, sentence case: `Add contact section badges`
- No period at the end
- Keep subject line under 72 characters

---

## Decisions and Tradeoffs

- **No JavaScript:** Required by `STANDARDS.md` ("Static site — no JavaScript"). Do not suggest adding JS for animations, a hamburger menu, or any other purpose without first updating `STANDARDS.md`.
- **Single `index.html` file:** Required by `STANDARDS.md`. Do not suggest splitting into multiple pages or adding a router.
- **Python `http.server` for development:** Chosen because Replit provides Python 3 without any installation steps. This is a development-only server — the deployment target is configured as a static site.
- **Inter from Google Fonts:** Chosen over system fonts for consistent cross-browser rendering and professional appearance. The `<link rel="preconnect">` tags are included to minimize render-blocking.
- **Earthy red / tan / gold palette:** Chosen by the author after the initial teal palette was delivered. The three core variables are `--color-accent: #8B3626`, `--color-bg: #F7F0E3`, and `--color-gold: #B8922A`. Do not change these without being explicitly asked.
- **BEM-style CSS class names:** Chosen for readability and to prevent accidental style collisions as the stylesheet grows. Established from the start — do not switch to utility classes or rename existing classes.
- **Three projects from PRD only:** The resume contains four projects. The PRD specifies exactly three. The NYC Bike Ride project was deliberately excluded. Do not add it without the author's instruction.

---

## What Was Tried and Rejected

- **Teal color palette (`#0D6E6E`):** Was the initial accent color. Rejected by the author in favor of earthy red/tan/gold. Do not suggest reverting to teal.
- **Placeholder/Lorem ipsum text:** Was never used — all content came from the real resume and PRD from the first build. Do not suggest placeholder text as a starting point.

---

## Known Issues and Workarounds

- **Missing favicon:** The browser console logs a 404 for a favicon on every page load. No workaround is in place — this is a cosmetic issue only and does not affect functionality. A favicon file can be added to the root and referenced in `<head>` when desired.
- **`STANDARDS.md` has unfilled template placeholders:** Section 1 (Project Overview) and the color/font rows in Section 3 still contain template instruction text (e.g., "[2–3 sentences describing…]"). This does not affect the site — `STANDARDS.md` is a reference document, not rendered content. No workaround needed; the author should fill these in manually.
- **No GitHub links on project cards:** The three project cards have no external links because the underlying repositories are not public. This is intentional, not a bug. When repositories are made public, `<a>` tags can be added to each `.project-card__title`.

---

## Browser / Environment Compatibility

| Browser | Status |
|---|---|
| Chrome (latest) | Tested — renders correctly |
| Firefox (latest) | Expected to work — no known incompatibilities |
| Safari (latest) | Expected to work — no known incompatibilities |
| Mobile Chrome / Safari (375 px+) | Tested via screenshot — single-column layout correct |

**Environment:**
- Platform: Replit (NixOS, stable-25_05 channel)
- Runtime: Python 3 (system-provided, used for `http.server` only)
- No Node.js, npm, or build tools are used or required

---

## Open Questions

- Should a `LICENSE` file be added to the repository root to resolve the broken link in `README.md`?
- Should GitHub repository links be added to the project cards once the underlying repos are made public?
- Should `STANDARDS.md` be updated by the author to fill in the remaining placeholder sections before the next coding session?
- Is a hamburger/collapsible mobile nav needed, or is the current horizontal nav at small widths acceptable?

---

## Session Log

### 2026-03-11
- Set up Replit workflow — Python HTTP server on port 5000, static deployment configured
- Built complete `index.html` and `css/stylesheet.css` from scratch using real resume, PRD, and STANDARDS content
- Implemented all five required PRD sections: Hero, Bio, Skills, Projects, Contact
- WCAG 2.2 Level AA compliance verified (semantic HTML, alt text, heading hierarchy, keyboard nav, contrast)
- Author requested color change from teal to earthy red/tan/gold — applied across all CSS variables and hardcoded values
- Generated `README.md` with all 16 required sections
- Generated `WORKING_NOTES.md` (this file)
- Left incomplete: LICENSE file, favicon, GitHub links on project cards
- Next step when resuming: create `LICENSE` file in repository root

---

## Useful References

- [MDN HTML5 element reference](https://developer.mozilla.org/en-US/docs/Web/HTML/Element) — semantic element usage
- [MDN CSS custom properties](https://developer.mozilla.org/en-US/docs/Web/CSS/Using_CSS_custom_properties) — CSS variable syntax
- [WCAG 2.2 Quick Reference](https://www.w3.org/WAI/WCAG22/quickref/) — accessibility compliance checklist
- [WebAIM Contrast Checker](https://webaim.org/resources/contrastchecker/) — verify color contrast ratios
- [Google Fonts — Inter](https://fonts.google.com/specimen/Inter) — font import and weight documentation
- [shields.io](https://shields.io/) — badge URL builder for README badges
- [BEM methodology](https://getbem.com/naming/) — CSS class naming convention used in this project
- AI assistance: Replit Agent (powered by Claude) was used to generate the initial `index.html`, `css/stylesheet.css`, `README.md`, and this `WORKING_NOTES.md`. All output was reviewed and approved by the author. The author made all content and design decisions; the AI implemented them.
