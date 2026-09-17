# Naama Hargil — Portfolio

A tiny Astro portfolio: an opening line, a grid of live project previews, and
a contact section.

## Running it

You'll need [Node.js](https://nodejs.org) (18 or newer) installed.

```bash
npm install
npm run dev
```

Then open the URL it prints (usually `http://localhost:4321`).

To build the static site for deployment:

```bash
npm run build
```

This outputs a ready-to-host site into `dist/`. You can drop that folder
onto Netlify, Vercel, GitHub Pages, or any static host.

## Adding your projects

Open `src/data/projects.js` and edit the list — each project just needs:

- `title` — the project name
- `url` — the live site
- `description` — one short line (optional)
- `image` — optional path to a screenshot in `/public` if you'd rather use
  that instead of a live preview

### About the thumbnails

By default, each card embeds the real, live site and scales it down to fit
— so the thumbnail is always an accurate, up-to-date preview of the actual
page, not a static screenshot.

Two things worth knowing:

1. **Some sites block being embedded** (via an `X-Frame-Options` or
   `Content-Security-Policy` header). If a project's card shows up blank,
   that site doesn't allow this — take a screenshot instead, drop it in
   `/public` (e.g. `/public/thumbs/my-project.jpg`), and set `image:
   "/thumbs/my-project.jpg"` for that project in `projects.js`.
2. Live previews add a bit of load time per card since each one loads the
   real page. For 4–6 projects this is fine; if you add many more, consider
   switching everything to static screenshots.

## Editing text

- Name, role, and the opening statement live at the top of
  `src/pages/index.astro`.
- Email and phone are also there, right below the statement.

## Structure

```
src/
  pages/index.astro       → the whole page
  components/ProjectCard.astro → one project card (frame + hover motion)
  data/projects.js        → your project list — edit this most often
  styles/global.css       → colors, type, layout tokens
public/
  favicon.svg
```
