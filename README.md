# HHG inverse noise-eval plots

Two pairs of figures for download / comparison.

## Detector model (`N0` + flicker `a`)

From `scatterometry/results/hhg逆问题求解抗噪分析_n0/`
(hhg3 recipe: H55–61, decoupling; floor kept; `a` shared by m=0 and ±1).

| File | Content |
|---|---|
| [n0_eval_noise_strip_new.png](n0_eval_noise_strip_new.png) | Estimated-value strip + box |
| [n0_eval_noise_curve_new.png](n0_eval_noise_curve_new.png) | Estimated-value mean ± 1σ |

Cases: \(N_0=10^4,a=0\); \(10^5,a=0\); \(10^6,a=0\); \(10^5,a=0.05\).

## Baseline (additive dB noise)

From `scatterometry/results/hhg逆问题求解抗噪分析/` (hhg3, same structure / recipe).

| File | Content |
|---|---|
| [hhg3_eval_noise_strip_new.png](hhg3_eval_noise_strip_new.png) | Estimated-value strip + box vs noise (dB) |
| [hhg3_eval_noise_curve_new.png](hhg3_eval_noise_curve_new.png) | Estimated-value mean ± 1σ vs noise (dB) |

## Layer-1 Jacobian / FIM ([PR #1](https://github.com/snpeng258/S4/pull/1), `87a1149`)

Masks and \((\lambda,\varphi)\) figures keep only measurable orders \(m\in\{-1,0,1\}\).
Cut-off cells are blank (gray). Higher-order propagating rows are excluded (122 hidden).

CRLB at default \(N_0=10^6\), YAML \(a=1\%\) (units: nm / °):

| mask | n | cd | depth | LSWA | RSWA | ρ(depth,CD) |
|---|---:|---:|---:|---:|---:|---:|
| prop | 44 | 9.2e-5 | 8.9e-5 | 4.5e-4 | 4.5e-4 | −0.85 |
| decoupling | 28 | 9.2e-5 | 8.9e-5 | 4.5e-4 | 4.5e-4 | −0.85 |
| only90 | 12 | 2.8e-4 | 1.4e-4 | 8.8e-4 | 8.7e-4 | −0.90 |
| m0_all | 20 | 2.6e-4 | 3.7e-4 | 3.7e-2 | 3.6e-2 | −0.93 |
| two_cam | 36 | 9.9e-5 | 9.1e-5 | 4.7e-4 | 4.6e-4 | −0.85 |

`two_cam` ≡ `drop_phi45`. Previous all-order stacked heatmaps: [`fim_study_all_orders/`](fim_study_all_orders/).

| File | Content |
|---|---|
| [fim_study/fim_R_lambda_phi.png](fim_study/fim_R_lambda_phi.png) | \(R_m(\lambda,\varphi)\) for \(m=0,\pm1\) |
| [fim_study/fim_J_m0.png](fim_study/fim_J_m0.png) | \(\partial R/\partial p\) at \(m=0\) |
| [fim_study/fim_J_m-1.png](fim_study/fim_J_m-1.png) | \(\partial R/\partial p\) at \(m=-1\) |
| [fim_study/fim_J_m+1.png](fim_study/fim_J_m%2B1.png) | \(\partial R/\partial p\) at \(m=+1\) |
| [fim_study/fim_Jw_m0.png](fim_study/fim_Jw_m0.png) | Whitened \(J\) at \(m=0\) |
| [fim_study/fim_crlb_by_mask.png](fim_study/fim_crlb_by_mask.png) | CRLB by layout mask |
| [fim_study/fim_crlb_vs_n0.png](fim_study/fim_crlb_vs_n0.png) | CRLB vs \(N_0\) |
| [fim_study/fim_flicker.png](fim_study/fim_flicker.png) | YAML \(a\) vs \(a=0\) |
| [fim_study/fim_corr.png](fim_study/fim_corr.png) | \(F^{-1}\) correlation |
| [fim_study/fim_study.json](fim_study/fim_study.json) | Full numeric dump |

## FIM at pitch = 300 nm

Same recipe / masks / \(m\in\{-1,0,1\}\), only `pitch_nm: 300` (CD/depth/SWA unchanged).
At 300 nm, \(m=\pm1\) propagate at all five \(\varphi\) (60 measurable rows vs 44 at 80 nm).

