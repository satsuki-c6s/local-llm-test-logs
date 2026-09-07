# sarashina2.2-1b — 実測ログ / Measured Log

- モデル / Model: `hf.co/mmnga/sarashina2.2-1b-instruct-v0.1-gguf:Q4_K_M`
- 測定日 / Measured on: 2026-08-03

## 実行条件 / Run Conditions

| 項目 / Item | 値 / Value |
|---|---|
| ランタイム / Runtime | Ollama (digest で固定 / pinned by digest) |
| モデル digest / Model digest | `3e7f8ed6d72b` |
| 量子化 / Quantization | Q4_K_M 統一 (無ければ最も近いもの / nearest available) |
| temperature / top_p | 0.2 / 0.9 |
| seed | 42 |
| max_tokens / context | 4096 / 8192 |
| 試行回数 / Attempts | 各問1件のみ・リトライなし / one record per task, no retry |
| 測定日 / Measured on | 2026-08-03 |

> **この回は他の回と同じ土俵ではありません / Not on the same footing as other runs**
> - KV キャッシュ q8_0 非互換のため f16 で実行。速度・VRAM を他モデルと並べるときは条件差の明記が必須

## 6問の実測 / Measurements (6 tasks)

| 問題 / Task | tok/s | 出力文字数 / Output chars |
|---|---|---|
| A1 | 561.2 | 1414 |
| A2 | 534.5 | 183 |
| B1 | 448.0 | 214 |
| B2 | 480.1 | 196 |
| C1 | 567.4 | 2083 |
| C2 | 572.0 | 156 |

tok/s は1リクエストの初期化コストを含むため、**問題間で順位を比較しないでください**。短い出力ほど低く出ます。
Each tok/s includes per-request startup cost, so **do not rank tasks against each other**; shorter outputs read lower.

## 再現方法 / Reproducing this run

```sh
# モデル digest: 3e7f8ed6d72b (この digest のときの実測です)
# Model digest: 3e7f8ed6d72b — these numbers are from this digest
ollama run hf.co/mmnga/sarashina2.2-1b-instruct-v0.1-gguf:Q4_K_M
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
