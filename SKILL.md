---
name: newspaper-daily-skill
description: Render project content into a newspaper-style daily page with deep browsing via chained entry links and breadcrumb navigation. Use when users want to generate daily reports, project papers, or topic papers in static HTML.
---

Use this skill to create or update newspaper pages.

Workflow:
1. Reuse `assets/template/index.html` as the base template. Do not rebuild layout from scratch.
2. Update `assets/template/examples/mvp.json` (or copy it to a new file and then edit).
3. Follow naming rules:
   - Daily: `YYYY-MM-DD.json` and `YYYY-MM-DD.html`
   - Project: `projects/<repo-or-folder-name>/index.json`
   - Topic: `topic-<slug>-YYYY-MM-DD.json`
   - Entry ID: `<domain>-<slug>`
4. Keep deep-browsing fields compatible:
   - Front feed item link: `feed[].entryId`
   - Entry library: `entries[]` with `id/title/content/links[]`
   - Route format: `#/entry/<id>`
5. Verify output:
   - Desktop full-screen layout is readable
   - Mobile single-column view is readable and back/breadcrumb works
   - Fallback data still renders when JSON loading fails
   - Browser print preview can export PDF

For reuse in another project:
- Copy `assets/template/index.html` into target project root.
- Copy `assets/template/examples/mvp.json` into target project `examples/`.
- Fill JSON with project-specific content while preserving field schema.
