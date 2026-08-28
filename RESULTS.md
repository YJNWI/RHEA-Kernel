# RHEA Kernel — Selected Experimental Results

This page reports selected experimental measurements from private RHEA Kernel validation campaigns.

**These figures are benchmark-specific and must not be interpreted as universal savings for every model, workload, company, or hardware platform.**

Technical implementation is not disclosed here.

---

## Controlled multi-round benchmark — v0.4.2.1

Model: **Llama 3.2 3B**  
Runs: **6 rounds × 600 queries**

Both the comparison baseline and RHEA Kernel achieved:

- Coverage: **100%**
- Accuracy: **100%**

Mean measured reductions relative to the controlled baseline:

| Metric | Reduction |
|---|---:|
| LLM calls | **83.8779%** |
| Prompt tokens | **83.9446%** |
| Output tokens | **83.5435%** |
| Wall time | **83.5298%** |
| Measured system-wide energy estimate | **81.1594%** |

The energy result was measured using sampled macOS system-wide telemetry. It is not a calibrated external power-meter measurement and is not process-exclusive.

---

## Independent second-LLM replication — v0.4.2.3

A corresponding six-round controlled validation using **Qwen3 4B** reproduced the overall measured effect while maintaining **100% coverage and accuracy**.

Selected mean reductions:

| Metric | Reduction |
|---|---:|
| LLM calls | **~84.20%** |
| Measured system-wide energy estimate | **~81.71%** |

This supports replication across more than one tested LLM family within the benchmark. It does not establish universal performance.

---

## Later energy campaign — v0.6.0-beta.2.2

A later preregistered campaign evaluated three distinct workload profiles.

Campaign summary:

- Model: **Llama 3.2 3B**
- **24 valid paired measurements total**
- **0 rejected pairs**
- Quality/parity checks: **100% in all recorded arms**

Across the three profiles, mean paired energy reductions ranged from **5.15% to 40.21%**.

The profiles are separate experimental conditions and should not be combined into a universal RHEA Kernel percentage.

---

## Interpretation

The public claim supported by these experiments is limited:

> RHEA Kernel has demonstrated reductions in model workload, token use, elapsed time, and measured system-wide energy in specific controlled workloads while preserving the required output quality.

The project does **not** claim that the same percentage applies to all AI systems or all workloads.

For a later dated validation record, see [VALIDATION_RECORD_2026-08-29.md](VALIDATION_RECORD_2026-08-29.md).
