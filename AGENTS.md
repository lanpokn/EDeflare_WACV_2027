# WACV Migration Instructions

This directory is the WACV 2027 target package for the E-Deflare paper.

The local WACV requirement reference is `原始要求.txt` in this directory (Windows path: `E:\BaiduSyncdisk\2025\event_flick_flare\论文写作\ECCV2026\wacv-2027-author-kit-template\原始要求.txt`). It states that papers, excluding references, must be no longer than eight pages.

The previous-round review/rebuttal notes are in `rebuttal意见.txt` in this directory (Windows path: `E:\BaiduSyncdisk\2025\event_flick_flare\论文写作\ECCV2026\wacv-2027-author-kit-template\rebuttal意见.txt`). Use them as a reviewer-risk checklist when deciding what to keep, clarify, shorten, or move to supplementary material.

Source priority:

1. Paper content, claims, equations, datasets, results, citations, and supplementary text come from `../EDeflare_ECCV_2026/`.
2. Figure/table placement may borrow compact CVPR-style decisions from `../CVPR2026_E_Deflare (2)/` when needed for WACV page limits.
3. Do not reintroduce older CVPR wording when it conflicts with ECCV.

WACV package expectations:

- `main.tex` is the main WACV review-paper entry point.
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