CRLB at \(N_0=10^6\), \(a=1\%\):

| mask | n | cd | depth | LSWA | RSWA | ρ(depth,CD) |
|---|---:|---:|---:|---:|---:|---:|
| prop | 60 | 9.6e-6 | 1.6e-6 | 4.6e-5 | 5.6e-5 | −0.63 |
| decoupling | 28 | 1.9e-5 | 5.6e-6 | 2.6e-4 | 2.6e-4 | −0.84 |
| only90 | 12 | 2.7e-5 | 7.3e-6 | 2.9e-4 | 2.9e-4 | −0.87 |
| two_cam | 48 | 1.0e-5 | 1.8e-6 | 4.8e-5 | 7.4e-5 | −0.65 |

| File | Content |
|---|---|
| [fim_study_pitch300/fim_R_lambda_phi.png](fim_study_pitch300/fim_R_lambda_phi.png) | \(R_m(\lambda,\varphi)\) |
| [fim_study_pitch300/fim_J_m0.png](fim_study_pitch300/fim_J_m0.png) | \(J\) at \(m=0\) |
| [fim_study_pitch300/fim_J_m-1.png](fim_study_pitch300/fim_J_m-1.png) | \(J\) at \(m=-1\) |
| [fim_study_pitch300/fim_J_m+1.png](fim_study_pitch300/fim_J_m%2B1.png) | \(J\) at \(m=+1\) |
| [fim_study_pitch300/fim_crlb_by_mask.png](fim_study_pitch300/fim_crlb_by_mask.png) | CRLB by mask |
| [fim_study_pitch300/fim_crlb_vs_n0.png](fim_study_pitch300/fim_crlb_vs_n0.png) | CRLB vs \(N_0\) |
| [fim_study_pitch300/fim_study.json](fim_study_pitch300/fim_study.json) | Numeric dump |

## FIM at pitch = 300 nm, CD = 150 nm

Same recipe / masks as the 300 nm pitch run, only `cd_nm: 150` (duty ≈ 50%).
Layout is unchanged (60 measurable rows); CRLB and \(\rho\) change with the wider line.

CRLB at \(N_0=10^6\), \(a=1\%\):

| mask | n | cd | depth | LSWA | RSWA | ρ(depth,CD) |
|---|---:|---:|---:|---:|---:|---:|
| prop | 60 | 1.2e-4 | 1.2e-5 | 7.7e-4 | 8.2e-4 | 0.09 |
| decoupling | 28 | 2.1e-4 | 1.3e-5 | 1.6e-3 | 1.6e-3 | −0.06 |
| only90 | 12 | 8.6e-4 | 1.3e-5 | 2.1e-3 | 2.1e-3 | −0.03 |
| two_cam | 48 | 1.3e-4 | 1.2e-5 | 7.8e-4 | 9.4e-4 | 0.08 |

| File | Content |
|---|---|
| [fim_study_pitch300_cd150/fim_R_lambda_phi.png](fim_study_pitch300_cd150/fim_R_lambda_phi.png) | \(R_m(\lambda,\varphi)\) |
| [fim_study_pitch300_cd150/fim_J_m0.png](fim_study_pitch300_cd150/fim_J_m0.png) | \(J\) at \(m=0\) |
| [fim_study_pitch300_cd150/fim_J_m-1.png](fim_study_pitch300_cd150/fim_J_m-1.png) | \(J\) at \(m=-1\) |
| [fim_study_pitch300_cd150/fim_J_m+1.png](fim_study_pitch300_cd150/fim_J_m%2B1.png) | \(J\) at \(m=+1\) |
| [fim_study_pitch300_cd150/fim_crlb_by_mask.png](fim_study_pitch300_cd150/fim_crlb_by_mask.png) | CRLB by mask |
| [fim_study_pitch300_cd150/fim_crlb_vs_n0.png](fim_study_pitch300_cd150/fim_crlb_vs_n0.png) | CRLB vs \(N_0\) |
| [fim_study_pitch300_cd150/fim_study.json](fim_study_pitch300_cd150/fim_study.json) | Numeric dump |

## Dense \((\lambda,\varphi)\) FIM (duty 0.5, depth 40 nm)

From `617d7b2`: \(\lambda=10\)–\(30\,\mathrm{nm}\) (1 nm), \(\varphi=0\)–\(90^\circ\) (5°), 399 conditions, 1995 S4 calls per pitch.
80 nm uses `NG=31`, CD 40 nm; 300 nm uses `NG=61`, CD 150 nm.

