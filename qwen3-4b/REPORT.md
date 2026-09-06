# qwen3-4b — 実測ログ / Measured Log

- モデル / Model: `qwen3:4b`
- 測定日 / Measured on: 2026-07-30

## 実行条件 / Run Conditions

| 項目 / Item | 値 / Value |
|---|---|
| ランタイム / Runtime | Ollama (digest で固定 / pinned by digest) |
| モデル digest / Model digest | `359d7dd4bcda` |
| 量子化 / Quantization | Q4_K_M 統一 (無ければ最も近いもの / nearest available) |
| temperature / top_p | 0.2 / 0.9 |
| seed | 42 |
| max_tokens / context | 4096 / 8192 |
| 試行回数 / Attempts | 各問1件のみ・リトライなし / one record per task, no retry |
| 測定日 / Measured on | 2026-07-30 |

## 6問の実測 / Measurements (6 tasks)

| 問題 / Task | tok/s | 出力文字数 / Output chars |
|---|---|---|
| A1 | 293.2 | 16174 |
| A2 | 304.5 | 172 |
| B1 | 306.3 | 101 |
| B2 | 303.4 | 295 |
| C1 | 302.6 | 2009 |
| C2 | 292.1 | 10097 |

tok/s は1リクエストの初期化コストを含むため、**問題間で順位を比較しないでください**。短い出力ほど低く出ます。
Each tok/s includes per-request startup cost, so **do not rank tasks against each other**; shorter outputs read lower.

## 再現方法 / Reproducing this run

```sh
# モデル digest: 359d7dd4bcda (この digest のときの実測です)
# Model digest: 359d7dd4bcda — these numbers are from this digest
ollama run qwen3:4b
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
