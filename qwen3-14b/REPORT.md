# qwen3-14b — 実測ログ / Measured Log

- モデル / Model: `qwen3:14b`
- 測定日 / Measured on: 2026-07-30

## 実行条件 / Run Conditions

| 項目 / Item | 値 / Value |
|---|---|
| ランタイム / Runtime | Ollama (digest で固定 / pinned by digest) |
| モデル digest / Model digest | `bdbd181c33f2` |
| 量子化 / Quantization | Q4_K_M 統一 (無ければ最も近いもの / nearest available) |
| temperature / top_p | 0.2 / 0.9 |
| seed | 42 |
| max_tokens / context | 4096 / 8192 |
| 試行回数 / Attempts | 各問1件のみ・リトライなし / one record per task, no retry |
| 測定日 / Measured on | 2026-07-30 |

> 生ログに記録された digest `7df6b6e09427` は誤りで、正しくは `bdbd181c33f2` です (生ログが qwen3:0.6b の digest を記録している。Ollama がタグを qwen3:14B と正規化するため完全一致が外れ、前綴りフォールバックが別モデル行を拾った)。 / The digest recorded in the raw logs (`7df6b6e09427`) is wrong; the correct one is `bdbd181c33f2`.

## 6問の実測 / Measurements (6 tasks)

| 問題 / Task | tok/s | 出力文字数 / Output chars |
|---|---|---|
| A1 | 136.2 | 1482 |
| A2 | 138.4 | 128 |
| B1 | 137.4 | 199 |
| B2 | 138.1 | 374 |
| C1 | 137.6 | 2342 |
| C2 | 138.9 | 72 |

tok/s は1リクエストの初期化コストを含むため、**問題間で順位を比較しないでください**。短い出力ほど低く出ます。
Each tok/s includes per-request startup cost, so **do not rank tasks against each other**; shorter outputs read lower.

## 再現方法 / Reproducing this run

```sh
# モデル digest: bdbd181c33f2 (この digest のときの実測です)
# Model digest: bdbd181c33f2 — these numbers are from this digest
ollama run qwen3:14b
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
