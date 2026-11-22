# LORA-ATTACH (fire-time, no bundle change)
Base model: gemma-4-31b-it-qat-w4a16-ct (unchanged in agent.yaml).
Attach at fire time via kernel Add-Models data-source mount (server-side, never download to browser):
- PRIMARY: scottweeden/gemma-4-31b-swe-tool-use-lora (r16/a32, trained on own resolved turns, base-string match). Single 0.17 vs our 0.13 floor (n=1, author agrees lucky draw; mean 0.14).
- OPTION B: robinamirbahar/gemma-4-31b-loop-breaker-lora (rank-4 main_lora + tool_lora; loop-breaker matches R3's observed temp-0 repeat failure).
Layout: adapters/main_lora/{adapter_config.json,adapter_model.safetensors}. Stage with writeup cell-20 pattern then serve vLLM --enable-lora. Costs 1 submission on convert-read; k4 first.
