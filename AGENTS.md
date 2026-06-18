# WACV Migration Instructions

This directory is the WACV 2027 target package for the E-Deflare paper.

The local WACV requirement reference is `原始要求.txt` in this directory (Windows path: `E:\BaiduSyncdisk\2025\event_flick_flare\论文写作\ECCV2026\wacv-2027-author-kit-template\原始要求.txt`). It states that papers, excluding references, must be no longer than eight pages.

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

Validation checklist:

- No template placeholder sections remain in the submitted paper.
- All referenced figures and supplementary figures exist.
- All cited BibTeX keys exist in `main.bib`.
- The WACV main paper excludes supplementary content from the eight-page main-paper count.
