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
├── index.html      → all page content and structure
├── style.css       → the entire design system (colors, type, layout)
└── README.md
```

There are no image assets wired in — the design doesn't use a hero photo.

## Design concept

A "query console / data ledger" theme: the hero types out a SQL query and
returns your profile as a query result, skills are shown as schema tables
(one card per category, fields as chips), and each project is an expandable
record rather than a static card. Palette is a paper-toned background with
pine green and cobalt accents; type is Space Grotesk (display), IBM Plex
Sans (body), and IBM Plex Mono (data/labels).

## Features

- **Typed hero query** — the SQL query in the hero types itself out on load
  and "returns" a one-row result table with your name, role, location, and
  status. Skips straight to the final state if `prefers-reduced-motion` is
  set.
- **Schema-style skills grid** — each skill category (languages, data & ML,
  GenAI, cloud, etc.) renders as its own table card with individual skills
  as fields, instead of animated progress bars.
- **Expandable project records** — built with native `<details>/<summary>`,
  so each project opens/closes on click *and* is keyboard-accessible with
  no extra JS.
- **Ledger-style experience & education rows**, and a certifications table.
- Fully responsive, keyboard-navigable, and respects `prefers-reduced-motion`.

## Editing content

Everything lives directly in `index.html`, in plain HTML — there's no data
object to keep in sync:

- **Hero** — name, role, location, summary, contact chips, and stat row near
  the top of `<body>`.
- **Skills** — each `.schema-card` in the `#skills` section is one category;
  add or remove `<span class="field">` chips inside `.schema-card__body`.
- **Experience / Education** — each is a `.ledger-row` inside a `.ledger`
  block: date/meta on the left, role/org/bullets on the right.
- **Projects** — each project is a `<details class="record">` block in the
  `#projects` section. Edit the title, period, tags (`.field` spans), bullet
  points, and the repo link's `href`.
- **Certifications** — rows in the `<table class="cert-table">` inside
  `#certifications`.

Repository links currently point to
`https://github.com/laxman243ops?tab=repositories`. Once each project has
its own repo, replace the matching `.record__link` `href` with the direct
repo URL.

## Deploying on GitHub Pages

1. Push `index.html`, `style.css`, and `README.md` to the `main` branch of
   `laxman243ops/laxman243ops.github.io`.
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