CRLB at \(N_0=10^6\), \(a=1\%\):

**pitch 80 nm** (841 measurable rows)

| mask | n | cd | depth | LSWA | RSWA | ρ(depth,CD) |
|---|---:|---:|---:|---:|---:|---:|
| prop | 841 | 4.5e-6 | 4.9e-6 | 2.6e-5 | 2.4e-5 | −0.47 |
| decoupling | 435 | 5.0e-6 | 6.4e-6 | 4.1e-5 | 4.1e-5 | −0.57 |
| only90 | 57 | 6.4e-6 | 8.7e-6 | 4.2e-5 | 4.2e-5 | −0.51 |
| two_cam | 183 | 6.1e-6 | 7.8e-6 | 4.2e-5 | 4.2e-5 | −0.53 |

**pitch 300 nm** (1091 measurable rows)

| mask | n | cd | depth | LSWA | RSWA | ρ(depth,CD) |
|---|---:|---:|---:|---:|---:|---:|
| prop | 1091 | 1.5e-5 | 9.8e-7 | 4.2e-5 | 4.2e-5 | −0.15 |
| decoupling | 441 | 2.6e-5 | 1.7e-6 | 7.5e-5 | 7.5e-5 | −0.20 |
| only90 | 63 | 5.5e-5 | 1.8e-6 | 1.1e-4 | 1.0e-4 | −0.27 |
| two_cam | 230 | 3.7e-5 | 1.7e-6 | 8.6e-5 | 8.4e-5 | −0.23 |

| File | Content |
|---|---|
| [fim_study_dense_p80/fim_R_lambda_phi.png](fim_study_dense_p80/fim_R_lambda_phi.png) | 80 nm \(R_m(\lambda,\varphi)\) |
| [fim_study_dense_p80/fim_J_m0.png](fim_study_dense_p80/fim_J_m0.png) | 80 nm \(J\) at \(m=0\) |
| [fim_study_dense_p80/fim_crlb_by_mask.png](fim_study_dense_p80/fim_crlb_by_mask.png) | 80 nm CRLB by mask |
| [fim_study_dense_p80/fim_study.json](fim_study_dense_p80/fim_study.json) | 80 nm numeric dump |
| [fim_study_dense_p300/fim_R_lambda_phi.png](fim_study_dense_p300/fim_R_lambda_phi.png) | 300 nm \(R_m(\lambda,\varphi)\) |
| [fim_study_dense_p300/fim_J_m0.png](fim_study_dense_p300/fim_J_m0.png) | 300 nm \(J\) at \(m=0\) |
| [fim_study_dense_p300/fim_crlb_by_mask.png](fim_study_dense_p300/fim_crlb_by_mask.png) | 300 nm CRLB by mask |
| [fim_study_dense_p300/fim_study.json](fim_study_dense_p300/fim_study.json) | 300 nm numeric dump |

## Inverse-loss landscape ([PR #4](https://github.com/snpeng258/S4/pull/4))

CD × depth slice at the true SWA (\(89.45^\circ\)). Z is the inverse data term
\(L=\sum_j w_j(R_j-R_{\mathrm{meas},j})^2\) with \(\sum w=1\).
Grid is \(17\times17=289\) points; H55–61 odd × \(\theta=70^\circ\) × \(\varphi\in\{0,30,45,60,90\}\).
Main figures are the `decoupling` pair (contour + surface). All four masks sit in each folder.

| run | truth | noiseless min | noisy min (`--seed 0`) |
|---|---|---:|---:|
| 80 nm | CD 40 / depth 40 | 0 at truth | \(3.3\times10^{-7}\) at truth |
| 300 nm | CD 150 / depth 40 | 0 at truth | \(2.7\times10^{-7}\) at truth |

Both pitches show a single basin **inside the ±8 nm window**. 300 nm is elongated along CD (weak CD sensitivity).

