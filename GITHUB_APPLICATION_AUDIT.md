# GitHub presentation audit

Audited 2026-09-19 from fresh clones of all 19 public repositories and all advertised remote branches. Claims below concern inspected code, not adoption or production reliability. No visibility changes or branch deletions are recommended automatically.

## Decisions and exact changes

| Repository | Decision | Strongest defensible claim | Biggest presentation problem / change |
| --- | --- | --- | --- |
| s4m256 | FEATURE | Selected mathematical software projects with inspectable implementations | Generic greeting, goals and icon wall: replace with one sentence and six project links. |
| Geogebra-Copilot | FEATURE, first | `main` already implements semantic JSON, strict schemas and compilation; `test` adds tested dependency validation | Default README misdescribes main as raw commands; main already uses semantic JSON. Add branch-qualified architecture, concrete compiler output, tests and a promotion plan; improve `test` on a separate branch. |
| phoreal | FEATURE, second | Structured source ingestion plus persistent per-item attempts and timing | README lists features without evidence. Add pipeline, generated corpus report, validation map and authentic problem screenshot. |
| math-shield | FEATURE, third | `main` protects MathJax v2 nodes and repairs recognized Cyrillic unit/text spans | Universal MathJax claim is false. Add offline reproducible before/after and narrow limitations; link the stronger `test` implementation separately. |
| Math-Arena | FEATURE, fourth | Authenticated, time-gated PDF submissions, grading, standings and pairwise Elo-style rating code | Tiny README hides workflow and mock areas. Add pipeline, code links, setup gaps and explicit mock status. |
| projeto-pitagoricos-site | FEATURE, fifth | Supabase RLS migrations, draft publication and expiring file URLs | Installation leads; organizational context can blur individual work. Add concise software overview and keep attribution to the project. |
| TabuLab | KEEP, sixth | Editable boards with drag-created pieces, cell text and undo | Long roadmap distracts. Lead with implemented interactions and a short limitation note. |
| Julia_Fractals | KEEP, unpinned | Per-pixel complex iteration with mouse-controlled parameter and zoom | Correct click semantics: first click locks the parameter, subsequent clicks pan/zoom. Keep concise. |

## Claims ledger

| Claim | Status | Evidence / boundary |
| --- | --- | --- |
| GeoGebra typed geometry and deterministic compiler | VERIFIED, branch-qualified | `main`: src/ai.ts and src/geometryCompiler.ts. `test`: extended semanticConstruction.ts plus 9 passing library tests. Backend uses a separate weaker parser/compiler. |
| GeoGebra strict dependency validation guards live backend requests | DO NOT CLAIM | `test` Supabase `_shared/copilot.ts` does not call the strict tested library; production integration is a release blocker. |
| GeoGebra validation guarantees mathematically correct output | DO NOT CLAIM | Checks schemas and references; not a theorem prover or complete degeneracy/type checker. |
| GeoGebra live AI demo works | DO NOT CLAIM | Hosted canvas loads, but submitting the documented fenced example returns missing `VITE_GROQ_API_KEY`. |
| GeoGebra authentication/billing/solve production readiness | PARTIAL | Code exists on `test`; external configuration and end-to-end flows unverified. |
| PhoReal has 18 XY exams, 165 problems and 2,200 part records | VERIFIED | Counted from checked-in `data/phors-catalog.json`; generated report will validate unique IDs and relational references. Part records are not independent problems. |
| PhoReal production persistence | PARTIAL | Owner-scoped API/database code and local tests inspected; no production account data written. |
| PhoReal full import audit reproducible without extra files | DO NOT CLAIM | `validate:phors` and `validate:site-data` require untracked `data/phors-full.sqlite`. |
| PhoReal mathematical translation is universally exact | DO NOT CLAIM | Automated preservation checks are narrower than mathematical/linguistic review. |
| MathShield supports every language and MathJax version | DO NOT CLAIM | `main` uses selected Cyrillic mappings and MathJax v2 `Hub.Queue`. |
| MathShield `test` has broader parser and unit database | VERIFIED in code | Locale indexes, balanced-group parser, generated database, preservation corpus and Playwright suite; separate from default branch. |
| Math Arena contest workflow and rating implemented | VERIFIED in code | `src/app/contests/[id]/actions.ts`, `src/app/admin/actions.ts`, `src/lib/submissions.ts`, `src/lib/rating.ts`. |
| Math Arena fully operational production service | PARTIAL | Landing page loads; database migrations/policies are absent from repository; authenticated grading/storage not exercised. Questions are mock UI and contest announcements use mock data. |
| Pitagóricos security mechanisms | VERIFIED in code | Supabase migrations, `material-file` and `admin-users` functions. Production policy effectiveness not audited. |
| Users, impact, awards, benchmarks, partnerships or improved learning outcomes | DO NOT CLAIM | No supporting evidence established in this audit. |

## Branch and asset inventory

- GeoGebra: `main` is an ancestor of `test` (0/27 unique commits). `test` is a candidate for promotion, not a stale branch to delete. Changes also include auth/billing and backend functions. Existing assets are logos, not proof of working geometry.
- MathShield: `main`, `master`, `test`; inspect and retain `test` for v2 review. It adds a parser, generated unit database, fixtures and E2E workflow. Default branch has icons only. Do not merge automatically.
- Profile: old `create-resume` branch (2025-04-12); review before deleting, no evaluator value.
- Pitagóricos: `feat/educational-mvp-supabase` is already contained in `main` (2/0 unique commits); safe cleanup candidate after owner review. Brand PNGs exist; no application screenshot.
- Other repositories advertise only their default branch. No source deletion is needed to improve presentation.
- PhoReal includes statement figures and public corpus data, not UI screenshots. Math Arena includes a logo. TabuLab and Julia have no existing screenshots or test/build scripts.

