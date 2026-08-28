# RHEA Kernel — Public Validation Record

**Record date:** 2026-08-29  
**Project:** RHEA Kernel  
**Public purpose:** dated evidence of development and experimentally observed results without disclosure of proprietary implementation details.

---

## Scope of this record

RHEA Kernel is an experimental AI-efficiency project under active private development.

This document records selected validation results that were obtained in controlled RHEA Kernel experiments before this public record was created. It intentionally reports **measured outcomes rather than the mechanisms that produced them**.

Technical implementation and unpublished supporting material remain private. This record is limited to dated validation outcomes and integrity references.

All percentages below are specific to the stated model, workload, experiment and measurement procedure. They are not universal performance guarantees.

---

## 1. Controlled multi-round benchmark — Llama 3.2 3B

**RHEA Kernel v0.4.2.1**  
**Model:** Llama 3.2 3B  
**Validation size:** 6 rounds × 600 queries

Mean measured reductions relative to the controlled baseline:

| Metric | Mean reduction |
|---|---:|
| Complete LLM calls | **83.8779%** |
| Prompt tokens | **83.9446%** |
| Output tokens | **83.5435%** |
| End-to-end wall time | **83.5298%** |
| Measured system-wide energy estimate | **81.1594%** |

Quality in the same benchmark:

- Baseline coverage: **100%**
- RHEA coverage: **100%**
- Baseline accuracy: **100%**
- RHEA accuracy: **100%**

This benchmark recorded simultaneous reductions in complete model invocations, input tokens, generated tokens, elapsed workload time and measured system-wide energy while preserving the benchmark's required coverage and accuracy.

The energy figure is derived from sampled macOS system-wide telemetry integrated over the measured intervals. It is not a calibrated external power-meter measurement and is not process-exclusive.

---

## 2. Independent cross-model replication — 6 × 600 queries per model

The controlled multi-round validation pattern was reproduced with additional model families using the same 6-round × 600-query scale.

### Qwen3 4B

| Metric | Mean reduction | 95% CI across 6 rounds |
|---|---:|---:|
| Complete LLM calls | **84.2006%** | **83.9875–84.4138%** |
| Prompt tokens | **84.1820%** | **83.9627–84.4013%** |
| Output tokens | **84.1532%** | **83.9285–84.3779%** |
| End-to-end wall time | **83.6865%** | **81.7468–85.6262%** |
| Measured system-wide energy estimate | **81.7123%** | **78.6936–84.7309%** |

Quality and output parity: **100%** across the recorded validation rounds.

### Gemma3 4B

| Metric | Mean reduction | 95% CI across 6 rounds |
|---|---:|---:|
| Complete LLM calls | **84.2006%** | **83.9875–84.4138%** |
| Prompt tokens | **84.1838%** | **83.9644–84.4031%** |
| Output tokens | **84.1485%** | **83.9211–84.3760%** |
| End-to-end wall time | **81.8084%** | **79.1197–84.4970%** |
| Measured system-wide energy estimate | **80.3839%** | **76.5736–84.1941%** |

Quality and output parity: **100%** across the recorded validation rounds.

These replications provide evidence that the measured benchmark effect was reproduced on more than one tested model family. They do not establish universal behavior outside the tested models and workloads.

---

## 3. Preregistered paired energy campaign — v0.6.0-beta.2.2

A later RHEA Kernel energy-validation campaign was preregistered before the primary energy results were known and evaluated three distinct workload profiles.

**Model:** Llama 3.2 3B  
**Profiles:** 3  
**Pairs:** 8 per profile, 24 valid pairs total  
**Arms:** 48 total  
**Queries:** 60 per arm  
**Rejected pairs:** 0  
**Quality gate:** 100% in all arms  
**Pair output parity:** 100%

Across the three preregistered workload profiles:

- Mean paired energy reductions ranged from **5.1526% to 40.2103%**.
- Each profile recorded **8 positive and 0 negative pairs**.
- The bootstrap 95% confidence interval was entirely above zero for every profile.
- The exact two-sided sign test was **p = 0.0078125** for every profile.

The campaign retained and verified its measurement evidence, including exact reintegration of **48/48 raw system telemetry logs** and an evidence manifest covering **509 files with zero missing files and zero SHA-256 mismatches**.

The three profiles are separate experimental conditions and should not be averaged into a single universal RHEA Kernel energy percentage.

As above, energy refers to a sampled macOS system-wide estimate and not to a calibrated external meter or process-exclusive measurement.

---

## 4. v0.6.0-beta.3.6 — Functional Freeze

On **2026-08-25**, RHEA Kernel v0.6.0-beta.3.6 received a formal **FUNCTIONAL FREEZE GRANTED** decision for its exact frozen runtime.

**Energy Freeze was not granted for beta.3.6**, and no earlier energy result is transferred to beta.3.6 by this record.

Selected public-safe functional-validation evidence from the freeze decision includes:

- Hosted validation: **171/171 tests passed**.
- Cross-model validation: **2/2 model cases passed**.
- Cross-model output parity: **100%**.
- Endurance validation: **9/9 cases passed**.
- Endurance output parity: **100%**.
- Independent functional recount: **5,220/5,220 recorded raw events validated**, with **0 incorrect, incomplete or cross-mode-mismatched events**.

Additional experimental detail is retained privately.

These beta.3.6 figures are functional-validation results for the recorded workloads. They are not energy claims and do not imply identical results on other models, datasets, workloads or environments.

---

## 5. Frozen beta.3.6 artifact fingerprints

The underlying private runtime and evidence are not published in this repository. Their SHA-256 fingerprints are recorded here so that retained private copies can later be checked against this dated public record.

| Private artifact | SHA-256 |
|---|---|
| `RHEA_Kernel_v0_6_0_beta_3_6_HOSTED_CANDIDATE_20260825.zip` | `7da487f13187008cd2c7d81ac46f1980842db8c31f9b9f18cb2b9a09e51e8fc9` |
| `RHEA_v060_beta3_6_FINAL_FUNCTIONAL_EVIDENCE.zip` | `0daf7997b3a7b50f9c509b6fe3665f1dfbc178ead9bcd43d08c70b9996eae0c3` |
| `RHEA_v060_beta3_6_FUNCTIONAL_FREEZE_DECISION_20260825.zip` | `d31c05d04cb28497aaedeff761af6af7d9ad5accbd625d290a046f55ffdd0f3d` |

Publication of these fingerprints is an integrity record only. It is not a patent filing, statutory copyright registration, qualified electronic timestamp or legal opinion regarding priority or ownership.

---

## 6. What this record establishes — and what it does not

Within the stated experiments, RHEA Kernel has recorded evidence across multiple independent dimensions:

- reduction of complete LLM invocations;
- reduction of prompt/input tokens;
- reduction of output/generated tokens;
- reduction of end-to-end workload time;
- measured system-wide energy reduction;
- quality and coverage preservation;
- output parity;
- replication across multiple model families;
- validation across multiple workload profiles;
- repeated and paired measurements;
- confidence intervals and statistical tests where available;
- frozen private artifacts with public cryptographic fingerprints;
- later cross-model and endurance validation on a functionally frozen beta runtime.

This record does **not** disclose the proprietary mechanism responsible for any of these observations, and it does **not** claim that the reported percentages apply universally.

---

## Rights and disclosure notice

RHEA Kernel remains a proprietary project. Unpublished technical material remains private.

Publication of this document grants no license to unpublished RHEA Kernel materials.

Copyright © 2026. All rights reserved.
