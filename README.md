# Class Visit Slides

Reveal.js slide decks for guest lectures and one-off class visits, built with
[Quarto](https://quarto.org/docs/presentations/revealjs/). Published to
GitHub Pages on every push to `main`.

**Live site:** <https://ucla-data-science-center.github.io/class-visit-slides/>
**Repo:** <https://github.com/ucla-data-science-center/class-visit-slides>

## Adding a new deck

1. Copy the template folder:
   ```bash
   cp -r 2000-01-01-example-course YYYY-MM-DD-course-name
   ```
2. Edit `YYYY-MM-DD-course-name/slides.qmd`:
   - `title`, `subtitle` (course/department), `date` in the frontmatter,
     since these drive the auto-generated index on the homepage
   - the slide content itself
3. Drop any images/data into the same folder (e.g. `img/`) and reference
   them with a relative path.
4. Preview locally:
   ```bash
   quarto preview YYYY-MM-DD-course-name/slides.qmd
   ```
5. Commit and push to `main`. GitHub Actions builds the site and deploys
   to GitHub Pages automatically. The homepage (`index.qmd`) lists every
   deck under `*/slides.qmd`, newest first, with no manual index upkeep.

## Conventions

- One folder per visit: `YYYY-MM-DD-short-course-name/`
- Each folder's presentation file is always named `slides.qmd`. The
  project config and homepage listing both depend on that filename.
- Shared UCLA-branded theme lives in the repo-level `styles.scss`. Pull it
  into a deck via `theme: [default, ../styles.scss]` in that deck's YAML
  frontmatter, **not** `css: ../styles.scss`. `css:` embeds the file
  as-is without running the Sass compiler, so the `$variables` and
  `scss:defaults`/`scss:rules` blocks are silently ignored and nothing
  renders. `theme:` is what actually compiles it.
- Delete `2000-01-01-example-course/` once you have real decks in place,
  or keep it around as a living template.

## Design

`styles.scss` follows the same pattern as an earlier deck Tim liked
(`~/projects/ospo/network-docs/presentations/iassist-2026/ucospo-theme.scss`):
a self-hosted accessible typeface, a colored underline on every slide
heading (not just the title) so the branding reads as a system, zebra-striped
tables, a tinted blockquote, and real accessibility touches (visible focus
ring, `prefers-reduced-motion` support). Colors are UCLA's instead of that
deck's UC OSPO palette.

Font is [Atkinson Hyperlegible](https://brailleinstitute.org/freefont)
(Braille Institute, SIL Open Font License, free to embed). The source
`.woff2` files live in `fonts/` at the repo root; `styles.scss` embeds them
as base64 data URIs rather than linking the files directly; referencing
them by relative path breaks once Quarto compiles the theme into
`_site/site_libs/`, since that's a different directory than where
`styles.scss` itself lives.

## Local setup

Requires Quarto (`brew install --cask quarto` or
https://quarto.org/docs/get-started/). No R or Python dependencies needed
for plain reveal.js decks.
