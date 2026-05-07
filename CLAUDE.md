# CLAUDE.md — InSAR Teaching Hub

This file gives a Claude session full context for working on this project.

---

## What this project is

A GitHub Pages teaching hub for masters-level students at ESNZ (Earth Sciences New Zealand) starting out with InSAR. Built and maintained by **Danielle (Dani) Lindsay**, InSAR Scientist at ESNZ, Wellington.

**Core philosophy:** curate existing resources, don't recreate them. Point students to the best things that already exist (ASF storyboards, MintPy docs, EarthScope courses) and add NZ-specific context. Do not pad with AI-generated content that looks authoritative but isn't verified.

**Target audience:** masters students with a geology/earth science background who have seen InSAR in the literature but haven't processed data themselves.

---

## Tech stack

- **MkDocs Material** — static site generator, Markdown source
- **GitHub Actions** — auto-deploys on push to `main` via `.github/workflows/deploy.yml`
- **GitHub Pages** — live at https://dani-lindsay.github.io/insar-teaching-hub/
- **Requirements:** `mkdocs-material`, `mkdocs-jupyter` (see `requirements.txt`)
- **Custom CSS:** `docs/stylesheets/extra.css` — photo grid layout for home page

To deploy: just push to `main`. The Action handles the rest (`mkdocs gh-deploy --force` to `gh-pages` branch).

---

## Repository layout

```
docs/
  index.md                        # Home page — personal intro + photo grid + pathway
  resources.md                    # InSAR Resources — ASF storyboards, background reading, GitHub repos
  community.md                    # Conferences and Scholarships
  about.md                        # Dani's background, research, publications
  assets/
    photos/                       # Personal photos for home page grid (10 photos)
    InSAR_history.png             # History banner — used in literature/keystone-papers.md
    ionosphere_examples_alos2.jpg # From PhD thesis chap2 — used in concepts/ionosphere.md
    SAR_basics.png                # Simons & Rosen 2015 figure (not currently linked from nav)
    ScanSAR_geometry_simons2015.png
    ASF_*.png / View_*.png        # Screenshots for single interferogram workflow
    LiCS*.png                     # Screenshots for LiCSBAS workflow
    Pritchard_Simons_2002.jpg     # Used in single-interferogram.md as example figure
  workflows/
    index.md                      # Workflows landing page
    environment-setup.md          # STUB — OpenSARLab link + placeholder for local install guide
    single-interferogram.md       # Complete — ASF OnDemand screenshots, full walkthrough
    hyp3-mintpy.md                # STUB — links to MintPy docs only, NZ example notebook pending
    licsar-licsbas.md             # Substantive — LiCSBAS install instructions (Ubuntu/Linux)
  literature/
    keystone-papers.md            # History timeline + key papers merged into one table with DOIs
    nz-papers.md                  # 10 NZ/relevant papers with takeaways
  concepts/
    ionosphere.md                 # Ionosphere explainer with thesis figure, correction methods
  tools/
    pygmt-maps.md                 # STUB — just links to PyGMT docs
assets/                           # OLD top-level assets folder — superseded by docs/assets/, can be ignored
```

---

## Navigation structure

```
Home
Resources
  └── InSAR Resources          (resources.md)
  └── Conferences & Scholarships (community.md)
Workflows
  └── [index]                  (workflows/index.md)
  └── Environment Setup        (STUB)
  └── Single Interferogram
  └── Time Series — HyP3 + MintPy  (STUB)
  └── Time Series — LiCSAR + LiCSBAS
  └── PyGMT Maps               (STUB)
Literature
  └── Key Papers               (history timeline + keystone papers merged)
  └── NZ InSAR Papers
  └── Ionospheric Effects
About
```

Key MkDocs features enabled: `navigation.tabs`, `navigation.indexes`, `navigation.sections`. `navigation.indexes` makes the first unlabelled item in a section the section landing page — this is what makes clicking the "Resources" tab land on resources.md rather than showing a blank section.

---

## What's done vs pending

### Done and reviewed by Dani
- Home page (personal intro, photo grid, pathway, NISAR note)
- Resources page (ASF storyboards, background reading, OpenSARLab, GitHub repos)
- Single interferogram workflow (complete, ASF screenshots)
- LiCSBAS workflow (install instructions, needs worked NZ example)
- Key Papers (history timeline with DOIs, bolded essentials)
- NZ InSAR Papers (10 papers with takeaways, consistent table format)
- Ionospheric Effects (full explainer, ALOS-2 thesis figure, correction methods)
- Community / Conferences and Scholarships (EarthScope deadline ~June 9, Fulbright Oct 1)
- About page

### Stubs — content pending
- `workflows/environment-setup.md` — needs full conda/mamba local setup instructions
- `workflows/hyp3-mintpy.md` — needs worked NZ example notebook
- `tools/pygmt-maps.md` — needs example notebooks for InSAR visualisation

### Deliberately hidden / removed
- `getting-started.md` — deleted (Dani felt it was the weakest page; brief InSAR intro moved to resources.md)

### Warning banners
Almost all pages still carry `!!! warning "Under review"` banners — Dani to remove as she reviews each page.

---

## Key content decisions

- **No thumbnails** in literature tables — dropped after initial build. Format is Year | Authors | *Paper* | DOI | Takeaway/Significance.
- **No California-specific figures** in teaching content — students are NZ-based.
- **References consolidated in Literature** — no inline reference lists on other pages, just links to the Literature section.
- **Stubs are labelled honestly** — `!!! note "Worked example coming"` rather than fake placeholder content.
- **Not a course** — the hub explicitly frames itself as a curated pointer to existing resources, not a teaching environment.
- **Dani's voice** — personal, not institutional. First person throughout. "Scholarships are like sunscreen — apply liberally."

---

## Dani's preferences / things to keep in mind

- No bullet-point heavy explanations — prose preferred
- No "gotchas" language — assume students are smart
- No California examples in teaching content (thesis data is NorCal)
- Keep it lean — better to have honest stubs than padded fake content
- ESNZ not GNS (GNS no longer exists as a brand) — link to https://www.gns.cri.nz/
- Dani's staff page: https://www.gns.cri.nz/about-us/staff-search/danielle-lindsay/
- `Dani_content/` is gitignored — never push thesis figures, dissertation files, or personal photos directly from that folder. Copy to `docs/assets/` first.

---

## Things worth adding eventually

- NZ SAR data coverage page — which Sentinel-1 tracks cover NZ, frame numbers, ALOS-2 archive, when NISAR data starts flowing
- NISAR section — Dani is actively working out NZ processing workflows, not ready to write this yet
- Full environment setup guide (conda/mamba, MintPy, ISCE2/3, Windows via WSL2)
- HyP3 + MintPy worked NZ example notebook
- PyGMT example notebooks for InSAR visualisation
- More NZ papers as Dani's reading list grows
- Warning banners to be removed as Dani reviews each page
