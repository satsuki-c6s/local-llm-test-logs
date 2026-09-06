# v4flash-iq1s-cluster — 実測ログ / Measured Log

- モデル / Model: `DeepSeek-V4-Flash-0731-UD-IQ1_S`
- 測定日 / Measured on: 2026-08-27

## 実行条件 / Run Conditions

| 項目 / Item | 値 / Value |
|---|---|
| ランタイム / Runtime | `llama.cpp RPC (5 nodes)` |
| モデル digest / Model digest | — (この回は未記録 / not recorded) |
| top_p | 0.9 |
| temperature / seed | 指定不可 (ランタイムが未サポート) / not settable (unsupported by the runtime) |
| max_tokens / context | 4096 / 8192 |
| 試行回数 / Attempts | 各問1件の記録 / one record per task |
| 測定日 / Measured on | 2026-08-27 |

> **この回は他の回と同じ土俵ではありません / Not on the same footing as other runs**
> - thinking ON で実行した初回。シリーズの凍結条件 (think:false) と異なる
> - 正式採点は --reasoning off で再実行した v4flash-iq1s-cluster-nothink を正とする
> - C1 は思考ON/OFFの両条件で捏造が再現しており、この回だけの傾向ではない
> - llama.cpp RPC 5台分散 (Ollama ではない)。VRAM は5ノード合計の確保量で他行と比較不可

## 6問の実測 / Measurements (6 tasks)

| 問題 / Task | tok/s | 出力文字数 / Output chars |
|---|---|---|
| A1 | 4.8 | 1838 |
| A2 | 5.9 | 147 |
| B1 | 5.6 | 186 |
| B2 | 4.6 | 265 |
| C1 | 5.1 | 1712 |
| C2 | 7.8 | 33 |

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
