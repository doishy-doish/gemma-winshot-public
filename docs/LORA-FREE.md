# LORA-FREE 2026-11-22 — train nothing

## Pre-trained LoRAs (no training needed)
### 1. scottweeden r16 tool-use LoRA (THE 234MB one)
- where: Kaggle Models scottweeden/gemma-4-31b-swe-tool-use-lora (Transformers/main-lora)
- spec: r16/alpha32/dropout0.05, 410 projections (no v_proj on 10 global layers), assistant-only loss, 83 samples/14 tasks, loss 0.17->0.11, tool-agree 0.990->0.985
- access: DO NOT download via tool (crashed tab: 234MB through pipe). 3 safe paths: (1) Kernel Input > Add > Models > scottweeden/... (mounts /kaggle/input/.../adapter_model.safetensors server-side, zero browser RAM); (2) code downloadUrl server-side; (3) read adapter_config.json only (1KB) for wiring check. Bundle layout per writeup cell20: adapters/main_lora/{adapter_config.json,adapter_model.safetensors} + agent.yaml line 'adapter: main_lora'.
- status: PUBLIC, Apache-2.0, ships WITHOUT in his submission.zip until paired run confirms (resolve-rate PENDING)
### 2. boristown surgical_top12 adapter
- where: generated INSIDE boristown V23 notebook (not hosted)
- spec: r8/alpha2/scale0.25, 24 modules/48 tensors, layers 48-59 q_proj+o_proj, trust-region ||dW||<=5e-6, <2.8% Punica overhead
- access: needs a GPU run to materialize; notebook sets ATTACH=False on 31B (100% native speed) — training-free to USE (zero-trained trust-region), but you must run his notebook once to export it. Our boristown-lora.zip pull was corrupt (HTML login page, deleted) — re-pull needs auth.
- status: ZERO-TRAINED, not a real SFT win; skip for 31B
### 3. dmitriigluzdov verification kit
- where: dmitriigluzdov/gemma-4-serving-and-lora-verification-kit (cited in boristown KIT_CANDIDATES)
- spec: 
- access: MISSING — needs Kaggle-auth pull; expected training-free (serving + verification scripts, LoRA checks)
- status: scavenge-queued
### 4. E-LORAHAB rank-8 habit adapter (disc 758968)
- where: Kaggle discussion 758968 (registry E-LORAHAB)
- spec: rank-8 edit-now offline 0->67% (93% valid), live 0.12 < base 0.15/0.13, zero-weight also 0.12
- access: no hosted weights in banked pull (_pull-disc-758968.md 3271B); would need thread scrape + auth
- status: NULL live — not worth chasing as weights
### 5. GH/HF sweep
- where: GitHub + HuggingFace search for gemma-4 SWE LoRA
- spec: 
- access: done 2026-11-22: NO SWE LoRA on GH/HF (both vault GH tokens 401 for authed, public endpoints fine)
- status: only Kaggle has one

## Training-free compute already in-hand
- 124 offline wheels mounted at /wheels (no pip, no net) — HARNESS §9
- 129 snapshots .tgz + graphs JSON + 256-d embeddings .npz pre-mounted (no build needed)
- vLLM 0.19.1 wheelhouse + TP=4 server (competition hardware does serving; you only ship yaml)
- TF-IDF localization baseline (romanrozen §7, sklearn, CPU seconds) — measures Hit@k before any GPU
- edit_file 3-tier simulator + patch-sanity + tag-tolerant YAML validator (CPU, in-notebook)
- check_submission.py + check_kinds.json (HAVE 111KB — blocking=hard-limit/schema/security only; run CPU pre-push)
- experiment log template (one-change + exp_card.json) — tracking without compute

## Safe wiring for the 234MB one (no tab crash)
1. In your fire/submission kernel: Add Input > Models > scottweeden/gemma-4-31b-swe-tool-use-lora (NOT via chat download).
2. stage(with_adapter=True) per writeup cell20 copies adapter_config.json + adapter_model.safetensors to adapters/main_lora/ and inserts 'adapter: main_lora' after the model line.
3. Keep submission.zip adapter-free; build submission_with_adapter.zip side-by-side until the paired rich-fold run (A1 vs A1+adapter, concurrency 2) confirms. That run costs GPU quota — needs calm per-fire order, NOT fired here.
