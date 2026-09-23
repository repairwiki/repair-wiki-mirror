# repair-wiki-mirror

A weekly, verbatim mirror of the text of [repair.wiki](https://repair.wiki)
(Repair Preservation Group), licensed CC BY-SA 3.0. See `ATTRIBUTION.md` and `LICENSE`.

## What it is

- `wikitext/` — every main-namespace page, one file per page: a comment header
  (title, ids, URLs, contributors, categories, sha1, licence) then a blank line,
  then the page's wikitext exactly as the wiki holds it. The `sha1` in the header
  is the wiki's own `rvprop=sha1` for that revision and matches the body.
- `templates/`, `files/descriptions/` — Template: and File: description pages,
  same format. `modules/` appears only if the wiki has Lua modules.
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
every run by a deterministic converter: the structural template becomes YAML front
matter / `infobox`; `{{stub}}` is dropped; `{{List Guides}}` becomes a generated
list; `[[File:X|thumb|caption]]` and galleries become images with their captions;
wikitables become Markdown tables; `[[A|B]]` becomes `[B](A.md)`; external links
are left as they are. `thin: true` marks pages with under 40 words of prose.

## The junk rule

A page is excluded only when all five hold: no structural template, no heading,
no image, no wikilink or URL, and exactly one named contributor who has no other
page and no anonymous edits. Re-evaluated every run. `excluded.json` lists the
result.

## Refresh and history

A job on our Pi captures the wiki every Friday at 19:00 UTC. It lists every live
page (`allpages` with `prop=info`), diffs by page id and revision id against
`manifest.json`, fetches only what changed, verifies every fetched revision
against the API's size and sha1, refreshes contributors, images and the build,
and commits once per snapshot that changed anything, tagged `snapshot/<date>`.
Renames are `git mv`; deletions are committed (the content stays in history and
in the previous tag). Commits are never amended, squashed or force-pushed; a
capture bug is fixed forward in the next snapshot. The `captured` field says
which snapshot last fetched a page; unchanged pages keep their files byte for
byte.

The job's source is the `repair-wiki-mirror` stack in
https://github.com/rikibakerrepaircms/phone-price-trackers — see its README to reproduce a capture.
