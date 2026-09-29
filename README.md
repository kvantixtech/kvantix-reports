# We tested ourselves first

[![live files](https://github.com/kvantixtech/kvantix-reports/actions/workflows/live-site.yml/badge.svg)](https://github.com/kvantixtech/kvantix-reports/actions/workflows/live-site.yml)
![verdict](https://img.shields.io/badge/our%20own%20engine-1%2F7%20·%202%2F7-c0392b)

Kvantix started as a crypto signal engine. Every score it published was written to a hash-chained ledger before its outcome existed. Then we judged it with the same seven statistical tests we now use on other people's signals.

It failed. Both reports are published here unedited.

| Report | Engine | Data | Result | Verdict |
|---|---|---|---|---|
| [**KVX-EXAMPLE-V1**](reports/kvantix-example-report-v1.pdf) | KAS v1, the score published live on kvantix.tech | 62,907 scores · 8 coins · 6 Jul – 26 Sep 2026 · 4h · 0.06 % | **1/7** | Indistinguishable from noise |
| [**KVX-EXAMPLE-V2**](reports/kvantix-example-report-v2.pdf) | KAS v2.1, the rebuilt engine, run in shadow | 47,944 rows · 14 Jul – 14 Sep 2026 · 4h · 0.06 % | **2/7** | Consistent, but not an edge |

## KAS v1: 1 of 7

The claim: a higher KAS score (0–100) is followed by a higher 4-hour return across the eight coins.

| Test | Result | |
|---|---|---|
| Correlation vs. noise floor | ρ +0.0003 vs. ±0.0769 | ✕ |
| Monotone ranking | 52.1 % → 51.2 % → 50.9 % positive | ✕ |
| Day consistency | 24 of 75 days | ✕ |
| Regime split | up +0.2460 · down −0.0713 · range −0.0825 | ✕ |
| Net of costs | best long-short +0.0063 % at 0.06 % | ✕ |
| Permutation | p = 0.991 | ✕ |
| Stability | slightly negative in both halves | ✓ |

What it was actually measuring: the score correlates +0.35 with the coin's price change over the **previous** four hours. It read momentum. High scores beat low scores only in rising markets, which is a long bias and not an edge. We closed paid access and retracted the claims built on v1.

## KAS v2.1: 2 of 7

The claim: KAS v2.1 ranks the next 4-hour returns well enough to trade at 0.06 % per round trip.

| Test | Result | |
|---|---|---|
| Correlation vs. noise floor | ρ +0.0247 vs. ±0.0887 | ✕ |
| Monotone ranking | 49.7 % → 50.5 % → 53.5 % positive | ✓ |
| Day consistency | 45 of 63 days | ✓ |
| Regime split | up −0.0718 · down +0.0361 · range −0.0163 | ✕ |
| Net of costs | best long-short −0.1432 % at 0.06 % | ✕ |
| Permutation | p = 0.098 | ✕ |
| Stability | half 1 +0.0600 · half 2 −0.0111 | ✕ |

v2.1 got further. It was right on most days, but the gap between the highest- and lowest-scored coins is negative at all three thresholds, before any trading cost. A signal that is right on most days but loses on the days that matter cannot be traded. Its score correlates −0.37 with the previous four hours: where v1 followed momentum, v2.1 leaned towards reversal. We stopped the shadow on 14 September 2026. Nothing built on it was ever offered for sale.

## Check the files

```bash
sha256sum -c SHA256SUMS
```

- Each report prints the SHA-256 of the data it was run on in its header ("Data fingerprint"), together with the toolkit version.
- A daily job compares these PDFs byte for byte with the copies served on kvantix.tech.

| File | SHA-256 |
|---|---|
| `kvantix-example-report-v1.pdf` | `d9bc8f38fe1d071c5aef337c279d76cd8474ec559930d172c71b428962d62274` |
| `kvantix-example-report-v2.pdf` | `8ef4fa29c14b1be6c9ba4cd2542ce61edb7226b09340fa77ff8c523061fdc230` |

## Why publish this

A validation service that only shows the signals that passed is running the same filter it should catch. These reports show what a failure looks like, on our own engine and under our own name. The tests that rejected our engine are now the product. They cost the same whatever the verdict.

- **Your signal:** a free Quick Check, or a written report, at [kvantix.tech](https://kvantix.tech).
- **What each test catches, on data where the truth is known:** [validation-examples](https://github.com/kvantixtech/validation-examples).
- **The method, run in public:** [weather-forecast-test](https://github.com/kvantixtech/weather-forecast-test).

## Licence

The reports are © 2026 Kvantix (CVR 46296036). They may be shared freely **in full and unedited**, with a link to this repository or to kvantix.tech. Quote them in full or not at all: numbers without the verdict next to them tell a different story.

validation@kvantix.tech · Hjørring, Denmark · Statistics, not advice.
