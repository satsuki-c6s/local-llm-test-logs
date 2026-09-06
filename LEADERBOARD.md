# 実測一覧 / Measurement Index

**これは速度と実行条件の記録であって、品質ランキングではありません。**
採点結果・採否の判定はここには載せていません。実行条件はモデルごとに違うので、行同士をそのまま優劣として読まないでください。
**This is a record of speed and run conditions, not a quality ranking.** Scores and adoption decisions are deliberately excluded, and run conditions differ per row, so rows are not directly comparable.

## 6問シリーズ (A1〜C2) / Six-question series

**実行環境が違う行は同じ土俵ではありません。** 環境列が同じ行同士だけを比べてください。
**Rows with different run environments are not on the same footing.** Compare only within the same environment.

| モデル / Model | 実行環境 / Environment | digest | 測定日 / Measured on | 6問平均 tok/s / Mean tok/s over 6 tasks | レポート / Report |
|---|---|---|---|---|---|
| `apodex-1.1-mini:latest` | Ollama 単機 / single machine | `5e4e1690264b` | 2026-08-28 | 233.5 | [REPORT](./apodex-11-mini/REPORT.md) |
| `hf.co/prism-ml/Bonsai-27B-gguf:Q1_0` | Ollama 単機 / single machine | `b5556075df5e` | 2026-07-27 | 145.5 | [REPORT](./bonsai-27b/REPORT.md) |
| `gemma3:12b` | Ollama 単機 / single machine | `f4031aab637d` | 2026-07-30 | 121.7 | [REPORT](./gemma3-12b/REPORT.md) |
| `gemma3:1b` | Ollama 単機 / single machine | `8648f39daa8f` | 2026-07-31 | 307.6 | [REPORT](./gemma3-1b/REPORT.md) |
| `gemma3:27b` | Ollama 単機 / single machine | `a418f5838eaf` | 2026-07-30 | 70.1 | [REPORT](./gemma3-27b/REPORT.md) |
| `gemma3:4b` | Ollama 単機 / single machine | `a2af6cc3eb7f` | 2026-07-30 | 206.3 | [REPORT](./gemma3-4b/REPORT.md) |
| `gemma4:12b` | Ollama 単機 / single machine | `4eb23ef187e2` | 2026-07-27 | 98.1 | [REPORT](./gemma4-12b/REPORT.md) |
| `gemma4:26b` | Ollama 単機 / single machine | `5571076f3d70` | 2026-07-27 | 183.3 | [REPORT](./gemma4-26b/REPORT.md) |
| `gemma4-26b-qat:q4_0` | Ollama 単機 / single machine | `2f18146ba6e9` | 2026-09-01 | 203.1 | [REPORT](./gemma4-26b-qat-q4_0/REPORT.md) |
| `gemma4-26b-unsloth:UD-Q4_K_XL` | Ollama 単機 / single machine | `3758347de7f7` | 2026-09-01 | 183.0 | [REPORT](./gemma4-26b-unsloth-udq4kxl/REPORT.md) |
| `gemma4:31b` | Ollama 単機 / single machine | `6316f0629137` | 2026-07-27 | 56.6 | [REPORT](./gemma4-31b/REPORT.md) |
| `gemma4:e2b` | Ollama 単機 / single machine | `7fbdbf8f5e45` | 2026-07-31 | 238.0 | [REPORT](./gemma4-e2b/REPORT.md) |
| `gemma4:e4b` | Ollama 単機 / single machine | `c6eb396dbd59` | 2026-07-31 | 175.3 | [REPORT](./gemma4-e4b/REPORT.md) |
| `hf.co/unsloth/GLM-4.7-Flash-GGUF:Q4_K_M` | Ollama 単機 / single machine | `ae19295826a5` | 2026-07-27 | 197.8 | [REPORT](./glm-4.7-flash/REPORT.md) |
| `gpt-oss:20b` | Ollama 単機 / single machine | `17052f91a42e` | 2026-07-27 | 222.4 | [REPORT](./gpt-oss-20b/REPORT.md) |
| `hf.co/bloomer010/Ling-3.0-tiny-GGUF:Q4_K_M` | Ollama 単機 / single machine | `331a3257d548` | 2026-08-22 | 305.3 | [REPORT](./ling30-tiny/REPORT.md) |
| `mistral-small` | Ollama 単機 / single machine | `8039dd90c113` | 2026-07-27 | 84.6 | [REPORT](./mistral-small/REPORT.md) |
| `nemotron-3-nano:latest` | Ollama 単機 / single machine | `b725f1117407` | 2026-07-27 | 258.3 | [REPORT](./nemotron-3-nano/REPORT.md) |
| `nemotron-3-nano:4b` | Ollama 単機 / single machine | `6cc467f05439` | 2026-08-03 | 305.3 | [REPORT](./nemotron-3-nano-4b/REPORT.md) |
| `nemotron-3.5-lightning:30b` | Ollama 単機 / single machine | `e7a64ff15fb1` | 2026-08-12 | 128.7 | [REPORT](./nemotron-3.5-lightning-30b/REPORT.md) |
| `hf.co/ornith-ai/Ornith-1.5-35B-A3B-GGUF:Q4_K_M` | Ollama 単機 / single machine | `67a4c8ba6a74` | 2026-08-20 | 254.0 | [REPORT](./ornith15-35b-a3b/REPORT.md) |
| `hf.co/ornith-ai/Ornith-1.5-9B-GGUF:Q4_K_M` | Ollama 単機 / single machine | `803aeaf6af02` | 2026-08-20 | 197.4 | [REPORT](./ornith15-9b/REPORT.md) |
| `phi4:14B` | Ollama 単機 / single machine ⚠ 条件差あり / differing conditions | `ac896e5b8b34` | 2026-08-03 | 143.0 | [REPORT](./phi-4-14b/REPORT.md) |
| `phi4-mini:3.8b` | Ollama 単機 / single machine | `78fad5d182a7` | 2026-08-03 | 291.5 | [REPORT](./phi-4-mini/REPORT.md) |
| `qwen3:0.6b` | Ollama 単機 / single machine | `7df6b6e09427` | 2026-07-30 | 560.3 | [REPORT](./qwen3-0.6b/REPORT.md) |
| `qwen3:1.7b` | Ollama 単機 / single machine | `8f68893c685c` | 2026-07-30 | 441.9 | [REPORT](./qwen3-1.7b/REPORT.md) |
| `qwen3:14b` | Ollama 単機 / single machine | `bdbd181c33f2` | 2026-07-30 | 137.8 | [REPORT](./qwen3-14b/REPORT.md) |
| `qwen3:30b-a3b` | Ollama 単機 / single machine | `ad815644918f` | 2026-07-27 | 284.4 | [REPORT](./qwen3-30b-a3b/REPORT.md) |
| `qwen3:32b` | Ollama 単機 / single machine | `030ee887880f` | 2026-07-30 | 67.5 | [REPORT](./qwen3-32b/REPORT.md) |
| `qwen3:4b` | Ollama 単機 / single machine | `359d7dd4bcda` | 2026-07-30 | 300.3 | [REPORT](./qwen3-4b/REPORT.md) |
| `qwen3:8b` | Ollama 単機 / single machine | `500a1f067a9f` | 2026-07-30 | 214.4 | [REPORT](./qwen3-8b/REPORT.md) |
| `qwen3.5:0.8b` | Ollama 単機 / single machine | `f3817196d142` | 2026-07-28 | 410.3 | [REPORT](./qwen3.5-0.8b/REPORT.md) |
| `qwen3.5:27b` | Ollama 単機 / single machine | `7653528ba5cb` | 2026-07-28 | 68.2 | [REPORT](./qwen3.5-27b/REPORT.md) |
| `qwen3.5:2b` | Ollama 単機 / single machine | `324d162be6ca` | 2026-07-28 | 314.1 | [REPORT](./qwen3.5-2b/REPORT.md) |
| `qwen3.5:35b` | Ollama 単機 / single machine | `3460ffeede54` | 2026-07-28 | 219.3 | [REPORT](./qwen3.5-35b/REPORT.md) |
| `qwen3.5:4b` | Ollama 単機 / single machine | `2a654d98e6fb` | 2026-07-28 | 245.9 | [REPORT](./qwen3.5-4b/REPORT.md) |
| `qwen3.5:9b` | Ollama 単機 / single machine | `6488c96fa5fa` | 2026-07-28 | 184.7 | [REPORT](./qwen3.5-9b/REPORT.md) |
| `qwen3.6:27b` | Ollama 単機 / single machine | `a50eda8ed977` | 2026-07-27 | 68.7 | [REPORT](./qwen3.6-27b/REPORT.md) |
| `qwen3.6:35b` | Ollama 単機 / single machine | `07d35212591f` | 2026-07-27 | 186.0 | [REPORT](./qwen3.6-35b/REPORT.md) |
| `qwen3.8:27b-q4_K_M` | Ollama 単機 / single machine | `25b843619e94` | 2026-08-15 | 76.1 | [REPORT](./qwen38-27b/REPORT.md) |
| `hf.co/TeichAI/Qwen3.8-27B-Fable-Distill-GGUF:Q4_K_M` | Ollama 単機 / single machine | `5c921af2fe5c` | 2026-08-22 | 75.8 | [REPORT](./qwen38-27b-fable-distill/REPORT.md) |
| `qwen38-27b-gsq-rco-iq3xxs` | Ollama 単機 / single machine | `bfc8ed176534` | 2026-09-01 | 98.9 | [REPORT](./qwen38-27b-gsq-rco/REPORT.md) |
| `hf.co/OBLITERATUS/Qwen3.8-27B-OBLITERATED:Q4_K_M` | Ollama 単機 / single machine | `199e5fc395d9` | 2026-08-26 | 76.6 | [REPORT](./qwen38-27b-obliterated/REPORT.md) |
| `hf.co/empero-ai/Qwen3.8-2B-Distill-GGUF:Q4_K_M` | Ollama 単機 / single machine | `98e87c255611` | 2026-08-23 | 415.0 | [REPORT](./qwen38-2b-distill/REPORT.md) |
| `hf.co/empero-ai/Qwen3.8-4B-Distill-GGUF:Q4_K_M` | Ollama 単機 / single machine | `56c1b4004458` | 2026-08-23 | 263.6 | [REPORT](./qwen38-4b-distill/REPORT.md) |
| `hf.co/empero-ai/Qwen3.8-9B-Distill-GGUF:Q4_K_M` | Ollama 単機 / single machine | `9ce406b4f20e` | 2026-08-22 | 196.3 | [REPORT](./qwen38-9b-distill/REPORT.md) |
| `qwen38-whittle-moe-27b` | Ollama 単機 / single machine | `44d7b48ebc08` | 2026-09-01 | 87.1 | [REPORT](./qwen38-whittle-moe-27b/REPORT.md) |
| `hf.co/mmnga/sarashina2.2-0.5b-instruct-v0.1-gguf:Q4_K_M` | Ollama 単機 / single machine ⚠ 条件差あり / differing conditions | `ee215dc96c54` | 2026-08-03 | 622.5 | [REPORT](./sarashina2.2-0.5b/REPORT.md) |
| `hf.co/mmnga/sarashina2.2-1b-instruct-v0.1-gguf:Q4_K_M` | Ollama 単機 / single machine ⚠ 条件差あり / differing conditions | `3e7f8ed6d72b` | 2026-08-03 | 527.2 | [REPORT](./sarashina2.2-1b/REPORT.md) |
| `hf.co/mmnga/sarashina2.2-3b-instruct-v0.1-gguf:Q4_K_M` | Ollama 単機 / single machine | `4f06c3a02d13` | 2026-07-27 | 130.8 | [REPORT](./sarashina2.2-3b/REPORT.md) |
| `diffusiongemma` | `vllm 0.22.1rc1.dev357+g74b5964f0` ⚠ 条件差あり / differing conditions | — | 2026-07-28 | 400.3 | [REPORT](./diffusiongemma-26b/REPORT.md) |
| `flashnext-exl3-3.05bpw` | `exllamav3/TabbyAPI (flashnext-exl3-3.05bpw) max_seq_len=8192 cache=FP16` | — | 2026-09-03 | 5.2 | [REPORT](./flashnext-exl3-c3-off/REPORT.md) |
| `flashnext-iq3xxs` | `llama.cpp (<models>/Qwen3.8-Flash-Next-UD-IQ3_XXS-00001-of-00003.gguf)` | — | 2026-09-04 | 17.4 | [REPORT](./flashnext-iq3-c1-off/REPORT.md) |
| `flashnext-iq3xxs` | `llama.cpp (<models>/Qwen3.8-Flash-Next-UD-IQ3_XXS-00001-of-00003.gguf)` | — | 2026-09-04 | 28.5 | [REPORT](./flashnext-iq3-c2-on/REPORT.md) |
| `flashnext-iq3xxs-5080-cpumoe` | `llama.cpp (<models>/Qwen3.8-Flash-Next-UD-IQ3_XXS-00001-of-00003.gguf)` | — | 2026-09-02 | 20.7 | [REPORT](./flashnext-iq3xxs-5080/REPORT.md) |
| `flashnext-iq3xxs-ncmoe36` | `llama.cpp (<models>/Qwen3.8-Flash-Next-UD-IQ3_XXS-00001-of-00003.gguf)` | — | 2026-09-02 | 10.8 | [REPORT](./flashnext-iq3xxs-single/REPORT.md) |
| `Qwen3.6-35B-A3B-FP8` | `llamacpp` | — | 2026-09-05 | 129.3 | [REPORT](./freetoken-qwen36-fp8-6q/REPORT.md) |
| `Qwen3.6-35B-A3B-NVFP4` | `llamacpp` | — | 2026-09-05 | 123.7 | [REPORT](./freetoken-qwen36-nvfp4-6q/REPORT.md) |
| `glm-5.3-flash-ud-iq1s` | `llama.cpp-rpc` | — | 2026-08-28 | 3.7 | [REPORT](./glm53-flash-iq1s-cluster-nothink/REPORT.md) |
| `llm-jp-4-33b-thinking` | `llama.cpp (/models/sha256-12c23619261c824f88facec565a4b6750d2b0872db7e57f6289ad677822e00dd)` | — | 2026-08-21 | 63.5 | [REPORT](./llmjp4-33b-thinking-llamacpp/REPORT.md) |
| `muse-glimmer-30B` | `llama.cpp (D:/ai/models/muse-glimmer/muse-glimmer-30B-kquant-17gb.gguf)` | — | 2026-08-11 | 71.4 | [REPORT](./muse-glimmer-30b/REPORT.md) |
| `escha-qwen38-27b-w2` | `escha-sglang` | — | 2026-08-24 | 73.2 | [REPORT](./qwen38-27b-escha-w2/REPORT.md) |
| `Qwen3.8-Flash-Next-UD-IQ1_M` | `llama.cpp RPC (5 nodes)` | — | 2026-08-27 | 2.7 | [REPORT](./qwen38-flash-next-iq1m-cluster-nothink/REPORT.md) |
| `Qwen3.8-Flash-Next-UD-IQ1_M` | `llama.cpp-rpc` ⚠ 条件差あり / differing conditions | — | 2026-08-27 | 19.2 | [REPORT](./qwen38-flash-next-iq1m-single212/REPORT.md) |
| `DeepSeek-V4-Flash-0731-UD-IQ1_S` | `llama.cpp RPC (5 nodes)` ⚠ 条件差あり / differing conditions | — | 2026-08-27 | 5.6 | [REPORT](./v4flash-iq1s-cluster/REPORT.md) |
| `DeepSeek-V4-Flash-0731-UD-IQ1_S` | `llama.cpp RPC (5 nodes)` | — | 2026-08-27 | 6.3 | [REPORT](./v4flash-iq1s-cluster-nothink/REPORT.md) |
| `DeepSeek-R1-Distill-Llama-70B-UD-Q4_K_XL (mesh-llm 4台クラスタ)` | クラスタ / cluster | — | 2026-08-06 | — (未記録 / not recorded) | [REPORT](./deepseek-r1-distill-llama-70b-cluster/REPORT.md) |
| `gpt-oss-120b-UD-Q4_K_XL (mesh-llm 4台クラスタ)` | クラスタ / cluster | — | 2026-08-07 | — (未記録 / not recorded) | [REPORT](./gpt-oss-120b-cluster/REPORT.md) |
| `Llama-4-Scout-17B-16E-Instruct-UD-Q4_K_XL (mesh-llm クラスタ・4台参加)` | クラスタ / cluster | — | 2026-08-08 | — (未記録 / not recorded) | [REPORT](./llama-4-scout-cluster/REPORT.md) |
| `Qwen3-Next-80B-A3B-Instruct-UD-Q4_K_XL (mesh-llm クラスタ・3台参加)` | クラスタ / cluster | — | 2026-08-07 | — (未記録 / not recorded) | [REPORT](./qwen3-next-80b-cluster/REPORT.md) |
| `Qwen3-Next-80B-A3B-Thinking-UD-Q4_K_XL (mesh-llm クラスタ・3台参加)` | クラスタ / cluster | — | 2026-08-08 | — (未記録 / not recorded) | [REPORT](./qwen3-next-80b-thinking-cluster/REPORT.md) |

