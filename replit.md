# Personal Landing Page — Josh Morden

## Overview
A professional single-page landing page for Josh Morden, a Business Analytics and Information Systems student at the University of Iowa. Designed for recruiters and hiring managers to see his technical skills and project work. Built per PRD.md and STANDARDS.md from BAIS:3300 Module 8.

## Project Structure
```
/
├── index.html          # Main landing page (semantic HTML5)
├── css/
│   └── stylesheet.css  # All styles — no inline CSS anywhere
├── images/
│   └── headshot.jpeg   # Profile photo
├── PRD.md              # Product requirements
├── STANDARDS.md        # Technical and design standards
├── Josh_Morden.pdf     # Source resume (not linked on site)
└── README.md
```

## Tech Stack
- Vanilla HTML5 + CSS3 (no frameworks, no JavaScript)
- Inter font from Google Fonts
- Static site — no build step required

## Running the App
Served with Python's built-in HTTP server on port 5000:
```
python3 -m http.server 5000 --bind 0.0.0.0
```

## Deployment
Configured as a static site deployment with the root directory (`.`) as the public directory.

## Design
- Colors: Background `#F8F9FA`, Text `#212529`, Accent teal `#0D6E6E`, Card bg `#E9ECEF`
- Font: Inter (400/500/600/700)
- Max content width: 900px centered
- Fully responsive from 320px; two-column project grid on desktop
- WCAG 2.2 Level AA accessible
