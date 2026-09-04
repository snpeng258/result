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

## Download

```bash
git clone https://github.com/snpeng258/result.git
```

Or download individual PNGs from the repo page.