tok/s が «—» の行はクラスタ実行で、tok/s を記録していません (出力文字数からは換算できません)。
Rows with «—» are cluster runs that did not record tok/s; it cannot be derived from character counts.

### ⚠ 条件差のある行 / Rows with differing conditions

環境列が同じでも、以下の行は他と同じ土俵ではありません。
Even within the same environment column, these rows are not on the same footing as the others.

- `phi4:14B`
  - KV キャッシュ q8_0 非互換のため f16 で実行。速度・VRAM を他モデルと並べるときは条件差の明記が必須
- `hf.co/mmnga/sarashina2.2-0.5b-instruct-v0.1-gguf:Q4_K_M`
  - KV キャッシュ q8_0 非互換のため f16 で実行。速度・VRAM を他モデルと並べるときは条件差の明記が必須
- `hf.co/mmnga/sarashina2.2-1b-instruct-v0.1-gguf:Q4_K_M`
  - KV キャッシュ q8_0 非互換のため f16 で実行。速度・VRAM を他モデルと並べるときは条件差の明記が必須
- `diffusiongemma`
  - vLLM で実行。Ollama 勢と同じ土俵で比較できない
  - nvidia-smi の 32,040 MiB は --gpu-memory-utilization 0.9 の先取り確保量であって使用量ではない。VRAM 列・ランキングには載せない
  - 必要量の目安は重みサイズ (NVFP4 18.9GB) を使う
