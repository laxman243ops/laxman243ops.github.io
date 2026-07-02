# laxman243ops.github.io

Personal portfolio for **Butcha Laxmana Rao** — Data Analytics & Gen AI —
built as a static site for GitHub Pages. No build step, no framework:
just `index.html`, `style.css`, and vanilla JS.

**Live site:** https://laxman243ops.github.io
**Source:** https://github.com/laxman243ops/laxman243ops.github.io

---

## What's in here

```
.
├── index.html          → all page content and structure
├── style.css           → the entire design system (colors, type, layout, animation)
├── assets/
│   ├── dpe.jpg          → hero photo (included)
│   ├── background.jpeg  → about-section photo (included)
│   └── intro.mp3         → optional voice intro clip (add this yourself — see below)
└── README.md
```

## Features

- **Dashboard-styled design** — dark, graph-paper background, teal/amber accents,
  monospace data labels, self-drawing hero chart.
- **Click-to-expand detail modals** — every project, the internship, education,
  and each certification opens a full breakdown when clicked (or focused + Enter).
- **Animated skill bars & stat counters** that fill in as you scroll to them.
- **Voice-reactive hero photo** — add a short `assets/intro.mp3` recording of
  yourself and the play button shows a live soundwave that reacts to your
  actual voice, with the photo frame glowing in sync. If no audio file is
  present, the whole widget hides itself automatically — nothing breaks.
- Fully responsive, keyboard-navigable, and respects `prefers-reduced-motion`.

## Photos

Your two photos are already in `assets/` and wired into `index.html`:

- `dpe.jpg` — the circular hero photo.
- `background.jpeg` — the tilted photo in the About section.

To swap either one later, just replace the file (keep the same filename) or
update the `src` in `index.html` to point at a new file. If a photo is ever
missing, the page falls back to a monogram badge instead of a broken icon.

## Adding a voice clip

There's no `intro.mp3` in this repo yet — I don't have a way to generate
actual audio in this environment, so that part needs a real recording from
you. Two ways to get one:

1. **Record yourself** — a 5–10 second "Hi, I'm Laxman, welcome to my
   portfolio" clip from your phone works fine. Export as `.mp3`.
2. **Generate one with a TTS tool** — services like ElevenLabs or Play.ht
   can produce a natural-sounding clip from typed text if you'd rather not
   record your own voice.

Drop the file in as `assets/intro.mp3`, commit, and the play button in the
hero will start showing a live waveform that reacts to it — no code changes
needed. Until that file exists, the voice-intro widget stays hidden
automatically.

## Editing content

Everything lives in two places in `index.html`:

- The **visible cards/sections** (projects, experience, certifications) —
  edit the text directly in the HTML.
- The **`DETAILS` object** near the bottom of the `<script>` block — this
  powers the "click for more" modal for each project, the internship,
  education, and every certification. Each entry has an `eyebrow`, `title`,
  `tags`, `summary`, `points` (bullet list), and optional `links`. Keep the
  `data-detail="proj1"` attribute on a card in sync with its key in
  `DETAILS` (e.g. `proj1`) if you rename anything.

Repository links currently point to
`https://github.com/laxman243ops?tab=repositories`. Once each project has
its own repo, replace the matching `href` in both the project card and its
`DETAILS` entry with the direct repo URL.

## Deploying on GitHub Pages

1. Push `index.html`, `style.css`, `README.md`, and your `assets/` folder to
   the `main` branch of `laxman243ops/laxman243ops.github.io`.
2. In the repo, go to **Settings → Pages** and confirm the source is set to
   deploy from `main` (a `username.github.io` repo usually does this
   automatically).
3. Your site is live at `https://laxman243ops.github.io` within a few minutes.

## Running locally

No build tools required — just serve the folder:

```bash
python3 -m http.server 8000
# then open http://localhost:8000
```

## Credits

Design and build assembled with Claude. Content sourced from Butcha Laxmana
Rao's resume (June 2026) — update `index.html` directly as your experience,
projects, and certifications grow.
