# sarashina2.2-0.5b — 実測ログ / Measured Log

- モデル / Model: `hf.co/mmnga/sarashina2.2-0.5b-instruct-v0.1-gguf:Q4_K_M`
- 測定日 / Measured on: 2026-08-03

## 実行条件 / Run Conditions

| 項目 / Item | 値 / Value |
|---|---|
| ランタイム / Runtime | Ollama (digest で固定 / pinned by digest) |
| モデル digest / Model digest | `ee215dc96c54` |
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
| A1 | 644.1 | 2653 |
| A2 | 678.7 | 142 |
| B1 | 555.1 | 125 |
| B2 | 629.1 | 559 |
| C1 | 647.5 | 1871 |
| C2 | 580.3 | 186 |

tok/s は1リクエストの初期化コストを含むため、**問題間で順位を比較しないでください**。短い出力ほど低く出ます。
Each tok/s includes per-request startup cost, so **do not rank tasks against each other**; shorter outputs read lower.

## 再現方法 / Reproducing this run

```sh
# モデル digest: ee215dc96c54 (この digest のときの実測です)
# Model digest: ee215dc96c54 — these numbers are from this digest
ollama run hf.co/mmnga/sarashina2.2-0.5b-instruct-v0.1-gguf:Q4_K_M
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
