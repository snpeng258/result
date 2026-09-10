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

## Layer-1 Jacobian / FIM ([PR #1](https://github.com/snpeng258/S4/pull/1))

From `runs/inverse/fim_study/` after `python3 fim_study.py --config config_fim.yaml`
(hhg3 recipe H55–61, 20 conditions, 100 S4 calls for one full-order \(J\)).

CRLB at default \(N_0=10^6\), YAML \(a=1\%\) (units: nm / °):

| mask | n | cd | depth | LSWA | RSWA | ρ(depth,CD) |
|---|---:|---:|---:|---:|---:|---:|
| prop | 166 | 2.2e-5 | 6.1e-5 | 2.4e-4 | 2.5e-4 | −0.93 |
| decoupling | 28 | 9.2e-5 | 8.9e-5 | 4.5e-4 | 4.5e-4 | −0.85 |
| only90 | 16 | 2.3e-5 | 6.9e-5 | 2.8e-4 | 2.9e-4 | −0.94 |
| m0_all | 20 | 2.6e-4 | 3.7e-4 | 3.7e-2 | 3.6e-2 | −0.93 |
| no90 | 150 | 2.8e-4 | 1.3e-3 | 0.11 | 0.11 | −0.64 |

`two_cam` ≡ `drop_phi45` (both = prop minus φ=45°).

| File | Content |
|---|---|
| [fim_study/fim_crlb_by_mask.png](fim_study/fim_crlb_by_mask.png) | CRLB by layout mask |
| [fim_study/fim_crlb_vs_n0.png](fim_study/fim_crlb_vs_n0.png) | CRLB vs \(N_0\) |
| [fim_study/fim_flicker.png](fim_study/fim_flicker.png) | YAML \(a\) vs \(a=0\) |
| [fim_study/fim_corr.png](fim_study/fim_corr.png) | \(F^{-1}\) correlation |
| [fim_study/fim_rho_cond.png](fim_study/fim_rho_cond.png) | ρ(depth,CD) and cond(\(F\)) |
| [fim_study/fim_jacobian.png](fim_study/fim_jacobian.png) | Jacobian heatmap |
| [fim_study/fim_jacobian_whitened.png](fim_study/fim_jacobian_whitened.png) | Whitened Jacobian |
| [fim_study/fim_study.json](fim_study/fim_study.json) | Full numeric dump |
| [fim_study/mask_table.txt](fim_study/mask_table.txt) | Row counts by mask |

## Download

```bash
git clone https://github.com/snpeng258/result.git
```

Or download individual files from the repo page.