| File | Content |
|---|---|
| [chi2_landscape/p80/chi2_cd_depth_decoupling.png](chi2_landscape/p80/chi2_cd_depth_decoupling.png) | 80 nm, noiseless |
| [chi2_landscape/p80_noisy/chi2_cd_depth_decoupling.png](chi2_landscape/p80_noisy/chi2_cd_depth_decoupling.png) | 80 nm, noisy |
| [chi2_landscape/p300/chi2_cd_depth_decoupling.png](chi2_landscape/p300/chi2_cd_depth_decoupling.png) | 300 nm, noiseless |
| [chi2_landscape/p300_noisy/chi2_cd_depth_decoupling.png](chi2_landscape/p300_noisy/chi2_cd_depth_decoupling.png) | 300 nm, noisy |

## Wide-depth second basin ([PR #7](https://github.com/snpeng258/S4/pull/7), `f01786a`)

Same 80 nm square trench and recipe as `p80`, but depth is 16–64 nm (one \(\lambda/(2\cos\theta)\approx 19\)–\(21\,\mathrm{nm}\) fringe). Grid is \(17\times49=833\), noiseless. The old \(\pm 8\,\mathrm{nm}\) slice missed Gross’s height valley.

Every mask has **4 local minima**. Global min is still at truth (CD 40 / depth 40, \(L=0\)). A second basin sits at depth **63 nm** (\(\Delta h=+23\,\mathrm{nm}\)), next to the expected 59–61 nm fringe; a shallower pair is at 16–22 nm.

| mask | n | second basin | \(L\) |
|---|---:|---|---:|
| prop | 44 | CD 40 / depth 63 | \(1.5\times10^{-7}\) |
| decoupling | 28 | CD 40 / depth 63 | \(1.4\times10^{-5}\) |
| m0_all | 20 | CD 40 / depth 63 | \(1.5\times10^{-5}\) |
| only90 | 12 | CD 39 / depth 63 | \(1.5\times10^{-5}\) |

| File | Content |
|---|---|
| [chi2_landscape/p80_wide_depth/chi2_cd_depth_decoupling.png](chi2_landscape/p80_wide_depth/chi2_cd_depth_decoupling.png) | linear contour + surface |
| [chi2_landscape/p80_wide_depth/chi2_cd_depth_decoupling_log.png](chi2_landscape/p80_wide_depth/chi2_cd_depth_decoupling_log.png) | log iso-loss (second basin visible) |
| [chi2_landscape/p80_wide_depth/chi2_cd_depth_decoupling_depth_cut.png](chi2_landscape/p80_wide_depth/chi2_cd_depth_decoupling_depth_cut.png) | loss vs depth at true CD |
| [chi2_landscape/p80_wide_depth/chi2_cd_depth.json](chi2_landscape/p80_wide_depth/chi2_cd_depth.json) | `local_minima` / `depth_cut` |

### Detector noise: when does the second basin win?

Same R-grid, no extra S4. \(R_{\mathrm{meas}}\) uses the per-order detector model
\(\sigma^2=(a f)^2+f/N_0+b^2\) (Poisson + camera floor + flicker; yaml cameras kept).
Both groups use \(a=1\%\); only \(N_0\) changes. Figures are `--seed 0`. Trap rates are 40 independent draws.

| group | \(N_0\) | \(a\) | seed 0 global min | \(L_{63}/L_{40}\) (decoupling) | P(leave truth), 40 trials |
|---|---:|---:|---|---:|---|
| design | \(10^6\) | 1% | CD 40 / depth 40 | 38 | decoupling / prop / only90: **0 / 0 / 0** |
| dim | \(10^4\) | 1% | CD 40 / depth 40 | 1.6 | decoupling / prop / only90: **0.10 / 0.10 / 0.45** |

Design noise still has a needle at truth. At \(N_0=10^4\) the 63 nm valley is within a factor of ~1.2–1.6 of the truth loss; 4/40 decoupling draws jump (3 to ~63 nm, 1 to the shallow fringe). `only90` is already unstable (18/40 leave truth). Raising flicker to \(a=5\%\) at \(N_0=10^6\) does **not** trap decoupling (0/40); the degeneracy is shot/floor (\(N_0\)), not source flicker.

