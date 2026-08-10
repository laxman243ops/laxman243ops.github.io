# laxman243ops.github.io

Personal portfolio for **Butcha Laxmana Rao** — Software Engineer, AI Data
Analyst & AI Engineer — built as a static site for GitHub Pages. No build
step, no framework: just `index.html`, `style.css`, and vanilla JS.

**Live site:** <https://laxman243ops.github.io>
**Source:** <https://github.com/laxman243ops/laxman243ops.github.io>

---

## What's in here

```
.
├── index.html          → all page content and structure
├── style.css            → the entire design system (colors, type, layout)
├── dpe.jpg               → hero photo
├── background.jpeg       → about-section photo
└── README.md
```

## Design concept

The whole page is framed as a running Jupyter notebook, `profile.ipynb`.
Code cells (`In [1]:` / `Out[1]:`) define your profile, skills, and projects
as Python objects and "run" into rendered output; plain sections (about,
experience, education, certifications) sit in markdown cells with no
execution prompt, the same way real notebooks mix code and markdown. Dark
editor palette with a genuine syntax-highlight hue set — blue for keywords,
amber for strings, green for function names / output — set in JetBrains
Mono (code), Sora (headings), and Work Sans (body).

## Features

- **"Run All" button** in the toolbar replays the profile cell's output
  animation and scrolls back to the top, like re-executing a notebook.
  Individual cells (like the hero) also have their own ▶ run button.
- **Code cells vs. markdown cells** are visually distinct — code cells get
  a bordered box, execution prompt, and syntax-highlighted Python; markdown
  cells blend into the page like rendered prose, no prompt in the gutter.
- **Schema-style skills output** — each skill category renders as its own
  card, like the printed output of a Python dict.
- **Expandable project records** — built with native `<details>/<summary>`,
  so each project opens/closes on click *and* is keyboard-accessible with
  no extra JS.
- Fully responsive, keyboard-navigable, and respects `prefers-reduced-motion`
  (skips straight to the settled state instead of animating).

## Photos

Two photos are wired into `index.html`, matching the filenames already in
this repo:

- `dpe.jpg` — a small framed portrait inside the profile cell's `Out[1]:`.
- `background.jpeg` — shown as an "attached image" inside the About
  markdown cell, captioned `Image('background.jpeg')`.

Both are referenced by relative path, so keep the files at the repo root
with these exact names and they'll show up automatically. If either file is
missing or fails to load:

- `dpe.jpg` falls back to a "BLR" monogram badge in the same frame.
- `background.jpeg`'s image block hides itself entirely — nothing breaks.

To swap either photo later, replace the file (same filename) or update the
`src` in `index.html`.

## Editing content

Everything lives directly in `index.html`, in plain HTML — there's no data
object to keep in sync:

- **Profile cell** (`#profile`) — name, role, location, summary, stat row,
  and contact chips are in the `.output-profile` block. The `<pre
  class="cell__code">` above it is decorative Python — update it to match
  if you change the facts below.
- **About** (`#about`) — prose paragraphs plus the `background.jpeg` image
  block in `.md-body`.
- **Skills** (`#skills`) — each `.schema-card` in the `Out[2]:` output is
  one category; add or remove `<span class="field">` chips inside
  `.schema-card__body`. The `<pre>` above is a matching (decorative) Python
  dict — keep it roughly in sync.
- **Experience / Education** — each is a `.ledger-row`: date/meta on the
  left, role/org/bullets on the right.
- **Projects** (`#projects`) — each project is a `<details class="record">`
  block inside `Out[3]:`. Edit the title, period, tags (`.field` spans),
  bullet points, and the repo link's `href`.
- **Certifications** — rows in the `<table class="cert-table">`.
- **Contact** (`#contact`) — chips inside `Out[4]:`.

Repository links currently point to
`https://github.com/laxman243ops?tab=repositories`. Once each project has
its own repo, replace the matching `.record__link` `href` with the direct
repo URL.

## Deploying on GitHub Pages

1. Push `index.html`, `style.css`, your photos, and `README.md` to the
   `main` branch of `laxman243ops/laxman243ops.github.io`.
2. In the repo, go to **Settings → Pages** and confirm the source is set to
   deploy from `main` (a `username.github.io` repo usually does this
   automatically).
3. Your site is live at `https://laxman243ops.github.io` within a few
   minutes.

## Running locally

No build tools required — just serve the folder:

```
python3 -m http.server 8000
# then open http://localhost:8000
```

## Credits

Design and build assembled with Claude. Content sourced from Butcha Laxmana
Rao's resume (June 2026) — update `index.html` directly as experience,
projects, and certifications grow. Currently reflects 5 projects and 9
certifications.
