# repair-wiki-mirror

A weekly, verbatim copy of the text of [Repair Wiki](https://repair.wiki), the
community repair knowledge base run by the
[Repair Preservation Group](https://fighttorepair.org/).

## Why this exists

When repair.wiki is down, slow, or unreachable, people lose access to the guide
they were in the middle of following, sometimes with a device open on the bench.
This mirror keeps a faithful copy of the wiki's text so that work can continue,
and so the knowledge is preserved in a second place with its full history.

Everything here is the wiki's own content under the
[Creative Commons Attribution-ShareAlike 3.0 licence](https://creativecommons.org/licenses/by-sa/3.0/)
(CC BY-SA 3.0), the licence the wiki publishes under. Every file names the
contributors who wrote it, links back to the original page, and carries the
licence. If you build internal tools on this repository, you must respect that
licence: keep the attribution, link to the source, and share anything you derive
from it under the same terms. `ATTRIBUTION.md` sets out exactly what that means.

We support the Repair Preservation Group and the people who write these guides.
If this mirror is useful to you, please consider
[donating to the Repair Preservation Group](https://fighttorepair.org/donate/501c4/),
and contribute your own fixes on [repair.wiki](https://repair.wiki) itself, where they
help everyone. This mirror is not affiliated with or endorsed by the Repair
Preservation Group.

## How to use this

- **Read a page.** Find the page's title on repair.wiki, swap spaces for underscores,
  and open `wikitext/<Title>.wikitext` for the exact source, or
  `build/markdown/<Title>.md` for a readable version with the guide lists filled in.
  The header at the top of each file tells you who wrote it and where it came from.
- **Search.** Use GitHub's search box, or clone the repository and
  `grep -ril "no service" wikitext/`.
- **Use it in a tool.** `build/pages.jsonl` has one JSON object per page (title, kind,
  infobox, sections, clean Markdown, links, images, contributors). `manifest.json` is the
  index of every page; `files/index.json` lists every image with its URL.
- **Get an image.** Take its URL from `files/index.json`, or prefix the relative
  `images/...` path used in the Markdown with `https://repair-wiki-mirror.repairminder.com/`.
- **Go back in time.** Every snapshot is a tag: `git checkout snapshot/2026-09-23` gives you
  the wiki as it stood that day, and `git log -p wikitext/<Title>.wikitext` shows how a page
  changed. `snapshots/` and `CHANGELOG.md` say what each snapshot changed.
- **Reuse something.** Keep the file's header (or credit the contributors it names), link to
  the page on repair.wiki, and release your work under CC BY-SA 3.0.

## What is in the repository

- `wikitext/` — every main-namespace page, one file per page: a comment header
  (title, ids, URLs, contributors, categories, sha1, licence) then a blank line,
  then the page's wikitext exactly as the wiki holds it. The `sha1` in the header
  is the wiki's own `rvprop=sha1` for that revision and matches the body.
- `templates/`, `modules/`, `files/descriptions/` — Template:, Module: and File:
  description pages, same format.
- `redirects.json` — main-namespace redirects, title to target.
- `manifest.json` — one record per published page (ids, revision, size, sha1,
  kind, infobox, categories, contributors, images, first seen, captured).
- `excluded.json` — pages held back by the junk rule (below), with the reason.
- `contributors.json` — every contributor, page count and user-page URL.
- `files/index.json` — every file the wiki hosts: sha1, size, mime, dimensions,
  uploader, author when known, the pages that use it, and for referenced files
  the URL of our copy.
- `build/markdown/`, `build/pages.jsonl` — a cleaned, derived build (below).
- `snapshots/<date>.json` — what each snapshot changed. `CHANGELOG.md` — one line per snapshot.
- Tags `snapshot/<date>` mark each snapshot, so the corpus as it stood on any date
  can be checked out.

## What it is not

The wiki runs SemanticMediaWiki, PageForms, DynamicPageList and Scribunto. The
wikitext here is not renderable on its own: `{{Device page}}` stores semantic
properties and `{{List Guides}}` is a live query. The cleaned build reconstructs
the guide lists from `manifest.json` and marks them generated. Nothing else is
derived and no language model is involved anywhere.

## Images

Images are not committed. Every image referenced by a published page is copied,
unchanged, to `https://repair-wiki-mirror.repairminder.com/images/<x>/<xy>/<Name>`
(the wiki's own hashed path), and `files/index.json` carries that URL beside the
original. Objects are never deleted; when the wiki replaces a file the previous
bytes are kept under `archive/<sha1>/<Name>`. Files the wiki hosts but no page uses
are indexed but not copied. The cleaned build links images by the relative path
`images/<x>/<xy>/<Name>`.

## The cleaned build

`build/markdown/<same name>.md` and `build/pages.jsonl` are regenerated in full on
every snapshot by a deterministic converter: the structural template becomes YAML
front matter / `infobox`; `{{stub}}` is dropped; `{{List Guides}}` becomes a
generated list; `[[File:X|thumb|caption]]` and galleries become images with their
captions; wikitables become Markdown tables; `[[A|B]]` becomes `[B](A.md)`;
external links are left as they are. `thin: true` marks pages with under 40 words
of prose.

## The junk rule

A page is excluded only when all five hold: no structural template, no heading,
no image, no wikilink or URL, and exactly one named contributor who has no other
page and no anonymous edits. Re-evaluated every snapshot. `excluded.json` lists the
result.