## Live checks

- GeoGebra: page/canvas load; generation fails with a missing-key message. Do not promote as a functional live demo.
- PhoReal: anonymous dashboard and problem catalog load; catalog displays 165 XY and 296 Taiwan entries. This observation does not verify signed-in timing or AI hints.
- Math Arena: configured hostname redirects to `matharena-beta.vercel.app`; landing page loads and explicitly discloses example data. Account/storage flows not tested.

## Old repositories: recommendation only

| Repository | Recommendation | Evidence / reason |
| --- | --- | --- |
| 3D_viewer | ARCHIVE | Small p5 shape selector; boilerplate page title; retain learning history. |
| Bayes_Akinator | ARCHIVE | Three-character Flask experiment with process-global answer state; no setup/tests. |
| Colision_Simulator | KEEP PUBLIC, unpinned | Explicit collision impulse code; relevant early physics experiment, no numerical validation established. |
| Face_Detector | CONSIDER PRIVATE | Single OpenCV cascade demo in a Desktop path; rectangle coordinates used outside detection loop can be undefined. |
| Gravity_Simulator | KEEP PUBLIC, unpinned | Pairwise inverse-square force implementation; no accuracy/stability claims. |
| Grid_Games | ARCHIVE | Near-duplicate board tool; TabuLab is the clearer selected project. |
| Jogo-da-Forca | ARCHIVE | Small console hangman exercise. |
| Prophet_Orpheus | ARCHIVE | Introductory static Hack Club page. |
| site-imo | ARCHIVE | Static problem-list page with aging external dependencies and little documentation. |
| Tic-Tac-Toe | CONSIDER PRIVATE | Introductory React game, over 37,000 tracked files including node_modules; heavy clone with weak presentation value. |
| Personal_Website | KEEP PUBLIC, unpinned | Fetches the profile README and GitHub project list; useful mirror, not a selected technical project. |

Old projects received source spot checks, not runtime validation or engineering cleanup. No adoption, benchmark, or working-demo claim is made for them.

## Verification results

- GeoGebra semantic branch: `npm run verify` passed (9 tests, TypeScript/Vite build, ESLint).
- PhoReal: `npm test` passed (Taiwan validation, production build, 36 tests). Additional checks and generated reports recorded below after implementation.


## Final evidence and implementation record

- GeoGebra `main`: build and lint pass. Added `scripts/construction-proof.mjs`, generated input/output documentation, a browser fixture and a real screenshot. All 16 emitted commands executed; applet objects D=(1,0) and H=(1,1.33 displayed) appeared. Fixed input, no AI call. `main` has no test script.
- GeoGebra candidate: `docs/semantic-architecture` contains documentation on the existing `test` code. No runtime code was merged. The promotion plan explicitly requires backend integration of the tested strict library.
- PhoReal: new no-dependency report validates snapshot uniqueness and references and checks documentation freshness. Totals: 18 exams, 165 problems, 164 public statements, 1 source-authentication-required statement, 2,200 part records, 233 tags, 797 problem-tag links. `npm test` passes 36 tests after Taiwan validation/build; `test:hints` passes 5; lint passes. Taiwan validator independently reports 296 problems, 1,747 parts, 349 images, 291 solutions and 8,893 formulas; these are separate from XY totals.
- PhoReal browser: public catalog and X26/T1 problem rendered. An anonymous viewport screenshot is included. Content overflows horizontally at the default capture width; no responsive-quality claim is made. Account-dependent timers were disabled while signed out. Saving/hints were not exercised.
- MathShield `main`: new offline fixture executes the actual pure functions from `content.js`; 3 examples pass, including an unchanged formula. Syntax checks pass. Existing already-translated-page observer initialization bug is documented, not silently repaired. No installed-extension or native-translation end-to-end claim.
- MathShield `test`: generated database validator passes (764 units, 383 locale records, 742,877 aliases, 65,279 preserved collisions). These are database totals, not a guarantee of language coverage or runtime accuracy. Full Playwright extension tests were not run. Pages homepage returns 200 and renders documentation, not an interactive demo.
- Math Arena: lint and Next.js build pass. No automated test script. Public homepage works; signed-in storage/correction/rating flows and production policies remain unverified.
- Pitagóricos: lint, test and build pass. Test output includes educational-rule checks and 3 rendered-route checks. Supabase RLS tests require local Supabase/Docker and were not run. Both Vercel and the canonical `www.pitagoricos.com.br` homepage return 200; canonical homepage was inspected in the browser. Existing organizational impact figures were not copied into personal claims.
- TabuLab and Julia: JavaScript syntax checks pass; README changes only. Neither has a build/test script. No live homepage was advertised or claimed.

Build warnings include PhoReal's unresolved-at-build-time KaTeX font references and the Next.js middleware convention warning; successful compilation does not eliminate these runtime/deprecation considerations.

## Highest-value follow-up

Connect GeoGebra's tested semantic validator/compiler to its Supabase request boundary, test that boundary and publish a working anonymous or easily accessible geometry demonstration. That is more valuable than adding features or polishing old projects.