- `Qwen3.8-Flash-Next-UD-IQ1_M`
  - 5台RPCクラスターではなく単機 (212, VRAM32GB+RAM64GB=96GB) の参考実行。正式採点はクラスター (qwen38-flash-next-iq1m-cluster-nothink) を正とする
  - バックエンドが違う (単機 CUDA+CPU vs RPC分散) ため tok/s を並べて比較しない。単機は約8倍速いが同一条件ではない
  - 採点も◎3 △1 ×2 でクラスター側 (◎3 ○2 ×1) と異なる — 出力そのものが変わる
- `DeepSeek-V4-Flash-0731-UD-IQ1_S`
  - thinking ON で実行した初回。シリーズの凍結条件 (think:false) と異なる
  - 正式採点は --reasoning off で再実行した v4flash-iq1s-cluster-nothink を正とする
  - C1 は思考ON/OFFの両条件で捏造が再現しており、この回だけの傾向ではない
  - llama.cpp RPC 5台分散 (Ollama ではない)。VRAM は5ノード合計の確保量で他行と比較不可

## コード生成シリーズ (T1〜T3) / Code-generation series

課題数も測定条件も6問シリーズとは別です。上の表とは平均を比べないでください。
A different task set and different settings from the six-question series. Do not compare these means with the table above.

