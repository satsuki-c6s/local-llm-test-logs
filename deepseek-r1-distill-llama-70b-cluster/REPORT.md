# deepseek-r1-distill-llama-70b-cluster — 実測ログ / Measured Log

- モデル / Model: `DeepSeek-R1-Distill-Llama-70B-UD-Q4_K_XL (mesh-llm 4台クラスタ)`
- 測定日 / Measured on: 2026-08-06

## 実行条件 / Run Conditions

| 項目 / Item | 値 / Value |
|---|---|
| ランタイム・構成 / Runtime | 上のモデル名に併記 / stated in the model name above |
| モデル digest / Model digest | — (この回は未記録 / not recorded) |
| 試行回数 / Attempts | 各問1件の記録 / one record per task |
| 測定日 / Measured on | 2026-08-06 |

## 6問の実測 / Measurements (6 tasks)

| 問題 / Task | 所要秒 / Seconds | 出力文字数 / Output chars | 終了理由 / Finish |
|---|---|---|---|
| A1 | 174 | 2016 | stop |
| A2 | 552 | 130 | stop |
| B1 | 756 | 206 | stop |
| B2 | 1881 | 229 | stop |
| C1 | 1353 | 1583 | stop |
| C2 | 363 | 76 | stop |

この回は tok/s を記録していません。出力文字数はトークン数ではないので、ここから tok/s は換算できません。
This run did not record tok/s. Character counts are not token counts, so tok/s cannot be derived from them.

## 再現方法 / Reproducing this run

この回は digest を記録していないため、コマンドで固定できる再現手順がありません。
実行時の構成は上のモデル名と実行条件の表がすべてです。
This run has no recorded digest, so there is no command that pins it. The model name and the run-conditions table above are the full record.

クラスタの構成は [`../meshllm-cluster/README.md`](../meshllm-cluster/README.md) にまとめています。
Cluster hardware and settings are described in [`../meshllm-cluster/README.md`](../meshllm-cluster/README.md).

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
