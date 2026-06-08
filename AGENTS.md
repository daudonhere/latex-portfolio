# AGENTS.md

## Project overview

Static HTML portfolio for Dade Daud Yusup ("The Theoretical Archive"). Notebook aesthetic - grid background, hand-drawn borders, tape overlays, science formulas as decorative backgrounds.

## Structure

```
index.html        - Main portfolio (7 sections: Header, Abstraction, Skills, Education, Lab Tenure, Published Works, Contact)
experience.html   - Subpage: full Lab Tenure timeline (10 roles)
projects.html     - Subpage: full Published Works grid (9 projects)
assets/
  styles.css      - Notebook theme: grid bg, .tape, .hand-drawn-border, .torn-separator
  script.js       - Empty (placeholder)
  images/
    profile.png   - Profile photo
    favicon.png   - Favicon
    (project screenshots - currently placehold.co URLs)
```

## Tech stack (all CDN, no build step)

- **Tailwind CSS** - via `cdn.tailwindcss.com` script tag
- **Iconify** - `code.iconify.design/iconify-icon/1.0.7/iconify-icon.min.js` for social icons
- **Google Fonts** - Kalam (body), Caveat (formula backgrounds)

## Key conventions

- Each section has **exactly 9 formula spans** (Lab Tenure has 21) in `absolute inset-0` containers with `pointer-events-none select-none font-['Caveat'] leading-none opacity-15`
- Formulas use scattered `top`/`left`/`right` positions, varied `rotate` and font sizes (`text-3xl` to `text-7xl`)
- **No `overflow-hidden`** on formula containers - large text can extend beyond section bounds
- Section IDs: `section-header`, `section-abstraction`, `section-skills`, `section-education`, `section-tenure`, `section-portfolio`, `section-contact`
- Cards use `.hand-drawn-border`, `.tape` overlays, and slight `rotate` for imperfect look
- Skills grid: 6 cards in `grid-cols-1 md:grid-cols-3` layout
- Education: SVG on desktop, stacked cards on mobile
- Repetition of formulas across sections is intentional (background decoration doesn't need to be unique)

## Deployment

- Hosted on **Vercel** at `https://im-using.vercel.app`
- Canonical domain in meta tags and sitemap
- Deploy via Vercel dashboard or CLI (no config files in repo)


## Verification

Open each HTML file in a browser or use a local server:
```sh
python3 -m http.server 8000
# Open http://localhost:8000
```
