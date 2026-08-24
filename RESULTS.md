# RHEA Kernel — Selected Experimental Results

This page reports selected experimental measurements from private RHEA Kernel validation campaigns.

**These figures are benchmark-specific and must not be interpreted as universal savings for every model, workload, company, or hardware platform.**

No implementation details are disclosed here.

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

A corresponding six-round controlled validation using **Qwen3 4B** reproduced the same overall pattern while maintaining **100% coverage and accuracy**.

Selected mean reductions:

| Metric | Reduction |
|---|---:|
| LLM calls | **~84.20%** |
| Measured system-wide energy estimate | **~81.71%** |

This supports replication across more than one LLM family within the tested benchmark. It does not establish universal performance.

---

## Later energy campaign — v0.6.0-beta.2.2

A later preregistered energy campaign tested three different workload profiles.

Campaign summary:

- Model: **Llama 3.2 3B**
- **8 paired rounds per profile**
- **60 queries per arm**
- **24 valid pairs total**
- **0 rejected pairs**
- Quality/parity checks: **100% in all arms**

Mean paired energy reductions:

| Workload profile | Mean paired energy reduction |
|---|---:|
| Low | **5.15%** |
| Medium | **22.78%** |
| High | **40.21%** |

These profiles are intentionally different experimental conditions and should **not** be averaged into a single universal RHEA Kernel percentage.

---

## Interpretation

The public claim supported by these experiments is limited:

> RHEA Kernel has demonstrated substantial reductions in model workload, token use, elapsed time, and measured system-wide energy in specific controlled workloads while preserving the required output quality.

The project does **not** claim that the same percentage applies to all AI systems or all workloads.
