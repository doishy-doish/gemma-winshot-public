# MISSED-GRAFTS 2026-11-22 (mined from full yoink, not just the few dozen)
Source: 166 files, 2.36 MiB total. Prior log captured ~6 grafts; below = the rest with free-cost first.

## bliverrig-022 full system (v3, 0.22) — missed beyond 40c/fast-exit/issue-end
- edit-by-12: MUST have edited a source file by call 12; still only reading after 12 = almost never succeeds.
- locate budget: ~10 calls to find+read; no new exploration after call 20.
- minimal precise fix: smallest edit that satisfies issue; strict error strings / exception types / HTTP codes / API signatures.
- targeted tests ONLY: single file/method (pytest tests/test_target.py -k test_feature); NEVER bare pytest / pytest . / discover (minutes, timeouts, budget burn).
- existing tests may be broken (fixtures/env) — IGNORE, never repair test files; NEVER modify/create/delete tests/*, test_*.py (auto-fail).
- docs-code tasks (FastAPI): edit executable code under docs_src/, not docs text.
- find tests via: find tests -name "*<name>*.py"; find code via: git grep -n "text" -- '*.py' | head -20. Do not wander.
- submit gate: targeted test passes -> submit_patch immediately -> verify patch_size>0 && files_changed>0 -> reply Done (single word).
- exhaustion rule: budget-exhausted reply = call submit_patch at once.

## boristown V23 (ships WITHOUT adapter) — missed beyond drop-write_file/think2048
- 5 lean tools (remove write_file): kills 102 repro.py pollution patches + fastapi_15661 8-round 0B loop (V22: 2101B patch, rich_4075 PASS).
- think2048/out4096: kills 49 >=40s rounds (max 230.2s, 57.9m = 20.8% GPU).
- single-shot submit_patch: call once, on status ok stop tool calls + one-line summary (submit_calls/task <=1; kills 43-51 round loop).
- call-10 locate gate: no root cause by call 10 -> best-guess minimal candidate by 10-12, submit by 14; frees 3-5 min.
- repeat-error stop: same error twice with no new signal -> stop, keep cleanest compilable non-empty diff.
- high-ROI overtime (max 3 rounds) ONLY IF: reproducable AssertionError/test-fail AND free get_status says time>120s AND calls>=6 AND CLOCK_MIN<540.
- 2-pace /dev/shm clock + free get_status ROI: CLOCK_MIN<540 normal+overtime vs >=540 rapid single-check conservation; clock probe chained with call-1 grep (0 wasted turns); non-negative [ -s /dev/shm/.t0 ] guard.
- caps 36c/7.5m/80t/240s + compaction_interval=5 (official parity); run_command grep with || true; trap loops via timeout 20 python3 -c.
- prompt slim -52% (10.1k->4.8k chars), bounded reads 40-90 lines; include_thoughts true.
- adapter flag: ATTACH_SURGICAL_LORA_IN_SUBMISSION=False on 31B (100% native W4A16 speed); True only on E4B track.

## romanrozen EDA+playbook — missed beyond localization-#1/reviewer
- TF-IDF baseline: lexical Hit@k + mention-boost (issue names file/module/symbol) = what disciplined grep buys; low Hit@5 = need exploration.
- grep-first localization rule; mandatory reproduce->compile->test loop (many tasks add new tests; §8 edits apply yet break parse).
- analyzer sub-agent tuning: coder context fills fast; analyzer explores in own context, short report back; give graph tools only for vague issues.
- repo hints: hot files + per-repo test commands, small appendix (costs context every turn).
- experiment log: one change at a time + experiment_card.json table (run/arch/prompt-sha/temp/thinking/LB/notes).
- sampling sweep last-green; LoRA ranked #8 LAST with overfit warning (train on non-benchmark repos only).
- zero hard-coded facts: detect tools/model/context/bundle schema from HARNESS_README + sample_submission at runtime.
- edit simulator: exact->whitespace-flex->token-regex 3-tier + MUST still parse after edit.
- context math: schemas ~130 tok/tool + issue (median/p90/max) + max_output; warn if max_output>35% context; analyzer saves grey area.

## scottweeden kit — missed beyond r16/83-turns
- GRAPH decision line: A1 forces every graph call through a GRAPH line -> only 7 graph calls in 4732 (graph tools ~unused by design).
- 6-min cap math: 8-min cap projects 12.4-14.2h for ~120 tasks (errors whole submission); 6-min fits; 7-min only if scorer 0.7x speed.
- chunked SDPA: global-attn head-dim 512 falls back to math kernel (~16 GiB/layer at 16k); chunk 2048 queries, grad-diff 5e-7; + PEFT fp32-cast fix (bf16 autocast) => 16k fits 20.4 GiB peak, 16.7ms/tok.
- loss 0.17->0.11 thin; held-out tool agreement 0.990->0.985 = drift not quality (labels are base own choices).
- adapter heat: biggest moves MLP gate/up + last-10 layers; attention: q_proj of 10 global layers (only full-16k seers); k/v barely move.
- concurrency: 8 tasks share KV (holds ~1.4 seqs) -> 57/50 timeouts; 2 tasks -> 19 timeouts +1 resolve; scorer runs 1-at-a-time so local-8 understates speed.
- graph-first: faster (21 vs 26 calls, -5 timeouts, -33s) but +4 test fails, paired +1/-2 -> skipping reads = careless edits. A1 stays.
- rich-fold: A1 14/48 (29%) at concurrency 2; repo-train 10-12/81.
- checker: blocking = hard-limit/schema/security only (check_kinds.json); rest advisory.

## yufan docs (rules, not tactics)
- 129 public (fastapi/rich/requests/httpx) REPLACED by ~120 hidden private-repo tasks; same pipeline/graphs/verification. Do not overfit 4 public repos.
- 12h total incl setup excl validation; per-task caps via eval_config.yaml; PASS/FAIL per issue; declarative bundle (yaml/prompts/skills/adapters).
- goal: post-train open model for offline consumer hardware.

## small-model leaderboard: top 0.06 — lane dead, stock-31B only. Skipped, correctly.

## Priority add order (free first)
1. edit-by-12 + no-new-exploration-after-20 + targeted-tests-only + never-bare-pytest + never-touch-tests (free, prompt).
2. single-shot submit + repeat-error stop + call-10 gate + 3-round overtime gated on get_status (free).
3. 36c/7.5m + /dev/shm clock + compaction_interval=5 + prompt slim + bounded reads (free).
4. GRAPH decision line (free, kills graph waste without removing tools).
5. 6-min cap (free, fits 12h).
6. reviewer sub-agent + analyzer tuning + experiment log (cheap, needs build).
7. LoRA-attach (costs 1 submission/day, last).


## PRUNE VERDICT 2026-11-22 (CPU-only, zero GPU)
Threads: tensor audit (WHOLE pick V4x-full+B6+E28+F0+G1-direction; THEORY EV18 CONF0.36 CV15.44; PRUNE-32 SEP 17/24 p=0.025; CLAUDE CSP fail-first) + fail-first veto pass.
KEEP 13 (winning-shot core, staged scratch/gemma/plus-winshot/ + scratch/deliverables/plus-winshot.zip 2223B, sys 2281 chars, braces 0, 6 tools, no LoRA, no reviewer core): edit-by-12, no-explore-after-20, targeted-only, never-bare-pytest, never-touch-tests, single-shot-submit, repeat-error-stop, call-10-gate, overtime-3R-gated, 36c/6min/80t/240s+clock, compaction5+bounded-reads+slim, GRAPH-line.
GATED: reviewer-subagent (needs agent_tool wiring proof; boristown ships WITHOUT, scottweeden analyzer 0.15 unadopted) — optional sidecar only.
VETOED: LoRA-attach (D11 3x killed; X24/X25 144/192 vetoed; v6 retrain lower).
MISSED-BY-TENSORS (9 grafts had zero tensor rows — this is what we missed): edit-by-12, no-explore-after-20, targeted-only, never-bare-pytest, never-touch-tests, call-10-gate, overtime-3R-gated, GRAPH-line, 6min-cap.
SKILLS UPDATED: yoink-private-repo/skills-updated/{py-locate,repro-verify,swe-rca,test-scout}/SKILL.md (grep-first, /tmp-only, exact-strings, find-dont-sweep).
