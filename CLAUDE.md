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

Lectures 10–12 (NeuroAI, Hearing, Speech/Music/Language) are still to be added
before the 10/7 midterm.

Before finishing, run the skill's validator over this directory:

```sh
python3 <path-to-gamechanger>/.claude/skills/teaching-site/scripts/check_pages.py .
```
