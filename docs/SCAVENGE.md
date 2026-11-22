# SCAVENGE 2026-11-22

## Kaggle users
- bliverrigpdoge: bliverrigpdoge/lb-0-22-3-tweaks-40-tool-calls-no-training — HAVE + MINED (0.22 system full)
- boristown: boristown/gemma-4-e2b-lora-fine-tuning-swe-agent-baseline — HAVE + MINED V23 (ships WITHOUT adapter)
- romanrozen: romanrozen/gemma-eda-baseline-for-a-start-lb-top-1 — HAVE + MINED (EDA+playbook)
- scottweeden: scottweeden/gemma-4-developer-agent-tool-lora-writeup,scottweeden/gemma-4-developer-agent-tool-lora-kit,scottweeden/gemma-4-31b-swe-tool-use-lora — HAVE + MINED (ledger + recipe + evidence)
- verracodeguacas: verracodeguacas/gemma-4-agent-budget-fit-single-agent — MISSING — base of bliverrig 0.22, E3 field-envelope source (Budget-Fit). Needs Kaggle-auth pull.
- dmitriigluzdov: dmitriigluzdov/gemma-4-serving-and-lora-verification-kit — MISSING — cited in boristown kit candidates. Needs Kaggle-auth pull.
- ryanholbrook: ryanholbrook/gemma-4-developer-agent-small-model-leaderboard — HAVE (smallmodel-pull.json) — lane dead top 0.06, correctly skipped.
- honghanhhh: 0.24 wall holder (registry E14/E1) — MISSING — no public artifacts per X-LOGS hunt; K13 rerun only.
- moranzavdi: 1350-episode public trajectories (registry E-MORZ2) — MISSING — fresh/unvetted, needs pull for transfer test.

## Resources
- competition HARNESS_README.md (HAVE 55,940B)
- sample_submission / sample dummy adapter (HAVE via kit checker)
- tools/check_submission.py + check_kinds.json (HAVE — blocking=hard-limit/schema/security only)
- recipe/gemma4_31b_peft_recipe.md (HAVE)
- scripts/sample.py eval_bundles.py train.py eval_adapter.py (HAVE)
- evidence/a1_harness_runs.json rebuild_* (HAVE)
- bundles/a1_graph_decision + 6min + graph_first + skills_lean + skills_multi (HAVE)
- Budget-Aware v2 (MISSING slug — 0.22/0.22 V10, comment-logs only per E-LOGS2)
- Yurnero 0.29 / samson8 (no public artifacts per Q-YURN — not actionable)

## Corrupt
- scratch/gemma/yoink/boristown-lora.zip (21956B HTML login page, NOT a zip — quarantined, needs re-pull with auth)

## Next hunts (needs Kaggle-auth, vault key stays in page/worker)
- verracodeguacas budget-fit notebook (E3 source, bliverrig parent)
- dmitriigluzdov verification kit
- Budget-Aware v2 slug + honghanhhh 0.24 artifacts (expect none per X-LOGS)
- moranzavdi 1350-episode set (transfer test only)
