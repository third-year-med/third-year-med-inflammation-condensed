# CLAUDE.md — a module of the Interactive Pathology Teaching Platform

This repository is one module (a single `index.html`): **Inflammation & Healing — Condensed** (module key `inflcondensed`,
storage prefix `ic_`). Students see it under the PLAIN name ("Inflammation & Healing" / "Cell Injury & Cell Death" — no "Condensed" anywhere
visible, user 2026-10-19); the module key keeps "condensed" (never rename keys). It is an independent, ~50 % shorter high-yield version of `third-year-med/inflammation-healing`, built
on 2026-10-18 from that module's packaged course with the same app code. The original module is unchanged and separate.

The platform's decisions, the checklist for modules, the deployment steps, the testing workflow and the lessons learned are
in the platform repository: `third-year-med/Interactive-pathology-platform` → `CLAUDE.md` and `docs/HANDBOOK.md`
(rebuilds: `docs/REBUILD.md`).

- The course data in `index.html` is encrypted with this module's OWN content key, which lives only in the user's Code.gs
  (`CONTENT_KEYS.inflcondensed`). Never commit a key or an unencrypted copy of the course.
- The `<script id="platform-nav">` block is maintained in the platform repo (`modules/platform-nav.js`) and written here
  with `tools/module-release.js refresh` — do not edit it by hand.
- A new build goes through the preview / compatibility check / go-live procedure (`docs/REBUILD.md`) and must keep the
  IDs of continuing topics, sections, questions, cases and images (they continue the original module's IDs).
- Test changes on the real page with the platform repo's e2e tests (`IC_CONTENT_KEY` in the environment) before pushing.