| モデル / Model | digest | 測定日 / Measured on | 3課題平均 tok/s / Mean tok/s over 3 tasks | レポート / Report |
|---|---|---|---|---|
| `devstral-small-2 (Ollama, dense 24B Apache-2.0, RTX 5090 単機)` | — | 2026-08-09 | 88.5 | [REPORT](./devstral-small-2-codegen/REPORT.md) |
| `gemma3:12b (Ollama, dense 12B Gemma利用規約, RTX 5090 単機)` | — | 2026-08-09 | 122.0 | [REPORT](./gemma3-12b-codegen/REPORT.md) |
| `gemma3:27b (Ollama, dense 27B Gemma利用規約, RTX 5090 単機)` | — | 2026-08-09 | 70.6 | [REPORT](./gemma3-27b-codegen/REPORT.md) |
| `gemma4:12b (Ollama, dense 12B Apache-2.0, RTX 5090 単機)` | — | 2026-08-09 | 118.5 | [REPORT](./gemma4-12b-codegen/REPORT.md) |
| `gemma4:26b (Ollama, MoE 26B-A4B Apache-2.0, RTX 5090 単機)` | — | 2026-08-09 | 181.3 | [REPORT](./gemma4-26b-codegen/REPORT.md) |
| `gemma4:31b (Ollama, dense Q4_K_M 19GB, RTX 5090 単機)` | — | 2026-08-08 | 59.3 | [REPORT](./gemma4-31b-codegen/REPORT.md) |
| `gemma4:e4b (Ollama, Q4_K_M 9.6GB, RTX 5090 単機)` | — | 2026-08-08 | 179.4 | [REPORT](./gemma4-e4b-codegen/REPORT.md) |
| `gpt-oss-120b (Q4_K_XL 62.6GB / 36層, Apache-2.0, GPU4台クラスタ)` | — | 2026-08-10 | — (未記録 / not recorded) | [REPORT](./gpt-oss-120b-cluster-codegen/REPORT.md) |
| `qwen2.5-coder:1.5b (Ollama, Q4_K_M 1GB, RTX 5090 単機)` | — | 2026-08-08 | 434.7 | [REPORT](./qwen25-coder-15b-codegen/REPORT.md) |
| `qwen2.5-coder:32b (Ollama, dense Q4_K_M 20GB, RTX 5090 単機)` | — | 2026-08-08 | 66.5 | [REPORT](./qwen25-coder-32b-codegen/REPORT.md) |
| `qwen2.5-coder:7b (Ollama, Q4_K_M 4.7GB, RTX 5090 単機)` | — | 2026-08-08 | 222.5 | [REPORT](./qwen25-coder-7b-codegen/REPORT.md) |
| `qwen3-coder:30b (Ollama, Q4_K_M 18GB, RTX 5090 単機)` | — | 2026-08-08 | 260.9 | [REPORT](./qwen3-coder-30b-codegen/REPORT.md) |
| `Qwen3-Coder-Next (Q4_K_XL 49.9GB / 48層, Apache-2.0, GPU4台クラスタ)` | — | 2026-08-10 | — (未記録 / not recorded) | [REPORT](./qwen3-coder-next-cluster-codegen/REPORT.md) |
| `Qwen3-Next-80B-A3B-Thinking (Q4_K_XL 44GB / 48層, Apache-2.0, GPU4台クラスタ)` | — | 2026-08-10 | — (未記録 / not recorded) | [REPORT](./qwen3-next-80b-thinking-cluster-codegen/REPORT.md) |
| `qwen3.6:35b (Ollama, 汎用 A3B MoE Q4_K_M 23GB, RTX 5090 単機)` | — | 2026-08-08 | 226.3 | [REPORT](./qwen36-35b-codegen/REPORT.md) |
| `qwen3.8:27b-q4_K_M (Ollama 0.32.13, 汎用 dense 27B Q4_K_M 17GB, RTX 5090 単機)` | — | 2026-08-15 | 76.0 | [REPORT](./qwen38-27b-codegen/REPORT.md) |
| `EschaLabs/Qwen3.8-27B-Escha-W2 (escha 2bit 10.15GB, escha SGLang 1.2.0, RTX 5090 単機)` | — | 2026-08-25 | 82.0 | [REPORT](./qwen38-27b-escha-w2-codegen/REPORT.md) |
| `hf.co/TeichAI/Qwen3.8-27B-Fable-Distill-GGUF:Q4_K_M (Ollama 0.32.15, TeichAI による軽SFT・dense 27.8B Q4_K_M 17.4GB, RTX 5090 単機)` | — | 2026-08-22 | 73.9 | [REPORT](./qwen38-27b-fable-distill-codegen/REPORT.md) |
| `llama.cpp llama-server (PR ブランチ jkyamog/pr/flash-next-qsa-rotkv abdc7a0 = #27742+#27774 相当・Windows ネイティブ CUDA 13.1) / モデル unsloth/Qwen3.8-Flash-Next-GGUF UD-IQ1_M (74.5GB・48層) / RTX 5090 32GB + RAM 64GB 単機` | — | 2026-08-27 | 25.2 | [REPORT](./qwen38-flash-next-iq1m-single-codegen/REPORT.md) |

