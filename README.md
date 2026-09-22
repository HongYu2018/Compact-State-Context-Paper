# Compact-State-Context experimental and dataset
# First-paper experimental package v0.4

This release freezes the v0.3 context/perception/world algorithms and adds a reproducible experiment harness. It implements the agreed next stage: repeated trials, fresh balanced scenarios, independent evidence-support scoring, ablations, budget sweeps, paired statistics and report figures. It is not a declaration of publication readiness.

## Colab start
1. Unzip and upload `First_Paper_Experiments_v04.ipynb` to Colab.
2. Run cells in order. Upload the ORIGINAL v0.4 ZIP when asked. CPU is sufficient.
3. Keep Drive enabled. Use `paper_v04_pilot_01`, never a v0.3 folder.
4. Run the offline tests. The pretrained visual encoder is bundled; no training is required.
5. Keep STAGE='pilot' and SWEEP=False for the first API run. It schedules 112 episodes (8 scenarios × 7 conditions × 2 independent repetitions), at most 672 requests. The default estimated spending guard is $5; this is not an expected charge or a guaranteed provider billing cap.
6. In Colab Secrets add OPENAI_API_KEY, paste the key into Value, and enable Notebook access. Do not paste the key into code or chat.
7. Review the printed protocol and set RUN_API=True only when ready for paid calls.
8. Download the results ZIP, which contains audit tables, reports, PNG/PDF figures, responses and checkpoints. Share this ZIP for analysis.

## What changed, and what did not
The G/Z/B/T/P state, neural encoder, source-resolution rules, task projection, verifier and two-slot simulator are copied from v0.3. The core runner has three instrumentation changes only: an explicit case argument for one-scenario jobs, a shared API ledger, and unique job identity in cache keys. Model prompt and neural weights are unchanged. Compiler innovation, larger task families and additional modalities remain separate work; this experiment establishes whether the existing method merits those extensions.

The previous uploaded v0.3 results are preserved under `precheck/` with their original file checksum and an extracted summary. They are preliminary DEVELOPMENT evidence. Do not pool them with v0.4 test results or describe v0.3/v0.4 differences as a matched algorithm comparison: sampled scenarios and repetitions differ.

## Schedules
| Stage | Scenarios | Repeats | Main conditions | Episodes | Maximum calls |
|---|---:|---:|---:|---:|---:|
| pilot | 8 | 2 | 7 | 112 | 672 |
| development | 80 | 3 | 7 | 1,680 | 10,080 |
| test | 400 | 3 | 7 | 8,400 | 50,400 |

## Final results from this implementation with 560 scenarios for 80 settings are:
<img width="532" height="273" alt="image" src="https://github.com/user-attachments/assets/fc4f0140-5a8c-4ff4-ae89-749ca9576526" />
