# qwen38-4b-distill — 実測ログ / Measured Log

- モデル / Model: `hf.co/empero-ai/Qwen3.8-4B-Distill-GGUF:Q4_K_M`
- 測定日 / Measured on: 2026-08-23

## 実行条件 / Run Conditions

| 項目 / Item | 値 / Value |
|---|---|
| ランタイム / Runtime | Ollama (digest で固定 / pinned by digest) |
| モデル digest / Model digest | `56c1b4004458` |
| 量子化 / Quantization | Q4_K_M 統一 (無ければ最も近いもの / nearest available) |
| temperature / top_p | 0.2 / 0.9 |
| seed | 42 |
| max_tokens / context | 4096 / 8192 |
| 試行回数 / Attempts | 各問1件のみ・リトライなし / one record per task, no retry |
| 測定日 / Measured on | 2026-08-23 |

## 6問の実測 / Measurements (6 tasks)

| 問題 / Task | tok/s | 出力文字数 / Output chars |
|---|---|---|
| A1 | 275.5 | 4185 |
| A2 | 256.0 | 166 |
| B1 | 261.9 | 602 |
| B2 | 261.6 | 592 |
| C1 | 280.9 | 2517 |
| C2 | 245.5 | 48 |

tok/s は1リクエストの初期化コストを含むため、**問題間で順位を比較しないでください**。短い出力ほど低く出ます。
Each tok/s includes per-request startup cost, so **do not rank tasks against each other**; shorter outputs read lower.

## 再現方法 / Reproducing this run

```sh
# モデル digest: 56c1b4004458 (この digest のときの実測です)
# Model digest: 56c1b4004458 — these numbers are from this digest
ollama run hf.co/empero-ai/Qwen3.8-4B-Distill-GGUF:Q4_K_M
```

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
