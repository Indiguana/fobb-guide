# FoBB Field Guide

Static study-guide site for CMU Foundations of Brain & Behavior. Plain HTML, no
build. Serve with `python3 -m http.server 4281`.

Own git repo: pushes to `main` publish to https://indiguana.github.io/fobb-guide/
via GitHub Pages.

When adding or revising a chapter from new lecture material, use the
`teaching-site` skill (it lives in the gamechanger repo at
`.claude/skills/teaching-site/`). Conventions:

- Pages write only `<main>`; `assets/site.js` injects the shell. Register every
  page in its `CHAPTERS` array, and add it to the lecture table in `index.html`.
- `<body data-page>` equals the filename; every `<h2>` has an `id`.
- Canvases need `style="width:100%;display:block"` (style.css doesn't size them).
- Colour words in captions must match the palette: `--accent` is orange,
  `--accent-2` teal, `--accent-3` violet, `--rose` pink, `--gold` gold.
- Don't put a bare `$` in prose — KaTeX treats it as a math delimiter.
- Verify every number in `python3` before writing it.
- Never write a caption describing results that no code produced.
- Mark reconstructed figures as reconstructions; flag where the slides and the
  study guides disagree.

Lecture numbering: the midterm study guide numbers the hearing lecture 12, while
its slide deck is titled "Lecture 13". The guide follows the study guide, since
that is what the exam is written against. Actual mapping:

| Lecture | Topic | Chapter |
| :-- | :-- | :-- |
| 10 | Vision IV — colour, V4, dorsal/ventral | `colour-pathways.html` |
| 11 | NeuroAI (guest: Dr. Maggie Henderson) | `neuroai.html` |
| 12 | Hearing & sound | `hearing-sound.html` |

Speech, music and language are after the midterm and are covered only lightly.
`85-170_ Study Guide Midterm.pdf` is a per-lecture question bank — treat its
questions as the specification for any chapter covering that lecture.

Before finishing, run the skill's validator over this directory:

```sh
python3 <path-to-gamechanger>/.claude/skills/teaching-site/scripts/check_pages.py .
```
