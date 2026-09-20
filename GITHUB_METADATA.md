# GitHub metadata plan

Recommendations based on the source audit, 2026-09-19. No repository visibility or archive setting should change automatically. Do not pin the profile repository itself: its README already appears above pins.

| Pin order | Repository | Description | Homepage | Topics |
| --- | --- | --- | --- | --- |
| 1 | Geogebra-Copilot | Natural-language geometry compiled from typed semantic objects into GeoGebra commands. | Leave blank until live generation is repaired; preview currently returns a missing-key error. | geometry, geogebra, compilers, typescript, artificial-intelligence |
| 2 | phoreal | Physics olympiad training with structured problem ingestion, corpus validation and per-item timing. | https://phoreal.s4m256.workers.dev/problemas#taiwan | physics, physics-olympiad, data-validation, sqlite, typescript |
| 3 | math-shield | Chrome extension protecting MathJax notation during translation and normalizing recognized LaTeX units. | https://s4m256.github.io/math-shield/ (documentation page, not an interactive demo) | chrome-extension, mathjax, latex, mathematical-notation, javascript |
| 4 | Math-Arena | Proof-based math contests with timed PDF submissions, manual grading, standings and rating calculations. | https://matharena-beta.vercel.app | mathematics, math-olympiad, nextjs, supabase, typescript |
| 5 | projeto-pitagoricos-site | Educational website with study materials, individual progress and controlled content publication. | https://www.pitagoricos.com.br (public homepage verified) | education, mathematics, nextjs, supabase, row-level-security |
| 6 | TabuLab | Interactive boards for exploring olympiad configurations with colored pieces, cell annotations and undo. | Leave blank until a hosted board is verified. | mathematics, combinatorics, math-olympiad, visualization, javascript |
| Unpinned | Julia_Fractals | Interactive Julia-set visualization using complex iteration, mouse-controlled parameters and zoom. | Leave blank until hosting is verified. | fractals, complex-numbers, mathematics, canvas, visualization |
| Not a pin | s4m256 | Mathematics, physics and AI software projects. | https://github.com/s4m256 | mathematics, physics, artificial-intelligence |

## GitHub UI actions

Set the descriptions, homepages and topics through each repository's About gear. In the profile's Customize pins dialog, choose the six repositories above and order them exactly as listed. The first four have the strongest distinct engineering stories; Pitagóricos adds a real content/authorization system, and TabuLab provides a simple inspectable mathematical interaction.

Remove generic `config`/`github-config` profile topics. Do not present a broken or unverified endpoint as a Live Demo. Math Arena's URL is a preview, with mock/incomplete areas disclosed in its README.

## Old repository decisions

- **KEEP PUBLIC, unpinned:** Colision_Simulator, Gravity_Simulator, Personal_Website, Julia_Fractals.
- **ARCHIVE consideration:** 3D_viewer, Bayes_Akinator, Grid_Games, Jogo-da-Forca, Prophet_Orpheus, site-imo.
- **CONSIDER PRIVATE:** Face_Detector, Tic-Tac-Toe.

These are presentation recommendations, not judgments that learning exercises have no value. Preserve history; do not delete anything. See [the audit](GITHUB_APPLICATION_AUDIT.md) for source evidence and limitations.
