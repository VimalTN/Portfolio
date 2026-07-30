# Vimal TN — Portfolio

Personal portfolio site. Architect → AI Architect, told as **one continuous scroll** — the whole
journey from architecture practice in India → the IAAC pivot → the AI systems built now. No toggle;
architecture is featured here and links out to a separate CREV Architects site for depth.

Scroll order: Hero → Journey timeline → Architecture → AI Work → About → Contact. Vanilla scroll
mechanics: progress bar, `IntersectionObserver` reveals, scrollspy nav, graceful image placeholders.

**Stack:** plain HTML/CSS/JS, no build step. Deploys to Vercel as a static site.

> New to this repo or picking it up in Claude Code? Read **CLAUDE.md** first — it has the
> full project memory, content, design system, and TODOs.

## Run locally

Just open `index.html` in a browser. Or serve it:

```bash
python3 -m http.server 8000
# visit http://localhost:8000
```

## Project structure

```
index.html                     the whole site (self-contained)
CLAUDE.md                      project memory / context (read first)
assets/projects/<slug>/hero.jpg  hero images per project
spreads/*.md                   final per-project copy (source of truth)
HERO_SHOTLIST_AND_LINKS.md     image shot list + links
```

## Deploy to Vercel (first time)

### 1. Put it on GitHub

```bash
cd <this folder>
git init
git add .
git commit -m "Initial portfolio site"
# create an empty repo on github.com (e.g. vimaltn/portfolio), then:
git remote add origin https://github.com/VimalTN/portfolio.git
git branch -M main
git push -u origin main
```

### 2. Import to Vercel

1. Go to https://vercel.com and sign in with GitHub.
2. **Add New… → Project** → import the `portfolio` repo.
3. Framework preset: **Other** (it's a static site — no build needed).
4. Leave build command empty, output directory = root. Click **Deploy**.
5. You get a live URL like `vimal-portfolio.vercel.app`. Add a custom domain later in
   Project → Settings → Domains.

### 3. Updating the site

Every push to `main` auto-deploys:

```bash
git add .
git commit -m "what changed"
git push
```

## Adding a project image

Drop a file at `assets/projects/<slug>/hero.jpg`. Slugs:
- AI work: `oasis`, `growth`, `pluggrow`, `chronoscape`, `repair`
- Architecture: `thesis`, `urban`, `crev`
- Portrait (About): `assets/images/portrait.jpg`
- Link-share preview image: `assets/og-preview.jpg`

The page auto-detects and swaps images in; until then it shows a labelled placeholder.
Recapture UI screenshots at 2–3× so they don't pixelate.

## Still-to-fill placeholders (search these in `index.html`)

- **`data-role-todo`** — each AI project has a `My role — add one line` placeholder. Replace the
  text and delete the `data-role-todo` attribute so it renders in full colour.
- **`data-link="crev-*"`** — architecture cards link to the separate CREV site (URL pending).
- **`data-link="linkedin|video|resume"`** — fill the OASIS/RE:PAIR LinkedIn, RE:PAIR demo video,
  and résumé PDF once hosted.
- Architecture card copy (thesis / urban / CREV) — currently placeholder text.

## TODO

See the "Open TODOs" section in `CLAUDE.md`.
