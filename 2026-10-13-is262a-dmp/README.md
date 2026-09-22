# IS 262A: Data Management and Sharing Plans and the Role of Libraries

Guest lecture slide deck for IS 262A (UCLA Graduate School of Education and
Information Studies), presented by Tim Dennis and Jamie Jamison, UCLA
Library.

**Live:** <https://ucla-data-science-center.github.io/class-visit-slides/2026-10-13-is262a-dmp/slides.html>

**Audience:** graduate students in information studies.
**Duration:** approximately 45–60 minutes, including a DMPTool demonstration
and small-group discussion.
**Date:** placeholder of 2026-10-13, carried over from the prior year's
"Week 3" slot, **confirm the actual Fall 2026 session date and instructor
of record with the course before publishing or presenting**, and update the
`date:` field in `slides.qmd` (and this folder's name, for consistency with
the repo's `YYYY-MM-DD-course-name` convention) if it differs.

## Required software

[Quarto](https://quarto.org/docs/get-started/) (`brew install --cask
quarto`). No R or Python dependencies. This is a plain Markdown/reveal.js
deck.

## Preview locally

```bash
quarto preview slides.qmd
```

## Render

```bash
quarto render slides.qmd
```

Renders `slides.html`, a self-contained file (`embed-resources: true` is
set at the repo level), so it can be opened directly or emailed as a single
file.

## Speaker notes

Press **`s`** while the deck is open in a browser to open speaker view,
which shows the current slide, the next slide, a timer, and the notes
written under each `::: {.notes}` block in `slides.qmd`. Keyboard
navigation (arrow keys, space, Home/End, Esc for overview) is reveal.js's
native behavior and needs no extra configuration for accessibility.

## Printable PDF

Reveal.js decks built with Quarto support a built-in print stylesheet.
Append `?print-pdf` to the rendered URL (e.g.
`slides.html?print-pdf`), open it in Chrome, and use the browser's Print →
Save as PDF. This is Quarto's documented approach and needs no extra build
step. See <https://quarto.org/docs/presentations/revealjs/presenting.html#print-to-pdf>.

## Publishing

Push to `main` on the repo and GitHub Actions (`.github/workflows/publish.yml`)
builds and deploys the whole site, including this deck, to GitHub Pages.
This deck is not yet pushed anywhere. It was built to be reviewed locally
first, per the request that created it.

## Updating citations

Full citations live in `references.bib` (BibTeX) and are cited inline in
`slides.qmd` as `[@key]`, mostly inside speaker notes. Quarto's citeproc
renders a References section as the final slide automatically, no manual
bibliography slide to maintain. Add a new source by adding a `@misc{...}`
entry to `references.bib` and citing its key.

## Branding

UCLA Blue (`#2774AE`), UCLA Gold (`#FFD100`), and the darker blue accents
(`#003B5C`, `#005587`) come from the official UCLA brand guidelines at
<https://brand.ucla.edu/identity/colors> (verified September 2026). No
UCLA or UCLA Library logo image is embedded. An approved downloadable
logo asset wasn't located for this build, so the title slide uses a plain
typographic "UCLA Library" treatment instead. If an approved logo file is
obtained later, add it under `img/` and reference it directly rather than
recreating the mark.

Theme lives in the repo-level `../styles.scss`, shared across all decks in
this repo. Edit it there, not per-deck, unless a specific deck needs to
diverge.

## Images

- `img/rdm-lifecycle-harvard.png`: the research data lifecycle wheel
  diagram. Cioffi, Goldman & Marchese (Harvard Medical School / Harvard
  University), **CC BY-NC 4.0**,
  [doi.org/10.5281/zenodo.8076168](https://doi.org/10.5281/zenodo.8076168).
  Non-commercial classroom use is covered by the license. Swap it out
  first if this deck is ever repurposed commercially. The same file is
  cited by name in Library Carpentry's DMP101 lesson, which this talk is
  itself adapted from.
- `img/craigslist-screenshot.png`: Tim's own screenshot of craigslist's
  Toronto listings page, used on the Craigslist case-study slide. No
  third-party licensing question since Tim took it himself, but it does
  show craigslist's real branding/UI, so don't reuse it outside an
  educational-commentary context like this one.
- `source/is262a-original-google-slides.pdf`: the original Google
  Slides deck (pre-Quarto), kept for provenance and in case other slide
  content needs to be recovered later. Not referenced by `slides.qmd`
  and not something GitHub Pages will publish, but it's a real file in
  the repo so don't `git add -A` it into a public commit without
  thinking about whether it should be public.

## Licensing and attribution

Adapted from Library Carpentry's *DMP101* module (CC BY 4.0). The 2025
version of this talk is archived at
[doi.org/10.5281/zenodo.17360886](https://doi.org/10.5281/zenodo.17360886).
That DOI identifies the 2025 source only, not this revision.

## Annual review checklist

Before each delivery, re-check:

- **Funder policy dates:** the NSF Research.gov DMSP transition (April 27,
  2026), NIH's structured DMS Plan format (May 25, 2026), and NIH's RPPR
  reporting change (October 1, 2026) are all dated milestones already in
  effect by most future deliveries. Re-verify against
  <https://www.nsf.gov/policies/document/pappg24-1-supplement-2> and
  the current NIH Grants Policy Notices before each session, since these
  notices get superseded.
- **DMPTool demo:** test the live workflow before class. Institutional
  SSO, template content, and output-linking features have changed more
  than once in 2026 and may change again.
- **Presenter affiliation:** "UCLA Library" is used as a safe minimum
  affiliation because the prior "Data Science Center" unit name is stale
  post-reorg. Confirm current titles/unit names before presenting.
- **Case study details:** all three case studies are anonymized
  composites from UCLA practice, not published external sources. Don't
  add specifics that can't be verified, and keep the "librarian
  identifies and routes, doesn't decide" framing intact.
- **Jamie Jamison's contact email:** verified as `jamison@library.ucla.edu`
  against the UCLA Library staff directory in September 2026. Reconfirm if
  much time has passed.
