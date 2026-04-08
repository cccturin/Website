# CCC Turin — Website

Static site for Christian Community Center, Turin, NY.

## Files

- `index.html` — Homepage (includes featured event promo banner)
- `about.html` — About page
- `events.html` — Upcoming events (featured event + details, drop-off info)
- `youth-group.html` — Youth Group info
- `rent-ccc.html` — Rental page with live Google Calendar + Zapier request form
- `styles.css` — Shared stylesheet (brand tokens, nav, footer, base styles)

## Deploy to GitHub Pages

1. Create a new repository on GitHub (e.g., `cccturin-site`).
2. Upload all files to the root of the repository (drag and drop in the GitHub web UI works fine).
3. Go to **Settings → Pages**.
4. Under "Build and deployment," set **Source** to `Deploy from a branch`, pick the `main` branch and `/ (root)` folder, and save.
5. Wait ~1 minute. Your site will be live at `https://<username>.github.io/<repo-name>/`.

### Custom domain (optional)

If you want to use `cccturin.com` or similar:

1. In the repo, create a file named `CNAME` containing just the domain (e.g., `cccturin.com`).
2. In your domain registrar, point DNS to GitHub Pages:
   - A records for `@` → `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153`
   - CNAME for `www` → `<username>.github.io`
3. Enable "Enforce HTTPS" in the GitHub Pages settings once DNS resolves.

## Brand palette (Rooted & Hopeful)

| Color | Hex | Use |
|---|---|---|
| Sandstone | `#C9B99A` | Warm accents, subtle surfaces |
| Warm Brown | `#7A5C45` | Primary ink, headers, dark panels |
| Mist Gray | `#9DAAB0` | Soft neutrals |
| Linen | `#F2EDE4` | Page background |
| Sky Blue | `#7AAEC4` | CTAs, highlights, hope |

All colors are defined as CSS variables at the top of `styles.css` — edit there to adjust the whole site.

## Typography

- **Display:** Fraunces (warm, flexible serif with italic variants)
- **Body:** Inter (clean, light-weight sans-serif)

Both loaded from Google Fonts via `<link>` in each page's `<head>`.

## Editing content

All page content lives directly in the HTML — no build step, no framework. Open any `.html` file in a text editor and edit the text. Common edits:

- **Phone / email / address:** appear in the footer of every page and on `about.html` and `index.html`. Search for `315-771-7968` or `cccturin@gmail.com` to find them.
- **Youth group schedule:** edit `youth-group.html` — the schedule panel is near the top.
- **Rental embeds:** the Google Calendar `<iframe>` and Zapier form `<iframe>` live in `rent-ccc.html`. If those URLs change, replace the `src` attributes.
- **Events:** edit `events.html` to update the featured event. The homepage promo banner (the "May 02" card) is in `index.html` — search for `EVENT PROMO` to find it. When the Give & Take passes, either swap in the next event's details or remove both blocks and set the homepage promo / events page to a "no upcoming events" state.

## Accessibility notes

- Respects `prefers-reduced-motion` — entrance animations are disabled for users who request reduced motion.
- All interactive elements are keyboard-accessible.
- Color contrast meets WCAG AA for body text.
