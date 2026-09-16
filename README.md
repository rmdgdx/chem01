# CHEM01 · Chemistry for Engineers

Interactive course site for **CHEM01 – Chemistry for Engineers**, Department of Chemistry and Physics (CHEMAPHY), Rizal Technological University. Dependency-free, offline-capable HTML.

## Contents

| File | Purpose |
|---|---|
| `index.html` | Course landing page — chapter cards with live file detection, outcomes, 18-week road map, grading |
| `CHEM01_syllabus.html` | Enhanced student-friendly syllabus (print-to-PDF ready), linked from the landing page |
| `chapters/` | Put chapter lecture and exercise files here (see `chapters/README.md`) |
| `.nojekyll` | Tells GitHub Pages to serve files as-is |

## Publish on GitHub Pages

1. Create a new repository (e.g. `chem01`) and upload every file in this folder, keeping the `chapters/` subfolder.
2. Go to **Settings → Pages**, set **Source** to *Deploy from a branch*, choose `main` and `/ (root)`, then save.
3. After a minute the site is live at `https://<username>.github.io/chem01/`. The syllabus is at `.../CHEM01_syllabus.html`.

Chapter cards turn **green** when both lecture and exercise pages are found, **orange** for lecture only, **red** when nothing is uploaded yet. Opened directly from disk (`file://`) the checks are blocked by the browser, so cards show a neutral **Open** state instead.

## Adding a sub-chapter (extra lecture) to any chapter

Sub-chapters are optional additional lectures listed under a chapter's main Lecture/Exercises buttons. They do not affect the live file detection or the chapter's status colour.

1. Upload the lecture file next to the other chapter files, named `chapter-NN-K-<short-title>.html` (e.g. `chapter-01-2-periodic-table.html` for Chapter 1.2, `chapter-03-2-half-life.html` for Chapter 3.2).
2. In `index.html`, find that chapter's `<article class="chapter" data-num="NN">` card. Right after its `<div class="clinks">…</div>` block, add (or extend) a `.subs` block:

```html
<div class="subs">
  <span class="subs-lbl">Additional lectures</span>
  <a class="cl sub" href="chapter-03-2-half-life.html">⏳ 3.2 · Half-Life in Practice</a>
</div>
```

Add one `<a class="cl sub">` line per sub-chapter; never give these links the `lec` or `exo` class, since those are reserved for the main Lecture and Exercises buttons that the checker manages.

## Colour system

Blue-dominant with orange accent: `#040084` · `#1B3BC9` · `#E4E8FA` · `#FD6600` · `#FFEBDD`
