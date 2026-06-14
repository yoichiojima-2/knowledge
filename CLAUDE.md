# CLAUDE.md — content conventions for the knowledge vault

Guidance for writing and revising notes in `vault/`. The goal is **professional,
credible content**: not just good prose, but notes that are visually engaging and
that point readers to authoritative sources.

## what this vault is

A personal, Obsidian-compatible markdown vault published to GitHub Pages via the
reusable workflow in [`yoichiojima-2/nonnative`](https://github.com/yoichiojima-2/nonnative).
Notes and assets live in `vault/`. Because the content is **published**, treat it
as public-facing material: correctness, attribution, and working links matter.

## house style (do not break these)

- **all lowercase prose**, including headings, titles, image captions, and link
  text. This is a deliberate aesthetic — match it.
- every note opens with frontmatter (`domain:`), then an `# h1` title, then a
  one-line summary blockquote: `> **in one line:** ...`.
- section headings are `##` / `###`, all lowercase.
- most notes end with a `## where this falls short` section (honest limitations),
  then `## related`, then `## sources`, then a tag line.
- `## related` is a bulleted list of `[[wikilinks]]` with an em-dash gloss
  explaining *why* the link matters.
- the final line is tags: either inline (`#domain/x #pattern/y`) or `Tags: ...`.

## note skeleton

```markdown
---
domain: <philosophy | computer-science | technology | society | ...>
---

# <title, lowercase>

![<descriptive alt text, lowercase>](<hero image url, see below>)
*<lowercase caption> — <license>, via [wikimedia commons](<file page url>)*

> **in one line:** <one-sentence thesis>

## <body sections>

...

## where this falls short

- ...

## related

- [[other-note]] — why it connects

## sources

- [<lowercase title>](<url>)

#domain/<x> #pattern/<y>
```

## images

The vault publishes to a public site, so **hotlink images from Wikimedia Commons**
using the stable `Special:FilePath` form — never paste arbitrary web images
(copyright + link rot).

- **hero image** goes immediately after the `# h1`, before the one-line summary.
- syntax:
  ```markdown
  ![portrait of friedrich nietzsche, c. 1875](https://commons.wikimedia.org/wiki/Special:FilePath/Nietzsche187a.jpg)
  *friedrich nietzsche, c. 1875 — public domain, via [wikimedia commons](https://commons.wikimedia.org/wiki/File:Nietzsche187a.jpg)*
  ```
- the `Special:FilePath/<Filename>` URL is stable: it 301-redirects to the current
  file on `upload.wikimedia.org`. Always **verify** the file exists before using it
  (fetch the URL; a valid file redirects to `upload.wikimedia.org`).
- the caption links to the Commons **file page** (`.../wiki/File:<Filename>`) and
  states the license (most pre-1900 portraits/artwork are **public domain**).
- **only add a hero image where a real image makes sense**: people (portraits),
  places, named works (book covers), historical events, identifiable artifacts,
  software with an official logo. For **abstract concepts** (caching, coupling,
  currying, abstraction layers, etc.) do **not** force a photo — keep the existing
  Mermaid diagram and just add sources.
- keep the existing in-body Mermaid diagrams (`assets/*.svg` + `.mmd` source);
  they are a strength of this vault.

## sources

Every substantive note ends with a `## sources` section (placed after `## related`,
before the tag line) listing 2–5 **authoritative, verified** external links.

- prefer canonical references over blogs:
  - **philosophy** → [Stanford Encyclopedia of Philosophy](https://plato.stanford.edu/)
    (`plato.stanford.edu/entries/<topic>/`), Internet Encyclopedia of Philosophy,
    primary texts on [Project Gutenberg](https://www.gutenberg.org/).
  - **computer science / systems** → official documentation, and original papers
    where one exists (e.g. the Dynamo paper, Lamport's clocks).
  - **current events / technology** → reputable primary reporting and official
    statements.
- **verify every link resolves** before adding it (fetch it; confirm it's the
  intended page). A broken or wrong source is worse than none.
- link titles are lowercase, matching house style.

## when revising existing notes

- preserve frontmatter, the one-liner, all body sections, Mermaid diagrams,
  wikilinks, and tags. Add — don't rewrite — unless asked.
- insert the hero image after the `# h1`; insert `## sources` after `## related`.
- do not add a hero image to pure demo/meta notes (`index`, `tags`, `image`,
  `wikilinks`).
