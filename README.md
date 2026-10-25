# Edviora Acadamy — Website

A single-page, responsive, SEO-ready website for Edviora Acadamy, built with **HTML5 and CSS3 only**. There is no JavaScript, no framework and no build step.

## Project structure

```
index.html                 The full single-page website
css/style.css              All styles (design tokens at the top)
assets/images/             Logo files, icons, share image and SVG illustrations
  edviora-logo.png           Full logo, navy on transparent
  edviora-logo-white.png     Full logo, white (used on the dark footer)
  edviora-logo-compact.png   Logo without the tagline (used in the header)
  favicon.png / apple-touch-icon.png   Browser and phone icons from the "ED" block
  edviora-academy-share.png  1200×630 social share image
  source/edviora-logo-original.jpg     Original logo as supplied
robots.txt                 Crawler rules (contains a placeholder domain)
sitemap.xml                Sitemap (contains a placeholder domain)
README.md
```

## Preview

Double-click `index.html` to open it in a browser. Everything works from the file system.

To preview over a local server (optional), for example with Python installed:

```
python -m http.server 8000
```

Then open http://localhost:8000.

## Before you publish: replace the placeholders

Search the project for `REPLACE`, `ADD BEFORE LAUNCH`, `ENABLE AFTER` and `[… to be added]`.

| What | Where |
|------|-------|
| Production domain (`https://www.example.com/`) | `index.html` (canonical, Open Graph, JSON-LD), `robots.txt`, `sitemap.xml` |
| Address, phone, email, office hours | Contact section and footer in `index.html` (each placeholder has a comment showing the exact link markup to use, such as `tel:` and `mailto:`) |
| Google Maps / Google Business Profile link | Contact section ("Directions") and `sameAs` in the JSON-LD |
| Call / Email buttons | Commented-out block in the Contact section. Uncomment it once the real phone number and email are added |
| Structured data | Add `telephone`, `email`, `address` and `sameAs` to the JSON-LD in `<head>` (a template is in the comment above it) |
| Logo | The site uses PNGs made from the supplied JPG. If a vector (SVG/AI/PDF) version of the logo exists, export higher-quality PNGs from it with the same filenames |
| Location keywords | Once the city or locality is confirmed, add it naturally to the title, meta description, About heading (a suggestion is in a comment) and JSON-LD |
| PSC course details | Add confirmed features, such as mock tests or study material, in the PSC section (see the comment there) |
| Copyright year | Footer (update manually) |

Do not add ratings, reviews, results, fees or staff details unless they are real and verified.

### Why there is no enquiry form

A working form needs a backend or a third-party form service, and this site is HTML/CSS only. Visitors enquire through the phone, email and map links in the Contact section. To add a form later, use a form service that accepts a plain HTML `<form action="…" method="post">` and label every field.

## Customising the design

All colours, fonts, spacing, radii and shadows are CSS custom properties in the `:root` block at the top of `css/style.css`. For example, change `--color-blue` to restyle every button, link and accent.

The site uses the Plus Jakarta Sans font from Google Fonts and falls back to system fonts. To remove the external request, delete the three font `<link>` lines in `<head>`. You can also self-host the font files.

## Deploying

Upload the whole folder to any static host: Netlify, Cloudflare Pages, GitHub Pages, Vercel (static) or regular shared hosting. No build command is needed, and the publish directory is the project root.

After going live with the real domain:

1. Check that the canonical URL, `robots.txt` and `sitemap.xml` use the live domain.
2. Submit `sitemap.xml` in Google Search Console.
3. Create or claim the Google Business Profile, and keep the name, address and phone **identical** to the website.
4. Test the page with Google's Rich Results Test and PageSpeed Insights.

## Accessibility and motion

- Semantic landmarks, one `<h1>`, a logical heading order and a skip link.
- The mobile menu is a CSS-only checkbox toggle. It can be focused with Tab and toggled with Space.
- FAQs use native `<details>` / `<summary>`.
- Every animation and transition is turned off when the visitor's system requests reduced motion (`prefers-reduced-motion`).
- Scroll effects use CSS scroll-driven animations where the browser supports them (currently Chrome, Edge and other Chromium browsers): blur-in section reveals, the reading-progress bar, the header shadow and logo shrink, hero parallax, the learning-path line and the floating back-to-top button. Other browsers show the content in its final state, with no loss of content.
- FAQ answers open with a smooth height animation in browsers that support `::details-content`. Elsewhere they simply open.
