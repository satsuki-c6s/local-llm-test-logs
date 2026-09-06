# diffusiongemma-26b — 実測ログ / Measured Log

- モデル / Model: `diffusiongemma`
- 測定日 / Measured on: 2026-07-28

## 実行条件 / Run Conditions

| 項目 / Item | 値 / Value |
|---|---|
| ランタイム / Runtime | `vllm 0.22.1rc1.dev357+g74b5964f0` |
| モデル digest / Model digest | — (この回は未記録 / not recorded) |
| top_p | 0.9 |
| temperature / seed | 指定不可 (ランタイムが未サポート) / not settable (unsupported by the runtime) |
| max_tokens / context | 4096 / 8192 |
| 試行回数 / Attempts | 各問1件の記録 / one record per task |
| 測定日 / Measured on | 2026-07-28 |

> **この回は他の回と同じ土俵ではありません / Not on the same footing as other runs**
> - vLLM で実行。Ollama 勢と同じ土俵で比較できない
> - nvidia-smi の 32,040 MiB は --gpu-memory-utilization 0.9 の先取り確保量であって使用量ではない。VRAM 列・ランキングには載せない
> - 必要量の目安は重みサイズ (NVFP4 18.9GB) を使う

## 6問の実測 / Measurements (6 tasks)

| 問題 / Task | tok/s | 出力文字数 / Output chars |
|---|---|---|
| A1 | 126.1 | 2060 |
| A2 | 413.7 | 183 |
| B1 | 496.8 | 877 |
| B2 | 494.3 | 182 |
| C1 | 704.5 | 2278 |
| C2 | 166.7 | 49 |

tok/s は1リクエストの初期化コストを含むため、**問題間で順位を比較しないでください**。短い出力ほど低く出ます。
Each tok/s includes per-request startup cost, so **do not rank tasks against each other**; shorter outputs read lower.

## 再現方法 / Reproducing this run

この回は digest を記録していないため、コマンドで固定できる再現手順がありません。
実行時の構成は上のモデル名と実行条件の表がすべてです。
This run has no recorded digest, so there is no command that pins it. The model name and the run-conditions table above are the full record.

## 生ログ / Raw logs

- [`A1.md`](./A1.md)
- [`A2.md`](./A2.md)
- [`B1.md`](./B1.md)
- [`B2.md`](./B2.md)
- [`C1.md`](./C1.md)
- [`C2.md`](./C2.md)
- [`_summary.json`](./_summary.json)

---

動画リンクは別途 model-map から付与する (未実装) / Video link to be added from the model map (not yet implemented).
