# llmjp4-33b-thinking-llamacpp — 実測ログ / Measured Log

- モデル / Model: `llm-jp-4-33b-thinking`
- 測定日 / Measured on: 2026-08-21

## 実行条件 / Run Conditions

| 項目 / Item | 値 / Value |
|---|---|
| ランタイム / Runtime | `llama.cpp (/models/sha256-12c23619261c824f88facec565a4b6750d2b0872db7e57f6289ad677822e00dd)` |
| モデル digest / Model digest | — (この回は未記録 / not recorded) |
| top_p | 0.9 |
| temperature / seed | 指定不可 (ランタイムが未サポート) / not settable (unsupported by the runtime) |
| max_tokens / context | 4096 / 8192 |
| 試行回数 / Attempts | 各問1件の記録 / one record per task |
| 測定日 / Measured on | 2026-08-21 |

## 6問の実測 / Measurements (6 tasks)

| 問題 / Task | tok/s | 出力文字数 / Output chars |
|---|---|---|
| A1 | 65.5 | 5422 |
| A2 | 58.5 | 122 |
| B1 | 64.7 | 666 |
| B2 | 64.1 | 376 |
| C1 | 64.3 | 10363 |
| C2 | 64.2 | 52 |

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
