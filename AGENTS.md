# WACV 2027 Paper Package

This directory is the WACV 2027 camera-ready LaTeX package for the E-Deflare paper.

See `../CLAUDE.md` for the camera-ready requirements, deadlines and working rules. This file covers the LaTeX package itself.

Location: `E:\BaiduSyncdisk\2026\WACV 2027\paper\` (migrated 2026-10-20 from `E:\BaiduSyncdisk\2025\event_flick_flare\论文写作\ECCV2026\wacv-2027-author-kit-template\`).

- `原始要求.txt`: WACV 2027 author-kit guidelines (8-page body limit, references excluded).
- `../rebuttal.txt`: the WACV 2027 reviews (meta-review + BpRS, T9Tz, qXPa). This is the checklist for camera-ready revisions.
- `rebuttal意见.txt`: reviews from an earlier venue (Apr–May 2026). History only, not the WACV review.
- `修改记录.md`: running change log. Append after every substantive edit.

Source priority:

1. This directory is the content authority for the camera-ready version.
2. The older ECCV/CVPR drafts under `E:\BaiduSyncdisk\2025\event_flick_flare\论文写作\ECCV2026\` are history only. Do not reintroduce their wording.

WACV package expectations:

- `main.tex` is the main-paper entry point (switch from `review` to final mode for camera-ready).
- `sec/` contains the main-paper sections.
- `supplementary.tex` is the independent supplementary entry point.
- `figures/`, `figures_supp/`, and `main.bib` must remain complete enough for Overleaf compilation.
- Preserve `wacv.sty` and `ieeenat_fullname.bst`.
- The main paper should be prepared for the Algorithms track unless the user requests another track.

Current layout strategy:

- The current working layout prioritizes filling each page with either text or figures/tables, avoiding the earlier failure mode where double-column floats were delayed into pure float pages with large blank areas.
- Do not add mid-section `\FloatBarrier` commands in `main.tex` or the main sections unless there is a concrete, inspected need. Barriers before/inside Experiments previously caused LaTeX to flush float queues and create blank regions.
- Keep major experimental floats declared early. The main simulated quantitative table is intentionally placed immediately after the `Experiments` section opening in `sec/4_experiments.tex`, before the Experimental Settings subsection, so it can appear near the page where Experiments starts.
- In `sec/4_experiments.tex`, prefer `[!tbp]` for double-column experiment floats (`table*`, `figure*`) and `[!htbp]` for single-column downstream floats. Avoid reverting these to strict `[t]` unless a compiled PDF shows a specific regression.
- `preamble.tex` uses `stfloats` so double-column floats can be placed at the bottom of a page. This is intentional for the WACV two-column layout.
- Do not treat page-bottom blank space as acceptable when it is caused by float scheduling. The desired state is that usable body area is occupied by text or nearby figures/tables, except for normal page margins and unavoidable section endings.
- The latest clean-layout version may still be about nine main pages before references. Hitting the eight-page requirement is a separate pass that should reduce size or move content to supplementary material only with explicit intent.

Validation checklist:

- No template placeholder sections remain in the submitted paper.
- All referenced figures and supplementary figures exist.
- All cited BibTeX keys exist in `main.bib`.
- The WACV main paper excludes supplementary content from the eight-page main-paper count.
