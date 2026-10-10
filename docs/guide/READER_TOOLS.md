# Reader Tools and Maintenance

The [Review Center](../review/index.md) is a personal reading aid, not an application task manager.

## Reading workflow

1. On first use explicitly save a starting baseline. Prior visits are unknown.
2. Mark pages manually: to review, read, not understood, or ask your AI.
3. Compare added/changed/removed documentation with the baseline. A changed read page needs another review.
4. Acknowledge changes when ready. This updates the comparison baseline, not all reading marks.

Filters, name/source search, and 20-page pagination keep long catalogs bounded. Removed pages are listed without opening dead links. Export a local JSON backup if needed; this version has no import, login, multi-device sync, or automatic AI messaging. You can share selected questions with your assistant yourself.

## Source contract

- `extra.portal_reader.project_id`: stable unique slug. Origin + id separate personal browser state. Same id/origin reused for different projects can mix marks.
- `scripts/reader_hooks.py`: deterministic build-only catalog and per-page controls; source files are never rewritten.
- `docs/javascripts/reader.js` / `stylesheets/reader.css`: local, English/Turkish presentation; no telemetry or remote API calls. Hard `[hidden]` styles stay scoped to reader widgets and must not override the theme's navigation.
- Optional Markdown front matter `review_summary` (short intro) and `change_summary` (author's latest plain-text change note). These are not automatically generated diffs or independent proof of progress.
- Optional `extra.portal_reader.dependencies`: source Markdown path → list of public docs-relative files whose bytes affect the page hash. Missing or outside-docs references fail the build.

The generated `assets/reader/catalog.json` contains public page ids, URLs, titles, summaries and hashes. The hash tracks rendered body/title/notes and declared artifact bytes, not the whole application or every template/theme file. Catalog version 1.0; local review-state version 1.0. Rebuild after document changes; publishing source alone does not update an already built site.

## Failure behavior

Catalog errors show a retry and preserve direct document navigation. Invalid/unsupported local data remains untouched until an explicit clear action; a raw backup can be exported. If browser storage is blocked or full, controls report temporary state rather than claiming persistence. Clearing only affects this project's personal marks/baseline, not source documents. Browser marks are not placed in Git.

## Verify changes

Run the Python toolkit tests, content checker and strict build described in the repository README. Optionally run `node tests/test_reader_core.cjs`. Separately test real browser first use, mark/reload, filters, baseline comparison, mobile layout, missing catalog and unsupported saved data. Do not count these as tests of the tracked application. macOS/Linux and other AI-provider setup are not certified by Windows verification.
