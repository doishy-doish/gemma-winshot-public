# public-repo (staged 2026-11-22T09:19:57.762Z)
Winning-shot bundle + yoink haul, training-free.

## bundles/plus-winshot (A1-faithful + pruned grafts)
- agent.yaml: single agent, gemma-4-31b-it-qat-w4a16-ct, 9 tools (6 lean + 3 graph, GRAPH-line gated — the 0.17 shape)
- eval_config.yaml: 240s / 36 calls / 6 MIN / 80 turns (the finisher: 8-min risks 12.4-14.2h whole-submission error)
- configs/sampling.yaml: temp 0.2 / top_p 0.95 / out 4096 / thinking 2048
- prompts/system.md: LOCATE 1-3 -> EDIT by 12 -> single-shot SUBMIT; targeted-only; never-bare-pytest; never-touch-tests; repeat-stop; call-10 gate; gated 3R overtime; compaction5+bounded-reads+issue-pinned; GRAPH-line; /tmp-only.
- NO LoRA vendored (D11-vetoed). 234MB adapter NOT in repo (over GitHub 100MB/file sanity + tab-crash risk) — reference: Kaggle Models scottweeden/gemma-4-31b-swe-tool-use-lora, mount via Add Input > Models, stage() per writeup cell20.
- NO reviewer subagent in core (gated, wiring unproven) — skills-updated/ has reviewer-ready prompts as option.

## docs/ — GRAFTS-MISSED + 017-AUTOPSY + LORA-FREE + SCAVENGE
## yoink-all-hutterstyle.zip — full 166-file haul, DEFLATE-9 (1.12MB, ratio 0.453)
## plus-winshot.zip — fire-ready bundle zip

## push (operator, tokens 401 at last check — refresh first)
gh repo create gemma-winshot-public --public --source=scratch/gemma/public-repo --push
