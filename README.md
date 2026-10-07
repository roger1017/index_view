# Monopile can-opening geometry screen

Status: **COMPLETE — isolated-opening screening**. 45/45 screen cases, 4/4 shortlist refinements.

This separate study compares 27 one-can and 18 two-can geometries with the corrected production shell and existing signed-tensor recovery. It preserves the historical opening studies. These results select candidates for subsequent three-opening stress and LBA assessment; they do not establish design strength or three-opening interaction.

![Study geometry](figures/01_study_geometry.png)

## Fixed scope

- Outside diameter 8 m; uniform wall 100 mm; cylinder length 40 m. E = 210 GPa, ν = 0.3.
- Opening width 1.5 m measured on the developed midsurface. Radius rounds the opening outline.
- One-can envelope: 4 m, H = 3.0 to 3.8 m in 0.1 m increments. Two-can envelope: 8 m, H = 6.5 to 7.5 m in 0.2 m increments.
- R = 0.3, 0.4, 0.5 m in both families. Openings are centered in their envelope and in the cylinder.
- One isolated opening in the full circumference. The intended application has three openings at 0°, 120°, 240°; interaction is deferred.
- Circumferential welds and thickness transitions are omitted. Can boundaries are geometric references, not supports.
- Bottom rigid end ring fixed; top rigid end ring carries pure bending. Two orthogonal load cases share one stiffness factorization. Nominal stress is intact-annulus M/W = 1 MPa.

## Metric and numerical effort

The screening SCF is the maximum magnitude of either in-plane principal stress over the recovered opening edge, inner/mid/outer layers, and bending directions 0° ≤ θ < 180° at 0.25° spacing. The angle is defined by the existing bend_0/bend_90 bases. Signed axial, circumferential and shear components are combined before principal stresses are calculated. Reversing bending repeats the absolute envelope. No local nominal-stress division, peak filtering or edge-traction correction is applied.

Screen meshes bound rounded-corner arc spacing by 25 mm and straight-edge spacing by 100 mm. The existing outline allocator may refine one region further to satisfy the other. The 0.25 m outward band has 32 biased layers; transition uses 16 layers; sleeve/back spacing is 0.5/0.4 m. The core half-length is max(4 m, H/2 + 1.5 m), leaving room for the tallest opening. All modeled cells remain native Q4 cells with shared periodic seams.

Only the lowest two SCFs within each family receive doubled edge, band and transition resolution. The user omitted the proposed 60 m check; all models remain 40 m long. This bounds work at 49 solves, each containing two bending bases. A 1% band flags close numerical rankings. Refinement compares the governing envelope and all signed paths: paths include 8,001 uniform points and every native knot; the component difference is maximized analytically over bending direction. The reference limits are 1% envelope change and 0.02 of nominal signed-path change. A stable envelope alone is not complete local-path qualification.

Every accepted solve must satisfy the existing 1e-7 equilibrium, projected residual, work and constraint checks. These are screening meshes; the previous H3/R0.5 convergence study remains separate evidence and is not silently extended to all geometries.

## Screening results

![SCF trends](figures/03_scf_trends.png)

![SCF matrix](figures/04_scf_matrix.png)

### One Can

Lowest refined shortlist SCF: **H 3.8 m × W 1.5 m, R 0.5 m; K = 2.7736**. Governing layer: outer; sampled bending direction 6.50°. Developed area 5.485 m²; clearance to each envelope end 0.10 m.

3 screened geometries fall within 1% of the family minimum. Treat these as close candidates, with height and clearance informing the next design choice.

| H (m) | R (m) | Screen SCF | Direction (°) | Layer | End clearance (m) |
|---:|---:|---:|---:|---|---:|
| 3.8 | 0.5 | 2.7662 | 173.50 | outer | 0.10 |
| 3.7 | 0.5 | 2.7768 | 6.50 | outer | 0.15 |
| 3.6 | 0.5 | 2.7876 | 173.50 | outer | 0.20 |
| 3.5 | 0.5 | 2.7986 | 6.50 | outer | 0.25 |
| 3.4 | 0.5 | 2.8099 | 173.50 | outer | 0.30 |
| 3.3 | 0.5 | 2.8373 | 174.00 | inner | 0.35 |

