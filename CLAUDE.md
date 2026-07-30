# CLAUDE.md — Vimal TN Portfolio Website

> This file is auto-loaded by Claude Code. It is the full memory/handoff from the
> Cowork session where this project was planned and started. Read it first.

## Who this is for

**Vimal TN** — an architect with years of real practice in India, now completing the
**Master in AI for Architecture and the Built Environment (MaAI) at IAAC, Barcelona (2025–26)**.
Email: ar.vimaltn@gmail.com · GitHub: github.com/VimalTN

## The positioning (the whole point of the site)

Vimal is NOT a junior AI person. The narrative is:
**"An experienced architect transitioning to AI — someone who uses AI to build systems
that enhance real architectural workflows, practice, and implementation."**
Every design and copy decision should reinforce: *practice experience → AI systems*.
Hero line currently: "I spent years building architecture. Now I build the systems that build it."

## Site structure (decisions already made — don't relitigate)

- **Single-page site**, plain HTML/CSS/JS, no framework. (Beginner-friendly, but we're now
  moving to a repo + Vercel so it can grow. Keeping vanilla is fine; a light framework is
  optional later.)
- **One unified story, told through scroll** (replaced the old two-portfolio toggle as of
  2026-07-31, at Vimal's request). No toggle. The visitor scrolls the **whole journey from the
  start until now**: Hero → Journey timeline (the "transition spine") → **Architecture foundation**
  → **AI Architect work** → About → Contact. Chronological arc — architecture (the start) comes
  before the AI work (now).
- **Fixed left sidebar nav** (numbered 01–05, scrollspy active-state, inline-SVG social icons,
  "open to roles" dot). Collapses to a top bar + hamburger drawer below 900px. Modelled loosely
  on the reference site (thayaa-portfolio) but kept editorial — NO custom cursor / animated
  backgrounds / gradient overload / right-click-disable (deliberately rejected as off-brand).
- **Rotating hero phrase** — vanilla typewriter in the kicker ("Focus — …") cycling domains.
- **Working contact form** — EmailJS (`@emailjs/browser@4` via CDN). Keys are placeholders
  (`EMAILJS_PUBLIC_KEY/SERVICE_ID/TEMPLATE_ID` at top of the `<script>`); until filled the form
  gracefully falls back to opening the visitor's mail client via `mailto:`.
- **JSON-LD** Person schema in `<head>` for SEO / recruiter previews.
- **Architecture is featured here** as a real section, but the in-depth practice archive lives on
  a **separate CREV Architects website**; architecture cards link out to it
  (`data-link="crev-*"` placeholders until the CREV site URL exists).
- **Scroll mechanics** (vanilla JS): top scroll-progress bar, `IntersectionObserver` fade-in-up
  reveals (`.reveal` → `.in`), scrollspy active-nav highlighting, graceful image loader
  (`[data-img]` swaps real image in, shows labelled placeholder until then). All respect
  `prefers-reduced-motion`.
- **Hero** = narrative headline + "Available" badge + scroll cue (the two toggle entry cards are gone).
- Projects are **rebuilt as native responsive web sections** (NOT embedded A3 PDFs).
- **About** (with small portrait `assets/images/portrait.jpg`) + **Contact** at the bottom.
- Main file: `index.html` (self-contained, valid markup). Has `<meta og:>`/twitter tags + inline SVG favicon.

## Design system

- Theme: **light editorial** — warm off-white, large type, generous whitespace, one accent.
- Colors (CSS vars in index.html):
  `--bg:#f4f1ea` · `--surface:#faf8f3` · `--ink:#1a1815` · `--ink-soft:#4a463f`
  `--ink-mute:#8a857b` · `--line:#ded9cd` · `--accent:#b5482a` (clay red) · `--accent-soft:#e7dfd0`
- Fonts (Google Fonts): **Fraunces** (serif display), **Inter** (body), **JetBrains Mono** (meta/labels).
- Sentence case, italic serif for hooks/quotes, mono for metadata and stats.

## The five AI projects (content is FINAL — written and approved)

Full per-project spread content lives in `/spreads/*.md`. Summary:

1. **OASIS** 🏆 Best Project Award, IAAC · 2026 · Research Studio · Tutor Emanuele Naboni
   Team: Vimal TN, Gaelle Habib, Nithik Vairamuthu, Chun-Chun Chang.
   "Overheating Assessment System for Intervention Strategies." Multi-scale heat-adaptation:
   urban triage (12-factor HVI from live satellite+census) → building IFC room diagnosis →
   unit scale. Decision gate = tells cities what NOT to build. Leads the AI section.
   Links: github.com/helios0007/HVRA · LinkedIn (⚠️ URL needed). No blog post yet (should publish).

2. **The Ground Beneath Growth** · 2026 · AI for All · UIA Barcelona World Capital of Architecture
   Team: Vimal, Seid Burka, Sahil Yousaf, Rafik (⚠️ surname). Interactive installation on the
   Barcelona–El Prat third-runway / Llobregat Delta. 40 yrs of real geodata (land/heat/traffic/life)
   projected on a laser-engraved board + tablet; visitors vote on 2050. BEST PHOTO in portfolio
   (installation table). Consider making it the site/booklet opener.
   Links: live demo ai4all-gis-sim-interface.onrender.com · github.com/VimalTN/AI4ALL_GIS-Sim_Interface

3. **Plug & Grow** (a.k.a. Smart Farming; do NOT use old name "Holy Woah") · 2026 · Research Studio
   Team: Vimal, Juan Gaitán, Rojda Gulel. 4×4 m autonomous rooftop cultivation module, AI brain,
   3 ML models (ANN water / SVM disease / RF scheduling) → fusion. Honest-data story: caught own
   99% as leakage, published honest 40%. Scales to 233-module BCN grid.
   Links: github.com/rojda34/Holy-Woah---Smart-Farming · blog.iaac.net/holy-woah

4. **Chronoscape** · 2025 · Research Studio · Team: Vimal, Nithik, Jinesh Narendra Jain, Seid Burka.
   Faculty: Gonzalo Garcia Perate, Lora Fahmy. Memory-as-input image-generation for urban
   regeneration; Palisades Fire testbed; beats Grok/ChatGPT on site fidelity.
   Links: blog.iaac.net/chronoscape · LinkedIn urn:li:activity:7414961806747852801

5. **RE:PAIR** · 2026 · Hardware II · MRAC/MaAI · Team: Vimal, Onur Berk Doğrultucu, Nithik,
   Arthur Rotstein, Sam Holcombe. Perception-driven closed-loop robotic crack repair. YOLOv8
   detect → toolpath → UR10 3D-print → verify. ROS2 observability. mAP50 0.514, 46.6 ms/img.
   "Integration is a discipline, not a bug." Single-sheet project. Links: video (⚠️ host it), LinkedIn (⚠️).

## Architecture section (scaffolded, awaiting content)

Featured on THIS site as the "foundation" of the journey (it is NOT a separate toggle view
anymore). Placeholder cards exist for: Undergraduate Thesis (`assets/projects/thesis/hero.jpg`),
Urban Study (`assets/projects/urban/hero.jpg`), CREV Architects built work
(`assets/projects/crev/hero.jpg`). Each card has a **"View on CREV Architects ↗"** outbound link
(`data-link="crev-thesis|crev-urban|crev-site"`) — the in-depth practice archive lives on a
**separate CREV Architects website** Vimal is building; this site surfaces the key milestones and
links out. ⚠️ AWAITING from Vimal: project names, descriptions, images, and the CREV URLs.
Write copy in the SAME voice as the AI projects (hook → problem → approach → outcome).

## Voice rules (keep every project consistent)

1. Hook first — one sentence on what it does / why it matters.
2. Problem → approach → outcome, tight. Nothing over ~50 words per block.
3. Active concrete verbs. Tags carry the tech so prose stays readable.
4. Each project has a closing pull-quote in "not about X — it's about Y" register where possible.

## The A3 booklet (parallel deliverable, context only)

Separately, Vimal builds an A3-landscape print/flip-book portfolio in Affinity. System:
each project = 2 A3 sheets = 1 booklet spread (OASIS = 4 sheets); nothing critical crosses
the fold; hero image leads, text supports (~65% image). Shot list + which visual to keep/cut
per project: `/HERO_SHOTLIST_AND_LINKS.md`. Spread copy: `/spreads/`. The WEBSITE reuses this
content but as responsive sections, not embedded sheets.

## Open TODOs (priority order)

1. **Deploy to Vercel** (repo → import → live). See README.
2. Fill link gaps: OASIS LinkedIn URL, RE:PAIR demo video (host + link), Rafik's surname,
   résumé PDF, personal LinkedIn URL (data-link="linkedin" placeholders in index.html).
3. Add real hero images → `assets/projects/{oasis,growth,pluggrow,chronoscape,repair}/hero.jpg`
   (page auto-swaps them in; UI screenshots must be recaptured at 2–3× or they pixelate).
4. Populate the Architecture section with CREV/thesis/urban content.
5. Per-project role line ("My role: …") — still missing on every project; hiring managers need it.
6. Consider: OASIS IAAC blog post (only project without a "read more" deep link).
7. Mobile QA pass; add favicon; add <meta og:> preview tags for link sharing.

## Known critique (from a hiring-manager review of the earlier PDF booklet)

Fixed-in-web-version or still to watch: state individual role; proofread (the PDF had
"seperateanalyses", "makeing", fused pipeline labels); one consistent typeface/grid;
redraw unreadable screenshot-diagrams as clean vector; darker body text for contrast.

## File map

- `index.html` — the website (edit this)
- `CLAUDE.md` — this memory file
- `README.md` — setup + deploy steps
- `/spreads/*.md` — final per-project copy (source of truth for project text)
- `/HERO_SHOTLIST_AND_LINKS.md` — image shot list + link inventory
- `/PROJECT_CONTENT.md` — master project inventory
- `/CONTENT_WORKSHEET.md` — original intake worksheet
- `/assets/projects/<slug>/hero.jpg` — hero images (add these)
