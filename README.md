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

## Download

```bash
git clone https://github.com/snpeng258/result.git
```

Or download individual files from the repo page.
