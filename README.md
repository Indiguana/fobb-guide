# FoBB Field Guide

A study guide for CMU Foundations of Brain & Behavior (Fall 2026), rebuilt from the
lecture slides and study guides with intuition, mechanisms drawn out, interactive
figures, and exam-shaped problems. Built for Midterm 1; updated as new lectures come out.

Live: https://indiguana.github.io/fobb-guide/

## Run it

```sh
python3 -m http.server 4281
```

Then open http://localhost:4281. No build step, no dependencies — plain HTML, with
KaTeX loaded from a CDN for the little math there is.

## Layout

| | |
| :-- | :-- |
| `index.html` | Home, lecture → chapter map, study plan |
| `*.html` | One page per chapter, plus `practice.html` and `cheatsheet.html` |
| `assets/site.js` | Shared shell: sidebar, prev/next, table of contents, quizzes, math. The `CHAPTERS` array at the top defines the site's structure. |
| `assets/style.css` | All styling and components |

## Adding a chapter

1. Copy an existing chapter as a starting point; set `<body data-page>` to the
   new filename without `.html`.
2. Add it to `CHAPTERS` in `assets/site.js`, add a card to `index.html`, and fill
   in its row in the lecture table there.
3. Every `<h2>` needs an `id` — the table of contents is built from them.
4. Page scripts go inside `document.addEventListener("shellready", …)`.

Figures marked as reconstructions or schematics were rebuilt because the slide
images didn't survive text extraction — check them against the slides.
