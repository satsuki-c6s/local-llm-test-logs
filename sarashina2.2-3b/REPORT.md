# sarashina2.2-3b — 実測ログ / Measured Log

- モデル / Model: `hf.co/mmnga/sarashina2.2-3b-instruct-v0.1-gguf:Q4_K_M`
- 測定日 / Measured on: 2026-07-27

## 実行条件 / Run Conditions

| 項目 / Item | 値 / Value |
|---|---|
| ランタイム / Runtime | Ollama (digest で固定 / pinned by digest) |
| モデル digest / Model digest | `4f06c3a02d13` |
| 量子化 / Quantization | Q4_K_M 統一 (無ければ最も近いもの / nearest available) |
| temperature / top_p | 0.2 / 0.9 |
| seed | 42 |
| max_tokens / context | 4096 / 8192 |
| 試行回数 / Attempts | 各問1件のみ・リトライなし / one record per task, no retry |
| 測定日 / Measured on | 2026-07-27 |

## 6問の実測 / Measurements (6 tasks)

| 問題 / Task | tok/s | 出力文字数 / Output chars |
|---|---|---|
| A1 | 112.5 | 1230 |
| A2 | 138.7 | 176 |
| B1 | 146.0 | 230 |
| B2 | 143.0 | 213 |
| C1 | 98.9 | 2277 |
| C2 | 145.4 | 139 |

tok/s は1リクエストの初期化コストを含むため、**問題間で順位を比較しないでください**。短い出力ほど低く出ます。
Each tok/s includes per-request startup cost, so **do not rank tasks against each other**; shorter outputs read lower.

## 再現方法 / Reproducing this run

```sh
# モデル digest: 4f06c3a02d13 (この digest のときの実測です)
# Model digest: 4f06c3a02d13 — these numbers are from this digest
ollama run hf.co/mmnga/sarashina2.2-3b-instruct-v0.1-gguf:Q4_K_M
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
