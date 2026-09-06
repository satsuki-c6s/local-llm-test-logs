# gemma4-31b — 実測ログ / Measured Log

- モデル / Model: `gemma4:31b`
- 測定日 / Measured on: 2026-07-27

## 実行条件 / Run Conditions

| 項目 / Item | 値 / Value |
|---|---|
| ランタイム / Runtime | Ollama (digest で固定 / pinned by digest) |
| モデル digest / Model digest | `6316f0629137` |
| 量子化 / Quantization | Q4_K_M 統一 (無ければ最も近いもの / nearest available) |
| temperature / top_p | 0.2 / 0.9 |
| seed | 42 |
| max_tokens / context | 4096 / 8192 |
| 試行回数 / Attempts | 各問1件のみ・リトライなし / one record per task, no retry |
| 測定日 / Measured on | 2026-07-27 |

> 生ログに記録された digest `5571076f3d70` は誤りで、正しくは `6316f0629137` です (生ログが gemma4:26b の digest を記録している。VRAM 25.9GB / 56.5 tok/s は 31b の実測値で 26b と明確に異なるため、測定自体は 31b で正しい)。 / The digest recorded in the raw logs (`5571076f3d70`) is wrong; the correct one is `6316f0629137`.

## 6問の実測 / Measurements (6 tasks)

| 問題 / Task | tok/s | 出力文字数 / Output chars |
|---|---|---|
| A1 | 56.5 | 2834 |
| A2 | 55.7 | 134 |
| B1 | 57.2 | 973 |
| B2 | 57.3 | 145 |
| C1 | 56.8 | 2090 |
| C2 | 56.1 | 50 |

tok/s は1リクエストの初期化コストを含むため、**問題間で順位を比較しないでください**。短い出力ほど低く出ます。
Each tok/s includes per-request startup cost, so **do not rank tasks against each other**; shorter outputs read lower.

## 再現方法 / Reproducing this run

```sh
# モデル digest: 6316f0629137 (この digest のときの実測です)
# Model digest: 6316f0629137 — these numbers are from this digest
ollama run gemma4:31b
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