| File | Content |
|---|---|
| [chi2_landscape/p80_wide_depth_noisy_depth_cut_compare.png](chi2_landscape/p80_wide_depth_noisy_depth_cut_compare.png) | both \(N_0\) on one depth cut |
| [chi2_landscape/p80_wide_depth_noisy_n0_1e6/chi2_cd_depth_decoupling_log.png](chi2_landscape/p80_wide_depth_noisy_n0_1e6/chi2_cd_depth_decoupling_log.png) | design noise, log landscape |
| [chi2_landscape/p80_wide_depth_noisy_n0_1e4/chi2_cd_depth_decoupling_log.png](chi2_landscape/p80_wide_depth_noisy_n0_1e4/chi2_cd_depth_decoupling_log.png) | \(N_0=10^4\), log landscape |
| [chi2_landscape/p80_wide_depth_noise_mc.json](chi2_landscape/p80_wide_depth_noise_mc.json) | 40-trial trap counts |

## Compact-recipe CRLB vs inverse (`unify-swa`, `9c837bd`)

Same H55–61 recipe as production inverse (20 conditions). Three parameters: CD, depth, `swa_deg=89.45` (walls equal).
A = LM from truth, raw \(1/\sigma\), 40 trials. B = GA+LM (no 3-param library → `ga_lm`), 20 trials.
Units: nm / deg. `efficiency ≈ CRLB/std` near 1 means the Monte-Carlo scatter matches the bound.

**80 nm** (NG=31, CD 40 / depth 40)

| cell | n | CD std / RMSE / CRLB | depth | SWA |
|---|---:|---|---|---|
| prop A | 40 | 0.144 / 0.142 / 0.116 | 0.189 / 0.187 / 0.151 | 0.828 / 0.817 / 0.677 |
| decoupling A | 40 | 0.142 / 0.141 / 0.116 | 0.190 / 0.189 / 0.151 | 0.828 / 0.818 / 0.677 |
| m0_all A | 40 | 0.230 / 0.228 / 0.187 | 0.349 / 0.355 / 0.314 | 1.42 / 1.40 / 1.19 |
| only90 A | 40 | 0.209 / 0.210 / 0.207 | 0.180 / 0.178 / 0.164 | 0.783 / 0.775 / 0.754 |
| decoupling B | 20 | 0.146 / 0.144 / 0.116 | 0.168 / 0.164 / 0.151 | 0.819 / 0.804 / 0.677 |

**300 nm** (NG=61, CD 150 / depth 40)

| cell | n | CD std / RMSE / CRLB | depth | SWA |
|---|---:|---|---|---|
| prop A | 40 | 0.205 / 0.203 / 0.206 | 0.0235 / 0.0243 / 0.0279 | 0.928 / 0.942 / 0.882 |
| decoupling A | 40 | 0.233 / 0.230 / 0.239 | 0.0259 / 0.0271 / 0.0305 | 1.33 / 1.38 / 1.29 |
| m0_all A | 40 | 0.233 / 0.230 / 0.254 | 0.0838 / 0.0843 / 0.0822 | 1.37 / 1.43 / 1.30 |
| only90 A | 40 | 0.853 / 0.842 / 0.778 | 0.0298 / 0.0306 / 0.0321 | 1.79 / 1.81 / 1.52 |
| decoupling B | 20 | 0.294 / 0.291 / 0.239 | 0.0489 / 0.0480 / 0.0305 | 1.59 / 1.66 / 1.29 |
| m0_all B | 20 | 0.249 / 0.244 / 0.254 | 0.0968 / 0.0949 / 0.0822 | 1.64 / 1.71 / 1.30 |

A sits on the compact CRLB (std ≈ 1.0–1.2 × CRLB). 80 nm B matches A. 300 nm B is slightly worse on depth/SWA, not an order of magnitude.

| File | Content |
|---|---|
| [crlb_mc/p80/decoupling_A/scatter.png](crlb_mc/p80/decoupling_A/scatter.png) | 80 nm decoupling A |
| [crlb_mc/p80/decoupling_B/scatter.png](crlb_mc/p80/decoupling_B/scatter.png) | 80 nm decoupling B |
| [crlb_mc/p300/decoupling_A/scatter.png](crlb_mc/p300/decoupling_A/scatter.png) | 300 nm decoupling A |
| [crlb_mc/p300/decoupling_B/scatter.png](crlb_mc/p300/decoupling_B/scatter.png) | 300 nm decoupling B |
| [crlb_mc/p80/fim_compact.json](crlb_mc/p80/fim_compact.json) | 80 nm compact FIM |
| [crlb_mc/p300/fim_compact.json](crlb_mc/p300/fim_compact.json) | 300 nm compact FIM |

## Download

```bash
git clone https://github.com/snpeng258/result.git
```

Or download individual files from the repo page.