Recommended starting geometry for the next three-opening stress/LBA stage: **H 3.7 m, R 0.5 m**, refined SCF **2.7843**, with 0.15 m end clearance. Its SCF is 0.38% above the refined numerical minimum. This chooses the shorter of the two refined candidates inside the predefined 1% band to retain more clearance; it is a practical preference, not a claim of optimal strength. Other screened near-ties remain visible above and in the complete data.

![one_can stress atlas](figures/02_one_can_atlas.png)

### Two Can

Lowest refined shortlist SCF: **H 7.5 m × W 1.5 m, R 0.5 m; K = 2.5164**. Governing layer: outer; sampled bending direction 173.25°. Developed area 11.035 m²; clearance to each envelope end 0.25 m.

3 screened geometries fall within 1% of the family minimum. Treat these as close candidates, with height and clearance informing the next design choice.

| H (m) | R (m) | Screen SCF | Direction (°) | Layer | End clearance (m) |
|---:|---:|---:|---:|---|---:|
| 7.5 | 0.5 | 2.5149 | 173.25 | outer | 0.25 |
| 7.3 | 0.5 | 2.5231 | 173.25 | outer | 0.35 |
| 7.1 | 0.5 | 2.5329 | 6.75 | outer | 0.45 |
| 6.9 | 0.5 | 2.5441 | 6.75 | outer | 0.55 |
| 6.7 | 0.5 | 2.5545 | 6.75 | outer | 0.65 |
| 6.5 | 0.5 | 2.5653 | 173.25 | outer | 0.75 |

Recommended starting geometry for the next three-opening stress/LBA stage: **H 7.3 m, R 0.5 m**, refined SCF **2.5262**, with 0.35 m end clearance. Its SCF is 0.39% above the refined numerical minimum. This chooses the shorter of the two refined candidates inside the predefined 1% band to retain more clearance; it is a practical preference, not a claim of optimal strength. Other screened near-ties remain visible above and in the complete data.

![two_can stress atlas](figures/02_two_can_atlas.png)

## Verification

| Change | SCF before | SCF after | Envelope change | Signed-path change / nominal | Peak ≤1% / path ≤0.02 |
|---|---:|---:|---:|---:|---|
| refinement: one_can_h3.8_r0.5_refined_L40 | 2.76625 | 2.77363 | 0.266% | 0.04531 | PASS / FAIL |
| refinement: one_can_h3.7_r0.5_refined_L40 | 2.77680 | 2.78430 | 0.269% | 0.04548 | PASS / FAIL |
| refinement: two_can_h7.5_r0.5_refined_L40 | 2.51489 | 2.51637 | 0.059% | 0.05658 | PASS / FAIL |
| refinement: two_can_h7.3_r0.5_refined_L40 | 2.52309 | 2.52619 | 0.123% | 0.05710 | PASS / FAIL |

4/4 envelope-change checks meet 1%; 0/4 full signed-path checks meet 0.02 of nominal. Study completion means the agreed screening work is complete; it does not label unqualified detailed stress paths as converged.

![Verification](figures/06_verification.png)

No length sensitivity is performed in this study, as requested. Results and rankings apply to the agreed 40 m model. A failed signed-path limit is retained explicitly and requires targeted work before detailed stress qualification.

![Area trade-off](figures/05_area_tradeoff.png)

## Reproduction and retained evidence

Run from the repository root:

```sh
OPENBLAS_NUM_THREADS=1 OMP_NUM_THREADS=1 VECLIB_MAXIMUM_THREADS=1 python3 case_studies/monopile_can_opening_screen/run_screen.py --stage all
python3 case_studies/monopile_can_opening_screen/plot_study.py
python3 case_studies/monopile_can_opening_screen/write_report.py
```

`--stage pilot` runs H3/R0.5 and H7.5/R0.3; `screen` runs the 45 cases; `followup` requires the completed screen. Matching results are reused only after source/geometry/mesh signature validation. Each compressed run retains both signed stress bases, original recovery stages, mesh quality and physical checks. JSON summaries retain complete directional curves; all figures are provided as PNG and SVG. No LBA sweep is started by these commands.

Configuration, solution orchestration, numerical metrics, plots and report generation are separate small modules. Production solver files are unchanged by this study.