tok/s が «—» の行はクラスタ実行で、tok/s を記録していません (所要秒だけが記録にあります。各レポートを参照)。
Rows with «—» are cluster runs with no recorded tok/s; only elapsed seconds were logged (see each report).

## 保留 (採点なし) / On hold (not scored)

環境側の非互換で走らなかった回です。**モデルの成績ではないので上の表には入れていません。**
Runs blocked by runtime incompatibility. **These are not model results, so they are excluded from the tables above.**

| モデル / Model | 理由 / Reason | レポート / Report |
|---|---|---|
| `flashnext-exl3-c4-on` | 出力0文字の問題が 1 件あり、その tok/s は割り算で生まれた無効値です (実測値ではありません) | [REPORT](./flashnext-exl3-c4-on/REPORT.md) |
| `llm-jp-4-8b` | Ollama 0.32.4 で全問0文字 (即EOS)。非公式GGUF・公式GGUFの2系統で再現 | [REPORT](./llm-jp-4-8b/REPORT.md) |
| `qwen38-flash-next-iq1m-cluster` | thinking ON で実行 (シリーズの凍結条件 think:false と異なる)。A1・C2 は思考が max_tokens 4096 を使い切り本文0文字で、その tok/s は割り算で生まれた無効値。正式な採点は --reasoning off の qwen38-flash-next-iq1m-cluster-nothink を参照 | [REPORT](./qwen38-flash-next-iq1m-cluster/REPORT.md) |

---

動画リンクは別途 model-map から付与する (未実装) / Video links to be added from the model map (not yet implemented).
